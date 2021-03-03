---
title: Mindestnetzwerkanforderungen für die Skype-Besprechungen-App
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Zusammenfassung: Informationen für Organisationen, die Microsoft 365 oder Office 365 nicht verwenden und auf Besprechungen zugreifen müssen, die von Organisationen gehostet werden, die dies tun.'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816305"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Mindestnetzwerkanforderungen für die Skype-Besprechungen-App
 
**Zusammenfassung:**  Informationen für Organisationen, die Microsoft 365 oder Office 365 nicht verwenden und auf Von Organisationen gehostete Besprechungen zugreifen müssen. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.
  
Damit Benutzer mit der Skype-Besprechungs-App an in Skype for Business Online gehosteten Besprechungen teilnehmen können, sollten Netzwerkadministratoren von Organisationen, die Microsoft 365 oder Office 365 nicht verwenden, die unten genannten FQDNs, IPs und Ports zulassen oder anderweitig verfügbar machen.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Anforderungen für die Konnektivität der Skype-Besprechungs-App

Die hier aufgeführten Informationen sind eine Teilmenge der [Office 365-URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)und -IP-Adressbereiche, die mehr Tiefe bieten und immer auf dem neuesten Stand sind.
                    
 
|App |Ziel-FQDNs  |IP-Adressen  |Ports  |
|---|---------|---------|---------|
|**Skype-Besprechungs-App** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*Übertragen <span></span> von .officeapps.live.com <br/>\*<span></span>powerpoint.officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Diese IP-Adressen werden häufig aktualisiert.  Siehe [Skype for Business-IP-Bereiche](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie [Office-IP-Bereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Diese IP-Adressen werden häufig aktualisiert.  Siehe [Skype for Business-IP-Bereiche](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) sowie [Office-IP-Bereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)

[Bereitstellen von herunterladbaren Webclients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
