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
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Teams konfigurieren.'
ms.openlocfilehash: 5593dce3bef26e2b3f528618d88e4f87e1996596
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574130"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren der Hybridbereitstellung von Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Für die Konfiguration der Skype for Business-Hybridbereitstellung müssen Sie die folgenden Schritte ausführen:

- [Konfigurieren Sie Ihren lokalen Edgedienst so, dass er mit Teams verbunden wird.](#configure-your-on-premises-edge-service-to-federate-with-teams)
- [Konfigurieren Sie Ihre lokale Umgebung so, dass sie Teams vertraut und den freigegebenen SIP-Adressraum aktiviert.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrer Teams Organisation.](#enable-shared-sip-address-space-in-your-organization)

Wenn Sie Exchange lokal haben, können Sie OAuth zwischen Ihren Exchange lokalen und Onlineumgebungen konfigurieren. Weitere Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) und Planen der Integration von Skype for Business und [Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Konfigurieren Des lokalen Edgediensts für den Verbund mit Teams

Der Partnerverbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung die Kommunikation mit Teams Benutzern in Ihrer Organisation. Führen Sie zum Konfigurieren des Partnerverbunds das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Wenn der Wert "-EnablePartnerDiscovery" auf $True festgelegt ist, verwendet Skype for Business Server DNS-Einträge, um Partnerdomänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind. Wenn der Wert auf $False festgelegt ist, wird Skype for Business Server nur mit Domänen verbunden, die in der Liste "AllowedDomains" enthalten sind. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.

> [!NOTE]
> Weitere Informationen zum Aktivieren des Partnerverbunds zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern einer Microsoft 365 Organisation finden Sie unter Konfigurieren der [Verbundunterstützung für einen Microsoft 365 Kunden in Skype for Business Server.](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Konfigurieren Ihrer lokalen Umgebung zum Aktivieren des freigegebenen SIP-Adressraums mit Teams

Außerdem müssen Sie Ihre lokale Umgebung so konfigurieren, dass sie Teams vertraut und den freigegebenen SIP-Adressraum aktiviert. Diese Konfiguration bedeutet, Teams benutzerkonten für den gleichen Satz von SIP-Domänen wie Ihre lokale Umgebung hosten können, und Nachrichten können zwischen lokal und online gehosteten Benutzern weitergeleitet werden. Sie konfigurieren einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com wie unten beschrieben.

Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com verfügen. Wenn einer vorhanden ist, entfernen Sie ihn mithilfe des folgenden Befehls in der Skype for Business Server Verwaltungsshell:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie dann einen neuen Hostinganbieter mithilfe des Cmdlets New-CsHostingProvider wie folgt: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Aktivieren des freigegebenen SIP-Adressraums in Ihrer Organisation
  
Zusätzlich zu der Änderung, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrer Teams Organisation vornehmen, um den freigegebenen SIP-Adressraum mit Ihrer lokalen Bereitstellung zu aktivieren.  

Um den freigegebenen SIP-Adressraum in Ihrer Organisation zu aktivieren, richten Sie eine PowerShell-Remotesitzung mit Teams ein, und führen Sie dann das folgende Cmdlet aus:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das SharedSipAddressSpace-Attribut muss "True" bleiben, bis der Umstieg auf die Online-Bereitstellung abgeschlossen ist und keine Benutzer lokal bleiben. 
  
Um eine Remote-PowerShell-Sitzung mit Teams einzurichten, müssen Sie zuerst das [Teams PowerShell-Modul](/microsoftteams/teams-powershell-install)installieren. Das Teams PowerShell-Modul ersetzt die Skype für das Busines Online Connector-Modul, das eingestellt wurde.
  
Nach der Installation des Moduls können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Teams und zur Verwendung des Teams PowerShell-Moduls finden Sie unter [Einrichten ihres Computers für Windows PowerShell.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
