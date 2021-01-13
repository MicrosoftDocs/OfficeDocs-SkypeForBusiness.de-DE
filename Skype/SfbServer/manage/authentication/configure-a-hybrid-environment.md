---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung.'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828485"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Konfigurieren sie die Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung.

**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für die Skype for Business Server-Hybridumgebung.

In einer Hybridkonfiguration werden einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server und andere Benutzer in der Microsoft 365- oder Office 365-Version von Skype for Business Server gespeichert. Zum Konfigurieren der Server-zu-Server-Authentifizierung in einer Hybridumgebung müssen Sie zunächst Ihre lokale Installation von Skype for Business Server so konfigurieren, dass sie dem Autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann durch Ausführen des folgenden Skype for Business Server-Verwaltungsshell-Skripts ausgeführt werden:

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

Beachten Sie, dass der Bereichsname für einen Mandanten in der Regel vom Namen der Organisation abhing. Tatsächlich ist der Bereichsname fast immer mit der Mandanten-ID identisch. Aus diesem Grund wird die erste Zeile im Skript verwendet, um den Wert der Eigenschaft TenantId für den angegebenen Mandanten zurück (in diesem Fall fabrikam.com) und diesen Namen dann der Variablen $TenantId:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Zum Ausführen dieses Skripts müssen Sie das Skype for Business Online -PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen. Wenn Sie diese Cmdlets nicht installiert haben, kann das Skript nicht ausgeführt werden, da Get-CsTenant cmdlet nicht verfügbar ist. Nach Abschluss des Skripts müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem Autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem Autorisierungsserver konfigurieren. Dies kann nur mithilfe der cmdlets Microsoft Online Services werden.

> [!NOTE]
> Wenn Sie die cmdlets Microsoft Online Services installiert haben, müssen Sie sie über das PowerShell-Repository mit dem Cmdlet `install-module MSOnline` installieren. Ausführliche Informationen zum Installieren und Verwenden des Microsoft Online Services Finden Sie auf der Microsoft 365-Website. In diesen Anweisungen erfahren Sie auch, wie Sie einmaliges Anmelden, einen Verbund und eine Synchronisierung zwischen Microsoft 365 oder Office 365 und Active Directory konfigurieren. 



Nachdem Sie Microsoft 365 oder Office 365 konfiguriert und Microsoft 365- oder Office 365-Dienstprinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienstprinzipalen registrieren. Dazu müssen Sie zuerst ein X.509 Base64-Zertifikat abrufen, das als gespeichert ist. CER-Datei. Dieses Zertifikat wird dann auf die Microsoft 365- oder Office 365-Dienstprinzipale angewendet.

Wenn Sie das X.509-Zertifikat erhalten haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Microsoft Online Windows PowerShell-Modul, das die Cmdlets enthält, mit denen Dienstprinzipale verwaltet werden können:

```PowerShell
Import-Module MSOnline
```

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Connect-MsolService
```

Nachdem Sie die EINGABETASTE drücken, wird ein Anmeldeinformationsdialogfeld angezeigt. Geben Sie ihren Benutzernamen und das Kennwort für Microsoft 365 oder Office 365 in das Dialogfeld ein, und klicken Sie dann auf "OK".

Sobald Sie mit Microsoft 365 oder Office 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu Ihren Dienstprinzipalen zurück zu erhalten:

```PowerShell
Get-MsolServicePrincipal
```

Sie sollten für alle Dienstprinzipale ähnliche Informationen wie dies erhalten:

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

Im nächsten Schritt importieren, codieren und weisen Sie das X.509-Zertifikat zu. Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell, und achten Sie darauf, den vollständigen Dateipfad zu Ihrer anzugeben. CER-Datei beim Aufrufen der Importmethode:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365- oder Office 365-Dienstprinzipalen zuweisen. Verwenden Sie dazu zunächst die Get-MsolServicePrincipal, um den Wert der Eigenschaft "AppPrincipalId" sowohl für skype for Business Server als auch für die Microsoft Get-MsolServicePrincipal abzurufen. Der Wert der Eigenschaft "AppPrincipalId" wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird. Mit dem Wert der Eigenschaft "AppPrincipalId" für Skype for Business Server können Sie das Zertifikat mit dem folgenden Befehl der Skype For Business Online-Version zuweisen:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Wiederholen Sie dann den Befehl, und verwenden Sie dieses Mal den Wert der AppPrincipalId-Eigenschaft für Exchange 2013.

Wenn Sie das Zertifikat später löschen müssen, z. B. wenn es abgelaufen ist, können Sie dies tun, indem Sie zuerst die KeyId für das Zertifikat abrufen:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Dieser Befehl gibt Daten wie die folgenden zurück:

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

Zusätzlich zum Zuweisen eines Zertifikats müssen Sie auch den Exchange Online Service Principal konfigurieren und Ihre lokale Version der externen Webdienste-URLs von Skype for Business Server als Microsoft 365- oder Office 365-Dienstprinzipal konfigurieren. Dazu können Sie die folgenden beiden Befehle ausführen. 

Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die URL der externen Webdienste für den Skype for Business Server-Pool. Wiederholen Sie diese Schritte, um alle URLs für externe Webdienste in der Bereitstellung hinzuzufügen.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
