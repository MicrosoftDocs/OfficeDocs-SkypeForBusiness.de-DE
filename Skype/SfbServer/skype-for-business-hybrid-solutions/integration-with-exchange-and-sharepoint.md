---
title: Integration mit Exchange und SharePoint
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Zusammenfassung: Informationen Sie zu Skype für die Integration mit Exchange und SharePoint Business Server 2015.'
ms.openlocfilehash: 91291f960636b8fd0c41519ff65830b98b631e8c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227936"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integration mit Exchange und SharePoint

**Zusammenfassung:** Informationen Sie zu Skype für Business Server 2015 Integration mit Exchange und SharePoint.

Konfigurieren von Skype für Business Server 2015 Bereitstellungen für die Integration mit Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 und SharePoint Server lokal und online. Falls nicht anders angegeben, werden die in der folgenden Tabelle aufgeführten Funktionen von allen Clients unterstützt. Weitere Informationen zu Client unterstützt, finden Sie unter [Desktopclient Featurevergleich für Skype für Unternehmen](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) und Skype clientvergleichstabellen Clients [für Skype für Business Online](https://go.microsoft.com/fwlink/p/?LinkId=281902)Business Online.

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In den folgenden Tabellen aufgelistet, die in einer hybridbereitstellung bei Microsoft Exchange Server integriert unterstützten Features.

 **Skype für Business Server lokal und Exchange lokal**


|**Funktion**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter [Sofortnachrichten und Anwesenheit](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |Weitere Informationen finden Sie unter [Skype für Business Server 2015 mit Exchange Server zu integrieren](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Sofortnachrichten/Anwesenheitsinformationen in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren einer hybridumgebung in Skype für Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Zeitplan und Join online-Besprechung über Outlook Web App  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von Mobilität](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Ein Lync 2013 oder Skype für Business desktop Client ist erforderlich.  <br/>  Weitere Informationen finden Sie unter [Konfigurieren von Skype für Business Server 2015 einheitlichen Kontaktspeicher verwenden](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Hochauflösende Foto des Kontakts in Lync 2013-Client, Skype für Business-Client und Lync Web App.  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von hoch auflösenden Fotos in Skype für Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos auf die Skype für Geschäfts-app für MAC und Mobile muss Integration zwischen Skype für Business Server 2015 und Exchange Server eingerichtet werden, wie unter [Konfigurieren von partneranwendungen in Skype für Business Server und Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)beschrieben. <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype für Business hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Prüfliste für die Bereitstellung für die Archivierung](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von lokalen Exchange UM für Lync Server 2013-Voicemail bereitstellen](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype für Business Server lokal und Exchange Online**


|**Funktion**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Sofortnachrichten/Anwesenheitsinformationen in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Zeitplan und Join onlinebesprechung aus Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher).  <br/> |Nur Lync Server 2013. Ein Lync 2013 oder Skype für Business desktop Client ist erforderlich.  <br/> Weitere Informationen finden Sie unter [Konfigurieren von Skype für Business Server 2015 einheitlichen Kontaktspeicher verwenden](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Hochauflösende Foto des Kontakts in Lync 2013-Client, Skype für Business-Client und Lync Web App.  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von hoch auflösenden Fotos in Skype für Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos auf die Skype für Geschäfts-app für MAC und Mobile muss Integration zwischen Skype für Business Server 2015 und Exchange Server eingerichtet werden, wie in [Configure Integration zwischen lokalen Skype für Business Server und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md)beschrieben. <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype für Business hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Verpasste Unterhaltungsverlauf und Anrufprotokolle werden in Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |Weitere Informationen finden Sie unter [Prüfliste für die Bereitstellung für die Archivierung](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |Weitere Informationen finden Sie unter [Konfigurieren von Exchange für SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von Lync Server 2013 Voicemail für Benutzer auf Hosted Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype für Business Online und Exchange lokal**


|**Funktion**|**Hinweise**|
|:-----|:-----|
|Anwesenheit in Outlook  <br/> ||
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer Outlook-E-Mail heraus  <br/> ||
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Hochauflösende Foto des Kontakts in Lync 2013 oder Skype für Business-Client.  <br/> |Erfordert Exchange 2016 oder Exchange 2013. Dies ist in Lync Web App nicht unterstützt, wenn Benutzer auf Skype für Business Online verwaltet werden.  <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype für Business hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Verpasste Unterhaltungsverlauf und Anrufprotokolle werden in Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Serverseitig aufgezeichnete Unterhaltungen  <br/> ||

 **Skype für Unternehmen Online und Exchange Online**


|**Funktion**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> ||
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Sofortnachrichten/Anwesenheitsinformationen in Outlook Web App  <br/> ||
|Zeitplan und Join onlinebesprechung aus Outlook Web App  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Lync Server 2013 oder Skype für Business Client erforderlich  <br/> |
|Hochauflösende Foto des Kontakts in Lync 2013, Skype für Business-Client und Lync Web App  <br/> ||
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype für Business hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> ||
|Durchsuchen von archivierten Inhalten  <br/> ||
|Voicemail  <br/> ||

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

Die folgende Tabelle enthält die Features, die in einer hybridbereitstellung bei der Integration in SharePoint unterstützt.

||**SharePoint lokal**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype für Business Server 2015 lokalen** <br/> | Qualifikationssuche <br/>  Anwesenheitsinformationen in SharePoint <br/> | Anwesenheitsinformationen in SharePoint <br/> |
|**Skype for Business Online** <br/> | Anwesenheitsinformationen in SharePoint <br/> | Anwesenheitsinformationen in SharePoint <br/> |


