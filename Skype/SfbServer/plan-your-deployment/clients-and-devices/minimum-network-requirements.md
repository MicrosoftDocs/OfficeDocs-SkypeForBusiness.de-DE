---
title: Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Zusammenfassung: Informationen für Organisationen, die Office 365 nicht verwenden und auf von Organisationen gehostete Besprechungen zugreifen müssen.'
ms.openlocfilehash: 1017c81fc3432fbd409077b89809d725b2b0e2cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277482"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
 
**Zusammenfassung:**  Informationen für Organisationen, die Office 365 nicht verwenden und auf von Organisationen gehostete Besprechungen zugreifen müssen. Dieser Artikel ist nicht für die Benutzer dieser apps vorgesehen.
  
Damit Benutzer die Skype-Besprechungs-App verwenden können, um an Besprechungen teilzunehmen, die in Skype for Business online gehostet werden, sollten Netzwerkadministratoren von Organisationen, die Office 365 nicht verwenden, Whitelists oder anderweitig verfügbare FQDNs, IPS und Ports zur Verfügung stellen.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Anforderungen für Konnektivität mit der Skype-Besprechungs-App

Bei den hier aufgelisteten Informationen handelt es sich um eine Teilmenge der [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), die eine größere Tiefe bieten und immer auf dem neuesten Stand sind.
                    
 
|App |Ziel-FQDNs  |IP-Adressen  |Ports  |
|---|---------|---------|---------|
|**Skype-Besprechungs-App** | \*. lync.com <br/>\*. Infra.lync.com<br/>\*. Pipe.Aria.Microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*Power<span></span>Point. officeapps.Live.com <br/>\*. Office.Live.com<br/>\*. CDN.Office.net<br/>*.s-microsoft.com<br/>        |   Diese IP-Adressen werden häufig aktualisiert.  Sehen Sie sich die [IP-Bereiche von Skype for Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie die [IP-Bereiche von Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) an         |TCP: 80 &amp; 443<br/>UDP: 3478–3481<br/>
|**Microsoft Teams**    | \*<span></span>. Microsoft.com <br/>\*<span></span>. Skype.com | Diese IP-Adressen werden häufig aktualisiert.  Sehen Sie sich die [IP-Bereiche von Skype for Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie die [IP-Bereiche von Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) an      |TCP: 443 <br/> UDP: 3478–3481

## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Planen von Besprechungs Clients (app für Web App und Besprechungen)](meetings-clients.md)

[Bereitstellen von Webdownload-Clients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
