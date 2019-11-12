---
title: Integration mit Exchange und SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Zusammenfassung: erfahren Sie mehr über die Integration von Skype for Business Server 2015 in Exchange und SharePoint.'
ms.openlocfilehash: 18839125faee2dfd27ad3843e37b723f56581ff3
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231146"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integration mit Exchange und SharePoint

**Zusammenfassung:** Erfahren Sie mehr über die Integration von Skype for Business Server 2015 in Exchange und SharePoint.

Sie können die Bereitstellung von Skype for Business Server 2015 für die Integration mit Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 und SharePoint Server sowohl lokal als auch Online konfigurieren. Falls nicht anders angegeben, werden die in der folgenden Tabelle aufgeführten Funktionen von allen Clients unterstützt. Weitere Informationen zum Client-Support finden Sie unter [Vergleich der Desktop-Client-Features für Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) -und Skype for Business Online-Client Vergleichstabellen bei [Clients für Skype for Business Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In den folgenden Tabellen sind die Features aufgeführt, die in einer hybridbereitstellung unterstützt werden, wenn Sie in Microsoft Exchange Server integriert sind.

 **Skype for Business Server lokal und Exchange lokal**


|**Feature**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter [Chat und Anwesenheits](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)Informationen.  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |Weitere Informationen finden Sie unter [integrieren von Skype for Business Server 2015 mit Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Chat/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren einer Hybridumgebung in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planen und teilnehmen an Onlinebesprechungen über Outlook Web App  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von Mobilität](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Ein lync 2013-oder Skype for Business-Desktop Client ist erforderlich.  <br/>  Weitere Informationen finden Sie unter [Konfigurieren von Skype for Business Server 2015 für die Verwendung des einheitlichen Kontaktspeichers](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Kontakt Foto mit hoher Auflösung in lync 2013-Client, Skype for Business-Client und lync Web App.  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos in der Skype for Business-App für Mac und Handy muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter [Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)beschrieben eingerichtet sein. <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype for Business-Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Bereitstellungscheckliste für die Archivierung](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von lokalen Exchange um für die Bereitstellung von lync Server 2013-Voicemail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype for Business-Server lokal und Exchange Online**


|**Feature**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) . <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Chat/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) . <br/> |
|Planen und teilnehmen an einer Onlinebesprechung in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) . <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher).  <br/> |Nur lync Server 2013 Ein lync 2013-oder Skype for Business-Desktop Client ist erforderlich.  <br/> Weitere Informationen finden Sie unter [Konfigurieren von Skype for Business Server 2015 für die Verwendung des einheitlichen Kontaktspeichers](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) . <br/> |
|Kontakt Foto mit hoher Auflösung in lync 2013-Client, Skype for Business-Client und lync Web App.  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos in der Skype for Business-App für Mac und Handy muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter [Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md)eingerichtet werden. <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype for Business-Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Protokoll für verpasste Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben  <br/> ||
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |Weitere Informationen finden Sie unter [Bereitstellungscheckliste für die Archivierung](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |Weitere Informationen finden Sie unter [Konfigurieren von Exchange für SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) . <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von lync Server 2013-Benutzern für Voicemail in Hosted Exchange um](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype for Business Online und Exchange lokal**


|**Feature**|**Hinweise**|
|:-----|:-----|
|Anwesenheit in Outlook  <br/> ||
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer Outlook-E-Mail heraus  <br/> ||
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Kontakt Foto mit hoher Auflösung in lync 2013 oder Skype for Business-Client.  <br/> |Erfordert Exchange 2016 oder Exchange 2013. Dies wird in lync Web App nicht unterstützt, wenn Benutzer in Skype for Business Online verwaltet werden.  <br/> |
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype for Business-Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Protokoll für verpasste Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben  <br/> ||
|Serverseitig aufgezeichnete Unterhaltungen  <br/> ||

 **Skype for Business Online und Exchange Online**


|**Feature**|**Hinweise**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> ||
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Chat/Anwesenheit in Outlook Web App  <br/> ||
|Planen und teilnehmen an einer Onlinebesprechung in Outlook Web App  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Lync Server 2013 oder Skype for Business-Client erforderlich  <br/> |
|Foto mit hoher Auflösung in lync 2013, Skype for Business-Client und lync Web App  <br/> ||
|Besprechungsdelegation  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden. Weitere Informationen finden Sie unter [Skype for Business-Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> ||
|Durchsuchen von archivierten Inhalten  <br/> ||
|Voicemail  <br/> ||

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die in einer hybridbereitstellung unterstützten Features aufgeführt, wenn Sie in SharePoint integriert sind.

||**Lokales SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 lokal** <br/> | Qualifikationssuche <br/>  Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |
|**Skype for Business Online** <br/> | Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |


