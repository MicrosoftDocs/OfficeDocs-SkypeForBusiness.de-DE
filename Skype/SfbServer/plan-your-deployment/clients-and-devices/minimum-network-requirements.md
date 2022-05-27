---
title: Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Zusammenfassung: Informationen für Organisationen, die keine Microsoft 365 oder Office 365 verwenden und auf Besprechungen zugreifen müssen, die von Organisationen gehostet werden, die dies tun.'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674527"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Mindestnetzwerkanforderungen für die Skype-Besprechungs-App

**Zusammenfassung:** Informationen für Organisationen, die keine Microsoft 365 oder Office 365 verwenden und auf Besprechungen zugreifen müssen, die von Organisationen gehostet werden, die dies tun. Dieser Artikel richtet sich nicht an Office 365 oder Microsoft 365 Endbenutzer.

Benutzer der Skype-Besprechungs-App in Organisationen, die keine Microsoft 365 oder Office 365 verwenden, müssen möglicherweise an Besprechungen teilnehmen, die in Skype for Business Online gehostet werden. Um an diesen Besprechungen teilzunehmen, müssen ihre Netzwerkadministratoren die folgenden FQDNs, IP-Adressen und Ports über ihre Firewall zulassen.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Anforderungen für Skype Besprechungs-App-Konnektivität

Die hier aufgeführten Informationen sind eine Teilmenge der Informationen in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges). Dieses Thema ist viel ausführlicher und wird immer aktuell sein.

|App|Ziel-FQDNs|IP-Adressen|Ports|
|---|---------|---------|---------|
|**Skype Besprechungs-App**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Diese IP-Adressen werden häufig aktualisiert. Siehe [Skype for Business und Microsoft Teams IP-Bereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) sowie [Office IP-Bereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Microsoft Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Diese IP-Adressen werden häufig aktualisiert. Siehe [Skype for Business und Microsoft Teams IP-Bereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) sowie [Office IP-Bereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Planen von Besprechungsclients (Web-App und Besprechungs-App)](meetings-clients.md)

[Bereitstellen von herunterladbaren Webclients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype-Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
