---
title: Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Zusammenfassung: Informationen für Organisationen, die nicht verwenden von Office 365 und Besprechungen von Organisationen, die gehosteten zugreifen müssen.'
ms.openlocfilehash: 53e4bd52242faa62a14b39474f1859064afcdb43
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882656"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Mindestnetzwerkanforderungen für die Skype-Besprechungs-App
 
**Zusammenfassung:**  Informationen für Organisationen, die nicht verwenden von Office 365 und Besprechungen von Organisationen, die gehosteten zugreifen müssen. In diesem Artikel ist nicht für die Benutzer über diese apps vorgesehen.
  
Damit Benutzer Skype Besprechungen App zum Teilnehmen an Besprechungen in Skype für Business Online gehostet verwenden können, sollten Netzwerkadministratoren Organisationen, die nicht Office 365 verwenden weißen oder andernfalls die FQDNs sowie die IP-Adressen und Ports unten aufgeführten zur Verfügung stellen.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Anforderungen für Konnektivität mit der Skype-Besprechungs-App

Die hier aufgeführte Informationen ist eine Teilmenge von [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), die bietet Einzelheiten und wird immer die am häufigsten auf dem aktuellen Stand sein.
                    
 
|App |Ziel-FQDNs  |IP-Adressen  |Ports  |
|---|---------|---------|---------|
|**Skype-Besprechungs-App** | \*. Lync.com herzustellen <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Übertragung<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s microsoft.com<br/>        |   Diese IP-Adressen werden häufig aktualisiert.  Finden Sie unter [Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) als auch [Office Online IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478–3481<br/>
|**Microsoft Teams**    | \*<span></span>. Microsoft.com (engl.) <br/>\*<span></span>. skype.com | Diese IP-Adressen werden häufig aktualisiert.  Finden Sie unter [Skype für Business IP-Adressbereichen](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) als auch [Office Online IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478–3481

## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="BKMK_Conferencing"> </a>

[Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md)

[Bereitstellen Sie herunterladbare Webclients in Skype für Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype Besprechungen App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)