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
description: 'Zusammenfassung: Erfahren Sie mehr über die Integration von Skype for Business Server 2015 in Exchange und SharePoint.'
ms.openlocfilehash: 7e5303f5e47a2cfb017c893acbb63cce7e1521e7
ms.sourcegitcommit: d0fb9035903d9e1ce184417250913db10608b1a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2021
ms.locfileid: "53660763"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integration mit Exchange und Microsoft Office SharePoint Online

**Zusammenfassung:** Erfahren Sie mehr über Skype for Business Server 2015-Integration in Exchange und SharePoint.

Sie können Skype for Business Server 2015-Bereitstellungen für die Integration mit Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 und SharePoint Server konfigurieren, sowohl lokal als auch online. Die in der folgenden Tabelle aufgeführten Features werden mit allen Clients unterstützt, sofern nichts anderes angegeben ist. Weitere Informationen zur Clientunterstützung finden Sie unter [Desktop client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) and Skype for Business Online client comparison tables at Clients for Skype for Business [Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In den folgenden Tabellen sind die Features aufgeführt, die bei der Integration in Microsoft Exchange Server in einer Hybridbereitstellung unterstützt werden.

 **Skype for Business Server lokal und Exchange lokal**


|**Feature**|**Notizen**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter [Chat und Anwesenheit.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|Planen und Teilnehmen an Onlinebesprechung über Outlook  <br/> |Weitere Informationen finden Sie unter [Integrieren von Skype for Business Server 2015 in Exchange Server.](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Chat/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Konfigurieren einer Hybridumgebung in Skype for Business Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Planen und Teilnehmen an Onlinebesprechung über Outlook Web App  <br/> ||
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> |Weitere Informationen finden Sie unter [Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Veröffentlichungsstatus basierend auf Outlook Frei/Gebucht-Kalenderinformationen  <br/> ||
|Kontaktliste (über unified Contact Store)  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Ein Lync 2013- oder Skype for Business-Desktopclient ist erforderlich.  <br/>  Weitere Informationen finden Sie unter [Konfigurieren Skype for Business Server 2015 für die Verwendung des einheitlichen Kontaktspeichers.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Kontaktfoto in hoher Auflösung im Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Für Fotos in der Skype for Business-App für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter [Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)beschrieben eingerichtet werden. <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Der Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> ||
|Archivierung von Inhalten (Chat und Besprechung) in Exchange  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **lokale Skype for Business Server und Exchange Online**


|**Feature**|**Notizen**|
|:-----|:-----|
|Chat/Anwesenheit in Outlook  <br/> |Weitere Informationen finden Sie unter Konfigurieren der [Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planen und Teilnehmen an Onlinebesprechung über Outlook  <br/> ||
|Chat/Anwesenheit in Outlook Web App  <br/> |Weitere Informationen finden Sie unter Konfigurieren der [Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planen und Teilnehmen an Onlinebesprechung über Outlook Web App  <br/> |Weitere Informationen finden Sie unter Konfigurieren der [Integration zwischen lokalen Skype for Business Server 2015 und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechung in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend auf Outlook Frei/Gebucht-Kalenderinformationen  <br/> ||
|Kontaktliste (über unified Contact Store).  <br/> |Nur Lync Server 2013. Ein Lync 2013- oder Skype for Business-Desktopclient ist erforderlich.  <br/> Weitere Informationen finden Sie unter [Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Kontaktfoto in hoher Auflösung im Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Weitere Informationen finden Sie unter [Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Für Fotos in der Skype for Business-App für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter Konfigurieren der [Integration zwischen lokalen Skype for Business Server und Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md)beschrieben eingerichtet werden. <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Der Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Postfach des Benutzers Exchange geschrieben.  <br/> ||
|Archivierung von Inhalten (Chat und Besprechung) in Exchange  <br/> |Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Weitere Informationen finden Sie unter [Konfigurieren von Exchange für SharePoint eDiscovery Center.](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Bereitstellen von Lync Server 2013-Benutzer-Voicemail auf gehosteten Exchange UM.](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)  <br/> |


## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die Features aufgeführt, die bei der Integration in SharePoint in einer Hybridbereitstellung unterstützt werden.

||**SharePoint (lokal)**|**SharePoint Online**|
|:-----|:-----|:-----|
|**lokale Skype for Business Server 2015** <br/> | Suche nach Fähigkeiten <br/>  Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |
|**Skype for Business Online** <br/> | Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |
