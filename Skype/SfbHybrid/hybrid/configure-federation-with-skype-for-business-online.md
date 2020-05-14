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
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221449"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren der Hybridbereitstellung von Skype for Business

Für die Konfiguration der Skype for Business-Hybridbereitstellung müssen Sie die folgenden Schritte ausführen:

- [Konfigurieren Sie den lokalen Edgedienst so, dass er mit Microsoft 365 oder Office 365 verbündet wird](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).
- [Konfigurieren Sie Ihre lokale Umgebung so, dass Sie Microsoft 365 oder Office 365 vertraut und den freigegebenen SIP-Adressraum aktiviert](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).
- [Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrer Microsoft 365-oder Office 365-Organisation](#enable-shared-sip-address-space-in-your-organization).

Beachten Sie, dass Sie bei einer lokalen Exchange-Organisation möglicherweise OAuth zwischen der lokalen Exchange-Umgebung und Skype for Business Online Umgebungen konfigurieren möchten. Weitere Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) und [Planen der Integration von Skype for Business und Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Konfigurieren des lokalen Edge-Diensts für die Zusammenlegung mit Microsoft 365 oder Office 365

Mit dem Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Microsoft 365 oder Office 365 Benutzern in Ihrer Organisation kommunizieren. Führen Sie das folgende Cmdlet in der Skype for Business Server Verwaltungsshell aus, um den Verbund zu konfigurieren:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Wenn der Wert "-EnablePartnerDiscovery" auf "$true" festgelegt ist, verwendet Skype for Business Server DNS-Einträge zum ausprobieren und ermitteln von Partnerdomänen, die nicht in der Liste "AllowedDomains" aufgeführt werden. Wenn der Wert auf $false festgelegt ist, werden Skype for Business Server nur mit Domänen in der AllowedDomains-Liste Partnerverbund. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.

> [!NOTE]
> Weitere Informationen zum Aktivieren des Verbund zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern einer Skype for Business Online Organisation finden Sie unter [Konfigurieren der Verbundunterstützung für einen Skype for Business Online-Kunden in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Konfigurieren der lokalen Umgebung zur Aktivierung des freigegebenen SIP-Adressraums mit Microsoft 365 oder Office 365

Sie müssen auch Ihre lokale Umgebung so konfigurieren, dass Microsoft 365 oder Office 365 vertraut und freigegebener SIP-Adressraum aktiviert wird. Dies bedeutet, dass Microsoft 365 oder Office 365 potenziell Benutzerkonten für dieselbe Gruppe von SIP-Domänen wie Ihre lokale Umgebung hosten kann und Nachrichten zwischen lokal gehosteten und online gehosteten Benutzern weitergeleitet werden können.  Konfigurieren Sie hierzu einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com, wie unten beschrieben.

Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com verfügen. Wenn eine vorhanden ist, entfernen Sie Sie mithilfe des folgenden Befehls:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie dann einen neuen Hostinganbieter, verwenden Sie das New-CsHostingProvider-Cmdlet wie folgt: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Aktivieren von freigegebenem SIP-Adressraum in Ihrer Organisation
  
Zusätzlich zu der Änderung, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrer Microsoft 365-oder Office 365-Organisation zu aktiviertem freigegebenem SIP-Adressraum mit Ihrer lokalen Bereitstellung vornehmen.  

Um den freigegebenen SIP-Adressraum in Ihrer Organisation zu aktivieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das SharedSipAddressSpace-Attribut muss "true" bleiben, bis der Wechsel zu Online abgeschlossen ist und keine Benutzer lokal verbleiben. 
  
Um eine Remote-PowerShell-Sitzung mit Teams oder Skype for Business Online einzurichten, müssen Sie zuerst das Skype for Business Online-Connector-Modul für Windows PowerShell installieren, das Sie [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911)erhalten können.
  
Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online und zur Verwendung des Skype for Business Online-Connector-Moduls finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
