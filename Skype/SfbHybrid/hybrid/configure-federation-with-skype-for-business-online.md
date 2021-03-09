---
title: Konfigurieren der Hybridbereitstellung von Skype for Business
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online konfigurieren.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569217"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren der Hybridbereitstellung von Skype for Business

Für die Konfiguration der Skype for Business-Hybridbereitstellung müssen Sie die folgenden Schritte ausführen:

- [Konfigurieren Sie Ihren lokalen Edgedienst für eine Verbindung mit Microsoft 365 oder Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).
- [Konfigurieren Sie Ihre lokale Umgebung so, dass Sie Microsoft 365 oder Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)vertrauen und gemeinsam genutzten SIP-Adressraum aktivieren.
- [Aktivieren Sie freigegebenen SIP-Adressraum in Ihrer Microsoft 365- oder Office 365-Organisation.](#enable-shared-sip-address-space-in-your-organization)

Beachten Sie, dass Sie OAuth möglicherweise zwischen Ihren lokalen Exchange- und Skype for Business Online-Umgebungen konfigurieren möchten, wenn Sie über Exchange lokal verfügen. Weitere Informationen finden Sie unter  [Verwalten der Server-zu-Server-Authentifizierung in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) und Planen der Integration von Skype for Business und [Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Konfigurieren Des lokalen Edgediensts für die Zusammenarbeit mit Microsoft 365 oder Office 365

Der Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung die Kommunikation mit Microsoft 365- oder Office 365-Benutzern in Ihrer Organisation. Führen Sie zum Konfigurieren des Verbunds das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Wenn der Wert "-EnablePartnerDiscovery" auf $True festgelegt ist, verwendet Skype for Business Server DNS-Einträge, um Partnerdomänen zu ermitteln, die nicht in der Liste AllowedDomains aufgeführt sind. Wenn der Wert auf $False festgelegt ist, wird Skype for Business Server nur mit Domänen in der Liste AllowedDomains in Verbindung gesetzt. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.

> [!NOTE]
> Weitere Informationen zum Aktivieren des Verbunds zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern einer Skype for Business Online-Organisation finden Sie unter [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Konfigurieren Ihrer lokalen Umgebung zum Aktivieren des freigegebenen SIP-Adressraums mit Microsoft 365 oder Office 365

Außerdem müssen Sie Ihre lokale Umgebung so konfigurieren, dass Sie Microsoft 365 oder Office 365 vertrauen und gemeinsam genutzten SIP-Adressraum aktivieren. Dies bedeutet, dass Microsoft 365 oder Office 365 möglicherweise Benutzerkonten für denselben Satz von SIP-Domänen hosten kann wie Ihre lokale Umgebung, und Nachrichten können zwischen Benutzern, die lokal und online gehostet werden, geroutet werden.  Konfigurieren Sie dazu einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com wie unten beschrieben.

Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com verfügen. Falls vorhanden, entfernen Sie es mithilfe des folgenden Befehls:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie dann einen neuen Hostinganbieter, und verwenden Sie New-CsHostingProvider cmdlet wie folgt: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Aktivieren des freigegebenen SIP-Adressraums in Ihrer Organisation
  
Zusätzlich zu den Änderungen, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrer Microsoft 365- oder Office 365-Organisation ändern, um gemeinsam genutzten SIP-Adressraum mit Ihrer lokalen Bereitstellung zu aktivieren.  

Um freigegebenen SIP-Adressraum in Ihrer Organisation zu aktivieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das SharedSipAddressSpace-Attribut muss "True" bleiben, bis der Onlinezuzug endgültig ist und keine Benutzer lokal bleiben. 
  
Zum Einrichten einer Remote-PowerShell-Sitzung mit Teams oder Skype for Business Online müssen Sie zunächst das [Teams PowerShell-Modul installieren.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
  
Nach der Installation des Moduls können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online und zur Verwendung des Skype for Business Online Connector-Moduls finden Sie unter [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
