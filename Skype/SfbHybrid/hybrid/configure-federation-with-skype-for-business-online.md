---
title: Konfigurieren von Skype for Business Hybrid
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: 59f5f752e7a6d9fa4047e736f1a988819525955e
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "36160593"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren von Skype for Business Hybrid

Um Skype for Business Hybrid zu konfigurieren, müssen Sie Folgendes tun:

- [Konfigurieren Sie den lokalen Umgebungs Dienst für die Föderation mit Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).
- [Konfigurieren Sie Ihre lokale Umgebung, um Office 365 zu Vertrauen und den freigegebenen SIP-Adressraum mit Office 365 zu aktivieren](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrem Office 365 Mandanten](#enable-shared-sip-address-space-in-your-office-365-tenant).

Beachten Sie, dass Sie bei einer lokalen Exchange-Organisation möglicherweise OAuth zwischen der lokalen Exchange-Umgebung und Skype for Business Online Umgebungen konfigurieren möchten. Weitere Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) und [Planen der Integration von Skype for Business und Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Konfigurieren des lokalen Edge-Diensts für die Zusammenlegung mit Office 365

Mit dem Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Office 365 Benutzern in Ihrer Organisation kommunizieren. Führen Sie das folgende Cmdlet in der Skype for Business Server Verwaltungsshell aus, um den Verbund zu konfigurieren:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

Wenn der Wert "-EnablePartnerDiscovery" auf 1 festgelegt ist, verwendet Skype for Business Server DNS-Einträge, um Partnerdomänen zu testen und zu ermitteln, die nicht in der AllowedDomains-Liste aufgeführt sind. Wenn der Wert auf 0 festgelegt ist, wird Skype for Business Server nur eine Föderation mit Domänen in der AllowedDomains-Liste haben. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Konfigurieren der lokalen Umgebung zur Aktivierung des freigegebenen SIP-Adressraums mit Office 365

Sie müssen auch Ihre lokale Umgebung so konfigurieren, dass Office 365 vertraut und der freigegebene SIP-Adressraum mit Office 365 aktiviert wird. Dies bedeutet, dass Office 365 potenziell Benutzerkonten für dieselbe Gruppe von SIP-Domänen wie Ihre lokale Umgebung hosten kann und dass Nachrichten zwischen Benutzern, die lokal gehostet werden, und Online weitergeleitet werden können.  Konfigurieren Sie hierzu einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com, wie unten beschrieben.

Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com verfügen. Wenn eine vorhanden ist, entfernen Sie Sie mithilfe des folgenden Befehls:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie dann einen neuen Hostinganbieter, verwenden Sie das New-CsHostingProvider-Cmdlet wie folgt: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Aktivieren des freigegebenen SIP-Adressraums in Ihrem Office 365 Mandanten
  
Zusätzlich zu der Änderung, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrem Office 365 Mandanten zu aktiviertem freigegebenem SIP-Adressraum mit Ihrer lokalen Bereitstellung vornehmen.  

Um den freigegebenen SIP-Adressraum in Ihrem Office 365 Mandanten zu aktivieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das SharedSipAddressSpace-Attribut muss "true" bleiben, bis der Wechsel zu Online abgeschlossen ist und keine Benutzer lokal verbleiben. 
  
Um eine Remote-PowerShell-Sitzung mit Teams oder Skype for Business Online einzurichten, müssen Sie zuerst das Skype for Business Online-Connector-Modul für Windows PowerShell installieren, das Sie [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911)erhalten können.
  
Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online und zur Verwendung des Skype for Business Online-Connector-Moduls finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

