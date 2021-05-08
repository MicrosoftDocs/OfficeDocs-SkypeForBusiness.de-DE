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
description: 'Summary: Learn about Skype for Business Server 2015 integration with Exchange and SharePoint.'
ms.openlocfilehash: f8d57924d3a82effbc552de660b973aa36e7b8fe
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236991"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integration mit Exchange und Microsoft Office SharePoint Online

**Zusammenfassung:** Erfahren Sie mehr Skype for Business Server 2015-Integration in Exchange und SharePoint.

Sie können Skype for Business Server 2015-Bereitstellungen für die Integration in Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 und SharePoint Server sowohl lokal als auch online konfigurieren. Die in der folgenden Tabelle aufgeführten Features werden mit allen Clients unterstützt, sofern nichts anderes angegeben ist. Weitere Informationen zur Clientunterstützung finden Sie unter [Desktop client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) and Skype for Business Online client comparison tables at Clients for Skype for Business [Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In den folgenden Tabellen sind die Features aufgeführt, die in einer Hybridbereitstellung unterstützt werden, wenn sie in Microsoft Exchange Server.

 **Skype for Business Server lokal und Exchange lokal**


|**Feature**|**Notizen**|
|:-----|:-----|
|Im-/Anwesenheits Outlook  <br/> |Weitere Informationen finden Sie unter [Im- und Anwesenheitsinformationen.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|Planen und Teilnehmen an Online-Besprechungen Outlook  <br/> |Weitere Informationen finden Sie unter [Integrate Skype for Business Server 2015 with Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Im-/Anwesenheits Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Configure a hybrid environment in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planen und Teilnehmen an Online-Besprechungen über Outlook Web App  <br/> ||
|Im-/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> |Weitere Informationen finden Sie unter [Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Veröffentlichungsstatus basierend Outlook Frei/Gebucht-Informationen im Kalender  <br/> ||
|Kontaktliste (über Unified Contact Store)  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Ein Lync 2013- oder Skype for Business Desktopclient ist erforderlich.  <br/>  Weitere Informationen finden Sie unter [Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Hochauflösendes Kontaktfoto in Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos in der Skype for Business-App für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter [Configure partner applications in Skype for Business Server and Exchange Server beschrieben eingerichtet werden.](../deploy/integrate-with-exchange-server/configure-partner-applications.md) <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zuhause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben  <br/> ||
|Archivierungsinhalte (Im- und Besprechungsinhalte) in Exchange  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Erfordert Exchange 2016 oder Exchange 2013.  <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype for Business Server lokal und Exchange Online**


|**Feature**|**Notizen**|
|:-----|:-----|
|Im-/Anwesenheits Outlook  <br/> |Weitere Informationen finden Sie unter [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planen und Teilnehmen an Online-Besprechungen Outlook  <br/> ||
|Im-/Anwesenheits Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planen und Teilnehmen an Online-Besprechungen Outlook Web App  <br/> |Weitere Informationen finden Sie unter [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Im-/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Online-Besprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend Outlook Frei/Gebucht-Informationen im Kalender  <br/> ||
|Kontaktliste (über Unified Contact Store).  <br/> |Nur Lync Server 2013. Ein Lync 2013- oder Skype for Business Desktopclient ist erforderlich.  <br/> Weitere Informationen finden Sie unter [Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Hochauflösendes Kontaktfoto in Lync 2013-Client, Skype for Business-Client und Lync Web App.  <br/> |Weitere Informationen finden Sie unter [Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Für Fotos in der Skype for Business-App für MAC und Mobile muss die Integration zwischen Skype for Business Server 2015 und Exchange Server wie unter [Configure integration between on-premises Skype for Business Server and Outlook Web App beschrieben eingerichtet werden.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zuhause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Postfach des Benutzers Exchange geschrieben  <br/> ||
|Archivierungsinhalte (Im- und Besprechungsinhalte) in Exchange  <br/> |Weitere Informationen finden Sie unter [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Weitere Informationen finden Sie unter [Configure Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Voicemail  <br/> |Weitere Informationen finden Sie unter [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um).  <br/> |

 **Skype for Business Online und Exchange lokal**


|**Feature**|**Notizen**|
|:-----|:-----|
|Anwesenheit in Outlook  <br/> ||
|Antworten über Sofort-, PSTN-, Skype- oder Videoanruf über eine Outlook E-Mail  <br/> ||
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Im-/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend Outlook Frei/Gebucht-Informationen im Kalender  <br/> ||
|Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben  <br/> ||
|Hochauflösendes Kontaktfoto in Lync 2013 oder Skype for Business Client.  <br/> |Erfordert Exchange 2016 oder Exchange 2013. Dies wird in Lync Web App nicht unterstützt, wenn Benutzer in Skype for Business online Skype for Business werden.  <br/> |
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zuhause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Postfach des Benutzers Exchange geschrieben  <br/> ||
|Serverseitiger Unterhaltungsverlauf  <br/> ||

 **Skype for Business Online und Exchange Online**


|**Feature**|**Notizen**|
|:-----|:-----|
|Im-/Anwesenheits Outlook  <br/> ||
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> ||
|Im-/Anwesenheits Outlook Web App  <br/> ||
|Planen und Teilnehmen an Online-Besprechungen Outlook Web App  <br/> ||
|Im-/Anwesenheit in mobilen Clients  <br/> ||
|Teilnehmen an Online-Besprechungen in mobilen Clients  <br/> ||
|Veröffentlichungsstatus basierend Outlook Frei/Gebucht-Informationen im Kalender  <br/> ||
|Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben  <br/> ||
|Kontaktliste (über Unified Contact Store)  <br/> |Lync Server 2013 oder Skype for Business erforderlich  <br/> |
|Hochauflösendes Kontaktfoto in Lync 2013, Skype for Business und Lync Web App  <br/> ||
|Besprechungsdelegierung  <br/> |Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder beide lokal zuhause sind. Weitere Informationen finden Sie unter [Skype for Business Hybridlösungen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Archivierungsinhalte (Im- und Besprechungsinhalte) in Exchange  <br/> ||
|Durchsuchen archivierter Inhalte  <br/> ||
|Voicemail  <br/> ||

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die Features aufgeführt, die in einer Hybridbereitstellung unterstützt werden, wenn sie in die SharePoint.

||**SharePoint (lokal)**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 lokal** <br/> | Kompetenzsuche <br/>  Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |
|**Skype for Business Online** <br/> | Anwesenheit in SharePoint <br/> | Anwesenheit in SharePoint <br/> |