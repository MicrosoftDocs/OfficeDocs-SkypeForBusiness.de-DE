---
title: Integration mit Exchange und Microsoft Office SharePoint Online
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Skype for Business Server 2015-Integration in Exchange und SharePoint.'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821105"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integration mit Exchange und Microsoft Office SharePoint Online

**Zusammenfassung:** Erfahren Sie mehr über die Skype for Business Server 2015-Integration in Exchange und SharePoint.

Sie können Skype for Business Server 2015-Bereitstellungen für die Integration in Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 und SharePoint Server sowohl lokal als auch online konfigurieren. Die in der folgenden Tabelle aufgeführten Features werden bei allen Clients unterstützt, sofern nicht anders angegeben. Weitere Informationen zur Clientunterstützung finden Sie in den Vergleichstabellen für Clientfeatures für [Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) und Skype for Business Online unter Clients for Skype for Business [Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In den folgenden Tabellen sind die Features aufgeführt, die in einer Hybridbereitstellung unterstützt werden, wenn sie in Microsoft Exchange Server.

 **Skype for Business Server lokal und Exchange lokal**


|**Funktion**|**Notizen**|
|:-----|:-----|
|Im/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter ["Im- und Anwesenheitsinformationen".](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Planen und Teilnehmen an Online besprechungen über Outlook  <br/> |Weitere Informationen finden Sie unter [Integrieren von Skype for Business Server 2015 in Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Im/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter ["Konfigurieren einer Hybridumgebung in Skype for Business Server 2015".](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Planen und Teilnehmen an Online besprechungen über Outlook Web App  <br/> ||
|Im/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> |Weitere Informationen finden Sie unter [Deploying Mobility](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Ein Lync 2013- oder Skype for Business-Desktopclient ist erforderlich.  <br/>  Weitere Informationen finden Sie unter ["Konfigurieren von Skype for Business Server 2015 für die Verwendung des einheitlichen Kontaktspeichers".](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Hochauflösendes Kontaktfoto in Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter "Konfigurieren der Verwendung von hochauflösenden Fotos [in Skype for Business Server 2015".](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Für Fotos in der Skype for Business-App für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server [beschrieben eingerichtet werden.](../deploy/integrate-with-exchange-server/configure-partner-applications.md) <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zu Hause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Archivieren von Inhalten (Im- und Besprechung) in Exchange  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype for Business Server lokal und Exchange Online**


|**Funktion**|**Notizen**|
|:-----|:-----|
|Im/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter "Konfigurieren der Integration [zwischen lokalem Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) und Outlook Web App" <br/> |
|Planen und Teilnehmen an Online besprechungen über Outlook  <br/> ||
|Im/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter "Konfigurieren der Integration [zwischen lokalem Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) und Outlook Web App" <br/> |
|Planen und Teilnehmen an Online besprechungen aus Outlook Web App  <br/> |Weitere Informationen finden Sie unter "Konfigurieren der Integration [zwischen lokalem Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) und Outlook Web App" <br/> |
|Im/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Online besprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher).  <br/> |Nur Lync Server 2013. Ein Lync 2013- oder Skype for Business-Desktopclient ist erforderlich.  <br/> Weitere Informationen finden Sie unter ["Konfigurieren von Skype for Business Server 2015 für die Verwendung des einheitlichen Kontaktspeichers"](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Hochauflösendes Kontaktfoto in Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Weitere Informationen finden Sie unter "Konfigurieren der Verwendung von hochauflösenden Fotos [in Skype for Business Server 2015".](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Für Fotos in der Skype for [Business-App](../deploy/integrate-with-exchange-server/outlook-web-app.md)für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter "Konfigurieren der Integration zwischen dem lokalen Skype for Business Server und Outlook Web App" beschrieben eingerichtet werden. <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zu Hause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Archivieren von Inhalten (Im- und Besprechung) in Exchange  <br/> |Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Weitere Informationen finden Sie unter ["Konfigurieren von Exchange für SharePoint eDiscovery Center"](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter ["Bereitstellen von Lync Server 2013-Benutzer-Voicemail in gehosteten Exchange UM".](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)  <br/> |

 **Skype for Business Online und Exchange lokal**


|**Funktion**|**Notizen**|
|:-----|:-----|
|Anwesenheit in Outlook  <br/> ||
|Antworten über Chat, PSTN-Anruf, Skype-Anruf oder Videoanruf über eine Outlook-E-Mail  <br/> ||
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Im/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Hochauflösendes Kontaktfoto in Lync 2013 oder Skype for Business-Client.  <br/> |Erfordert Exchange 2016 oder Exchange 2013. Dies wird in Lync Web App nicht unterstützt, wenn Benutzer in Skype for Business Online zu Hause sind.  <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zu Hause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Serverseitiger Unterhaltungsverlauf  <br/> ||

 **Skype for Business Online und Exchange Online**


|**Funktion**|**Notizen**|
|:-----|:-----|
|Im/Anwesenheit in Outlook  <br/> ||
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Im/Anwesenheit in Outlook Web App  <br/> ||
|Planen und Teilnehmen an Online besprechungen aus Outlook Web App  <br/> ||
|Im/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Online besprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Informationen im Outlook-Kalender  <br/> ||
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Lync Server 2013- oder Skype for Business-Client erforderlich  <br/> |
|Kontaktfoto in hoher Auflösung in Lync 2013, Skype for Business-Client und Lync Web App  <br/> ||
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zu Hause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Archivieren von Inhalten (Im- und Besprechung) in Exchange  <br/> ||
|Durchsuchen archivierter Inhalte  <br/> ||
|Voicemail  <br/> ||

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die Features aufgeführt, die bei der Integration in SharePoint in eine Hybridbereitstellung unterstützt werden.

||**SharePoint (lokal)**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 lokal** <br/> | Qualifikationssuche <br/>  Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |
|**Skype for Business Online** <br/> | Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |


