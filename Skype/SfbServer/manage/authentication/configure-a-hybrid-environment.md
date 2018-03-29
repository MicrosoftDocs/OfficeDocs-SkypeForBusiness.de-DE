---
title: Konfigurieren einer Hybridumgebung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren von Skype für Business Server 2015 in einer hybridumgebung.'
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>Konfigurieren einer Hybridumgebung in Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren von Skype für Business Server 2015 in einer hybridumgebung.
  
In einer hybridkonfiguration sind einige Ihrer Benutzer, die sich in einer lokalen Installation von Skype für Business Server 2015, während andere Benutzer auf der Office 365-Version von Skype für Business Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer hybridumgebung konfigurieren, müssen Sie zuerst Ihrer lokalen Installation von Skype für Business Server 2015 Vertrauenswürdigkeit des Office 365-Autorisierung-Servers konfigurieren. Der erste Schritt in diesem Prozess kann durch Ausführen der folgenden Skype für Business Server-Verwaltungsshell-Skripts durchgeführt werden:
  
```
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
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

Nach Abschluss des Skripts müssen Sie dann eine Vertrauensstellung zwischen Skype für Business Server 2015 und den autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013 und den autorisierungsserver konfigurieren. Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.
  
> [!NOTE]
> Falls Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie zunächst zwei Dinge erledigen, bevor Sie fortfahren. Laden Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten herunter, und installieren Sie sie. Nach Abschluss der Installation herunterladen und Installieren der 64-Bit-Version von der Microsoft Online Services-Modul für Windows PowerShell. Ausführliche Informationen zum Installieren und Verwenden der Microsoft Online Services-Modul finden Sie auf der Office 365-Website. Diese Anweisungen auch informiert Sie, wie Sie einmaliges Anmelden, Verbund und die Synchronisierung zwischen dem Office 365 und Active Directory konfigurieren. 
  
Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.
  
Nachdem Sie Office 365 konfiguriert haben, und Sie Office 365-Dienstprinzipale für Skype für Business Server 2015 und Exchange 2013 erstellt haben, müssen Sie dann Ihre Anmeldeinformationen mit diesen dienstprinzipalen zu registrieren. Zu diesem Zweck müssen Sie zunächst ein Base64-kodiertes X.509-Zertifikat anfordern, das als CER-Datei gespeichert wird. Dieses Zertifikat wird dann auf die Office 365-Dienst-Prinzipale angewendet werden.
  
Wenn Sie das x. 509-Zertifikat abgerufen haben, starten Sie den Microsoft Online Services-Modul (klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Online Services**, und klicken Sie dann auf **Microsoft Online Services-Modul für Windows PowerShell**). Nachdem das Modul Dienste geöffnet wurde, geben Sie den folgenden zum Importieren des Microsoft Online Windows PowerShell-Moduls mit den Cmdlets, die zum Verwalten von Dienstprinzipale verwendet werden können:
  
```
Import-Module MSOnlineExtended
```

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE, um zu Office 365 zu verbinden:
  
```
Connect-MsolService
```

Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie im Dialogfeld Ihre Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.
  
Sobald Sie zu Office 365 verbunden sind, können Sie den folgenden Befehl, um die Rückgabe von Informationen über Ihre Dienstprinzipale ausführen:
  
```
Get-MsolServicePrincipal
```

Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen. Zum Importieren und das Zertifikat zu codieren, verwenden Sie die folgenden Windows PowerShell-Befehle, wird den vollständige Pfad zum Angeben der. CER-Datei beim Aufrufen der Import-Methode:
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Nachdem das Zertifikat importiert und codiert wurde, können Sie dann das Zertifikat für Ihre Office 365-Dienstprinzipale zuweisen. Klicken Sie dazu zunächst mit dem das Get-MsolServicePrincipal zum Abrufen des Werts der AppPrincipalId-Eigenschaft für die Skype für Business Server und die Microsoft Exchange-Dienst-Prinzipale; der Wert der AppPrincipalId-Eigenschaft wird verwendet werden, um den Dienstprinzipal zugewiesen wird, das Zertifikat zu identifizieren. Mit der AppPrincipalId-Eigenschaft Wert für Skype für Business Server 2015 Umwelt; verwenden den folgenden Befehl, um das Zertifikat für die Office 365-Version von Skype für Business Server zuzuweisen:
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Sie sollten den Befehl dann diesmal den AppPrincipalId-Eigenschaftswert für Exchange 2013 mit wiederholen.
  
Falls Sie das Zertifikat zu einem späteren Zeitpunkt löschen müssen, rufen Sie dazu zunächst die KeyID für das Zertifikat ab:
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Der entsprechende Befehl gibt in etwa folgende Daten zurück:
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Zusätzlich zum Zuweisen eines Zertifikats, müssen Sie auch Konfigurieren der Exchange Online Service Principal und Konfigurieren Ihrer lokalen Version von Skype für Business Server 2015 externen Webdienst-URLs als ein Office 365-Dienstprinzipal. Kann erfolgen, indem Sie die folgenden zwei Befehle ausführen. 
  
Im folgenden Beispiel wird die lync.contoso.com externen Webdienste-URL für die Skype für Business Server-Pool. Wiederholen Sie die folgenden Schritte aus, um alle externen Web Services-URLs in der Bereitstellung hinzuzufügen.
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```