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
description: 'Zusammenfassung: Informationen zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305969"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren der Hybridbereitstellung von Skype for Business

Für die Konfiguration der Skype for Business-Hybridbereitstellung müssen Sie die folgenden Schritte ausführen:

- [Konfigurieren Sie Ihren lokalen Edgedienst so, dass er mit Teams.](#configure-your-on-premises-edge-service-to-federate-with-teams)
- [Konfigurieren Sie Ihre lokale Umgebung so, dass sie Teams und freigegebenen SIP-Adressraum aktiviert.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Aktivieren des freigegebenen SIP-Adressraums in Teams Organisation](#enable-shared-sip-address-space-in-your-organization).

Wenn Sie über Exchange verfügen, können Sie OAuth zwischen Ihren lokalen Exchange und Skype for Business Onlineumgebungen konfigurieren. Weitere Informationen finden Sie unter [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) und Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Konfigurieren Des lokalen Edgediensts für die Verbindung mit Teams

Der Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung die Kommunikation mit Teams und Skype for Business Onlinebenutzern in Ihrer Organisation. Führen Sie zum Konfigurieren des Verbunds das folgende Cmdlet in Skype for Business Server Verwaltungsshell aus:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Wenn der Wert "-EnablePartnerDiscovery" auf $True festgelegt ist, verwendet Skype for Business Server DNS-Einträge, um Partnerdomänen zu ermitteln, die nicht in der Liste AllowedDomains aufgeführt sind. Wenn der Wert auf "$False" festgelegt Skype for Business Server wird nur ein Verbund mit Domänen in der Liste AllowedDomains verwendet. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.

> [!NOTE]
> Weitere Informationen zum Aktivieren des Verbunds zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern einer Microsoft 365-Organisation finden Sie unter [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Konfigurieren Sie Ihre lokale Umgebung so, dass freigegebener SIP-Adressraum mit Teams

Sie müssen ihre lokale Umgebung auch so konfigurieren, dass sie Teams und freigegebenen SIP-Adressraum aktiviert. Diese Konfiguration bedeutet, Teams möglicherweise Benutzerkonten für denselben Satz von SIP-Domänen hosten können wie Ihre lokale Umgebung, und Nachrichten können zwischen benutzern, die lokal und online gehostet werden, geroutet werden. Sie konfigurieren einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com wie unten beschrieben.

Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com verfügen. Falls vorhanden, entfernen Sie es mithilfe des folgenden Befehls in der Skype for Business Server Verwaltungsshell:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie dann einen neuen Hostinganbieter, indem Sie das cmdlet New-CsHostingProvider wie folgt verwenden: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Aktivieren des freigegebenen SIP-Adressraums in Ihrer Organisation
  
Zusätzlich zu den Änderungen, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrer Teams-Organisation ändern, um gemeinsam genutzten SIP-Adressraum mit Ihrer lokalen Bereitstellung zu aktivieren.  

Um freigegebenen SIP-Adressraum in Ihrer Organisation zu aktivieren, richten Sie eine Remote-PowerShell-Sitzung mit Teams ein, und führen Sie dann das folgende Cmdlet aus:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das SharedSipAddressSpace-Attribut muss "True" bleiben, bis der Onlinezuzug endgültig ist und keine Benutzer lokal bleiben. 
  
Zum Einrichten einer Remote-PowerShell-Sitzung mit Teams (oder Skype for Business Online) müssen Sie zuerst das Teams [PowerShell-Modul installieren.](/microsoftteams/teams-powershell-install) Das Teams PowerShell-Modul ersetzt das Skype Für Busines Online Connector-Modul, das eingestellt wurde.
  
Nach der Installation des Moduls können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Teams und zur Verwendung des Teams -PowerShell-Moduls finden Sie unter [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
