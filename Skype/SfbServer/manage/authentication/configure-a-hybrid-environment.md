---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221679"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Konfigurieren Sie die Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.

**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Skype for Business Server Hybridumgebung.

In einer Hybrid Konfiguration werden einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server verwaltet, während andere Benutzer in der Microsoft 365-oder Office 365-Version von Skype for Business Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer Hybridumgebung konfigurieren zu können, müssen Sie zunächst Ihre lokale Installation von Skype for Business Server so konfigurieren, dass Sie dem autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann ausgeführt werden, indem Sie das folgende Skype for Business Server-Verwaltungsshell-Skript ausführen:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Beachten Sie, dass der Bereichsname für einen Mandanten in der Regel nicht mit dem Namen der Organisation identisch ist. Tatsächlich ist der Bereichsname fast immer identisch mit der Mandanten-ID. Aus diesem Grund wird die erste Codezeile im Skript verwendet, um den Wert der Mandanten-Eigenschaft für den angegebenen Mandanten (in diesem Fall fabrikam.com) zurückzugeben und diesen Namen dann der Variablen $TenantId zuzuweisen:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Um dieses Skript auszuführen, müssen Sie Skype for Business Online PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen. Wenn Sie diese Cmdlets nicht installiert haben, tritt beim Skript ein Fehler auf, da das Cmdlet Get-CsTenant nicht verfügbar ist. Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem autorisierungsserver konfigurieren. Dies kann nur mithilfe der Microsoft Online Services-Cmdlets erfolgen.

> [!NOTE]
> Wenn Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie Sie mit dem Cmdlet aus dem PowerShell-Repository installieren `install-module MSOnline` . Ausführliche Informationen zum Installieren und Verwenden des Microsoft Online Services-Modul finden Sie auf der Microsoft 365-Website. In diesen Anweisungen erfahren Sie außerdem, wie Sie einmaliges Anmelden, Partnerverbund und Synchronisierung zwischen Microsoft 365 oder Office 365 und Active Directory konfigurieren. 



Nachdem Sie Microsoft 365 oder Office 365 konfiguriert und Microsoft 365 oder Office 365 Dienst Prinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren. Um dies zu erreichen, müssen Sie zunächst ein X. 509 Base64-Zertifikat erhalten, das als gespeichert wurde. CER-Datei. Dieses Zertifikat wird dann auf die Microsoft 365-oder Office 365-Dienst Prinzipale angewendet.

Wenn Sie das X. 509-Zertifikat erhalten haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Microsoft Online Windows PowerShell-Modul, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:

```PowerShell
Import-Module MSOnline
```

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Connect-MsolService
```

Nachdem Sie die EINGABETASTE gedrückt haben, wird ein Dialogfeld Anmeldeinformationen angezeigt. Geben Sie im Dialogfeld Ihren Microsoft 365-oder Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.

Sobald Sie eine Verbindung mit Microsoft 365 oder Office 365 hergestellt haben, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:

```PowerShell
Get-MsolServicePrincipal
```

Sie sollten für alle Dienst Prinzipale Informationen zurück erhalten, die diesem ähneln:

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

Der nächste Schritt besteht darin, das X. 509-Zertifikat zu importieren, zu codieren und zuzuweisen. Um das Zertifikat zu importieren und zu codieren, verwenden Sie die folgenden Windows PowerShell Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad angegeben wird. CER-Datei, wenn Sie die Import-Methode aufrufen:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365-oder Office 365-Dienst Prinzipalen zuweisen. Verwenden Sie dazu zunächst das Get-MsolServicePrincipal, um den Wert der AppPrincipalId-Eigenschaft sowohl für die Skype for Business Server als auch für die Microsoft Exchange Dienst Prinzipale abzurufen; der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wurde. Wenn der Wert der AppPrincipalId-Eigenschaft für Skype for Business Server in Hand ist, verwenden Sie den folgenden Befehl, um das Zertifikat der Skype for Business Online-Version zuzuweisen:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Sie sollten dann den Befehl wiederholen, diesmal mit dem AppPrincipalId-Eigenschaftswert für Exchange 2013.

Wenn Sie dieses Zertifikat später löschen müssen, beispielsweise wenn es abgelaufen ist, können Sie dies tun, indem Sie zunächst die KeyId für das Zertifikat abrufen:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Dieser Befehl gibt Daten wie diese zurück:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Anschließend können Sie das Zertifikat mit einem Befehl wie dem folgenden löschen:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Neben dem Zuweisen eines Zertifikats müssen Sie auch den Exchange Online Dienstprinzipal konfigurieren und die lokale Version Skype for Business Server externer Webdienst-URLs als Microsoft 365 oder Office 365 Dienstprinzipal konfigurieren. Dies kann durch Ausführen der folgenden beiden Befehle erfolgen. 

Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die externe Webdienste-URL für den Skype for Business Server Pool. Wiederholen Sie diese Schritte, um alle externen Webdienste-URLs in der Bereitstellung hinzuzufügen.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
