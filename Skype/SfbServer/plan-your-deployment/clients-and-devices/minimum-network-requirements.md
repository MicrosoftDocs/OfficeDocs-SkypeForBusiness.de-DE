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
ms.custom: null
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Zusammenfassung: Informationen für Organisationen, die keine Microsoft 365 oder Office 365 verwenden und auf Besprechungen zugreifen müssen, die von Organisationen gehostet werden, die dies tun.'
---

# <a name="skype-meetings-app-minimum-network-requirements"></a>Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
 
**Zusammenfassung:**  Informationen für Organisationen, die keine Microsoft 365 oder Office 365 verwenden und auf Besprechungen zugreifen müssen, die von Organisationen gehostet werden, die dies tun. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.
  
Damit Benutzer Skype Besprechungs-App verwenden können, um an Besprechungen teilzunehmen, die in Skype for Business Online gehostet werden, sollten Netzwerkadministratoren von Organisationen, die Microsoft 365 oder Office 365 nicht verwenden, die unten genannten FQDNs, IPs und Ports zulassen oder anderweitig zur Verfügung stellen.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Anforderungen für die Konnektivität Skype Besprechungs-App

Die hier aufgeführten Informationen sind eine Teilmenge der [Office 365 URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), die mehr Tiefe bieten und immer auf dem neuesten Stand sind.
                    
 
|App |Ziel-FQDNs  |IP-Adressen  |Ports  |
|---|---------|---------|---------|
|**Skype-Besprechungs-App** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Diese IP-Adressen werden häufig aktualisiert.  Siehe [Skype for Business IP-Bereiche](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie [Office IP-Bereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Microsoft Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Diese IP-Adressen werden häufig aktualisiert.  Siehe [Skype for Business IP-Bereiche](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie [Office IP-Bereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)

[Bereitstellen von herunterladbaren Webclients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
