---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung'
ms.openlocfilehash: 5d56f098589355b85f942a6b1eb80d8ab6c03225
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992352"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Konfigurieren Sie die Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung.

**Zusammenfassung:** Konfigurieren der Server-zu-Server-Authentifizierung für die Skype for Business Server-Hybridumgebung

In einer Hybrid Konfiguration sind einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server beheimatet, während andere Benutzer in der Office 365-Version von Skype for Business Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer Hybridumgebung zu konfigurieren, müssen Sie zuerst Ihre lokale Installation von Skype for Business Server so konfigurieren, dass Sie dem Office 365-autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann durchführen des folgenden Skype for Business Server-Verwaltungsshell-Skripts erfolgen:

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

Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall „fabrikam.com“) und den entsprechenden Namen anschließend der Variablen „$TenantId“ zuzuweisen:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Damit Sie dieses Skript ausführen können, müssen Sie das Skype for Business Online PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen. Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist. Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem autorisierungsserver konfigurieren. Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.

> [!NOTE]
> Wenn Sie die Microsoft Online Services-Cmdlets noch nicht installiert haben, müssen Sie Sie im PowerShell-Repository mit dem Cmdlet `install-module MSOnline`installieren. Detaillierte Informationen zum Installieren und Verwenden des Microsoft Online Services-Moduls finden Sie auf der Office 365-Website. In diesen Anweisungen erfahren Sie auch, wie Sie das einmalige Anmelden, den Verbund und die Synchronisierung zwischen Office 365 und Active Directory konfigurieren. 



Nachdem Sie Office 365 konfiguriert haben und nachdem Sie Office 365-Dienst Prinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren. Um dies zu erreichen, müssen Sie zuerst ein X. 509-Base64-Zertifikat abrufen, das als. CER-Datei. Dieses Zertifikat wird dann auf die Office 365-Dienst Prinzipale angewendet.

Wenn Sie das X. 509-Zertifikat erhalten haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Microsoft Online Windows PowerShell-Modul, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:

```PowerShell
Import-Module MSOnline
```

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, um eine Verbindung mit Office 365 herzustellen:

```PowerShell
Connect-MsolService
```

Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie Ihren Office 365-Benutzernamen und das Kennwort in das Dialogfeld ein, und klicken Sie dann auf OK.

Sobald Sie mit Office 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:

```PowerShell
Get-MsolServicePrincipal
```

Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:

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

Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen. Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell-Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad zu Ihrem. CER-Datei beim Aufrufen der Import-Methode:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat ihren Office 365-Dienst Prinzipalen zuweisen. Verwenden Sie dazu zunächst die Get-MsolServicePrincipal-Eigenschaft, um den Wert der AppPrincipalId-Eigenschaft sowohl für den Skype for Business-Server als auch für die Microsoft Exchange-Dienst Prinzipale abzurufen. der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird. Wenn der Wert der AppPrincipalId-Eigenschaft für Skype for Business Server in der Hand ist, verwenden Sie den folgenden Befehl, um das Zertifikat der Skype for Business Online-Version zuzuweisen:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Sie sollten diesen Befehl dann wiederholen, indem Sie dieses Mal den AppPrincipalId-Eigenschaftswert für Exchange 2013 verwenden.

Wenn Sie dieses Zertifikat später löschen müssen, beispielsweise wenn es abgelaufen ist, können Sie dies tun, indem Sie zunächst den KeyId für das Zertifikat abrufen:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Der entsprechende Befehl gibt in etwa folgende Daten zurück:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Neben dem Zuweisen eines Zertifikats müssen Sie auch den Exchange Online-Dienstprinzipal konfigurieren und die lokale Version der externen Skype for Business Server-URLs als Office 365-Dienstprinzipal konfigurieren. Dies kann durch Ausführen der folgenden beiden Befehle erfolgen. 

Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die externe Webdienste-URL für den Skype for Business-Server Pool. Wiederholen Sie diese Schritte, um alle externen Webdienste-URLs in der Bereitstellung hinzuzufügen.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
