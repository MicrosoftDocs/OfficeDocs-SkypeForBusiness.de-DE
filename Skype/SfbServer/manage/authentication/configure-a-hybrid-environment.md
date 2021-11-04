---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.'
ms.openlocfilehash: fcec1e982af0c5ad778a83fe6af9b58fbd44c7e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746071"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.

**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Skype for Business Server Hybridumgebung.

In einer Hybridkonfiguration werden einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server verwaltet, während andere Benutzer auf der Microsoft 365 oder Office 365 Version von Skype for Business Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer Hybridumgebung zu konfigurieren, müssen Sie zunächst Ihre lokale Installation von Skype for Business Server konfigurieren, um dem Autorisierungsserver zu vertrauen. Der erste Schritt in diesem Prozess kann durch Ausführen des folgenden Skype for Business Server-Verwaltungsshell-Skripts ausgeführt werden:

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

Beachten Sie, dass sich der Bereichsname für einen Mandanten in der Regel vom Organisationsnamen unterscheidet. Tatsächlich ist der Bereichsname fast immer identisch mit der Mandanten-ID. Aus diesem Grund wird die erste Zeile im Skript verwendet, um den Wert der TenantId-Eigenschaft für den angegebenen Mandanten (in diesem Fall fabrikam.com) zurückzugeben und diesen Namen dann der Variablen $TenantId zuzuweisen:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Um dieses Skript auszuführen, müssen Sie Skype for Business Online-PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen. Wenn Sie diese Cmdlets nicht installiert haben, schlägt ihr Skript fehl, da das Cmdlet Get-CsTenant nicht verfügbar ist. Nach Abschluss des Skripts müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem Autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem Autorisierungsserver konfigurieren. Dies kann nur mithilfe der Microsoft Online Services-Cmdlets erfolgen.

> [!NOTE]
> Wenn Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie sie mit dem Cmdlet aus dem PowerShell-Repository `install-module MSOnline` installieren. Ausführliche Informationen zum Installieren und Verwenden des Microsoft Online Services-Moduls finden Sie auf der Microsoft 365 Website. In diesen Anweisungen erfahren Sie auch, wie Sie einmaliges Anmelden, Verbund und Synchronisierung zwischen Microsoft 365 oder Office 365 und Active Directory konfigurieren. 



Nachdem Sie Microsoft 365 oder Office 365 konfiguriert und Microsoft 365 oder Office 365 Dienstprinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen registrieren. mit diesen Dienstprinzipalen. Zu diesem Zweck müssen Sie zuerst ein X.509 Base64-Zertifikat abrufen, das als . CER-Datei. Dieses Zertifikat wird dann auf die Microsoft 365 oder Office 365 Dienstprinzipale angewendet.

Wenn Sie das X.509-Zertifikat abgerufen haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Modul "Microsoft Online Windows PowerShell", das die Cmdlets enthält, die zum Verwalten von Dienstprinzipalen verwendet werden können:

```PowerShell
Import-Module MSOnline
```

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Connect-MsolService
```

Nachdem Sie die EINGABETASTE gedrückt haben, wird ein Dialogfeld für Anmeldeinformationen angezeigt. Geben Sie ihren Microsoft 365 oder Office 365 Benutzernamen und das Kennwort in das Dialogfeld ein, und klicken Sie dann auf "OK".

Sobald Sie mit Microsoft 365 oder Office 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu Ihren Dienstprinzipalen zurückzugeben:

```PowerShell
Get-MsolServicePrincipal
```

Sie sollten ähnliche Informationen für alle Dienstprinzipale abrufen:

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

Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen. Um das Zertifikat zu importieren und zu codieren, verwenden Sie die folgenden Windows PowerShell Befehle, wobei Sie den vollständigen Dateipfad zu Ihrem angeben. CER-Datei beim Aufrufen der Importmethode:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365 oder Office 365 Dienstprinzipalen zuweisen. Verwenden Sie hierzu zuerst die Get-MsolServicePrincipal, um den Wert der AppPrincipalId-Eigenschaft sowohl für die Skype for Business Server als auch für die Microsoft Exchange-Dienstprinzipale abzurufen. Der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird. Verwenden Sie mit dem AppPrincipalId-Eigenschaftswert für Skype for Business Server den folgenden Befehl, um das Zertifikat Skype For Business Online-Version zuzuweisen:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Wiederholen Sie dann den Befehl, dieses Mal mithilfe des AppPrincipalId-Eigenschaftswerts für Exchange 2013.

Wenn Sie dieses Zertifikat später löschen müssen, z. B. wenn es abgelaufen ist, können Sie dies tun, indem Sie zuerst die KeyId für das Zertifikat abrufen:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Dieser Befehl gibt Daten wie den folgenden zurück:

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

Zusätzlich zum Zuweisen eines Zertifikats müssen Sie auch den Exchange Online Dienstprinzipal und Die lokale Version von Skype for Business Server externen Webdienst-URLs als Microsoft 365 oder Office 365 Dienstprinzipal konfigurieren. Dies kann durch Ausführen der folgenden beiden Befehle erfolgen. 

Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die URL der externen Webdienste für den pool Skype for Business Server. Wiederholen Sie diese Schritte, um alle URLs für externe Webdienste in der Bereitstellung hinzuzufügen.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
