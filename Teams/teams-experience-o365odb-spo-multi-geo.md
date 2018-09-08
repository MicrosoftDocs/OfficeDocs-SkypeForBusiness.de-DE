---
title: Teams Erfahrung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-enabled-Instanz
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Informationen Sie zum Verwenden von Teams in einer Office 365 OneDrive und SharePoint Online Multi-Geo-enabled-Instanz.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68e3acc139894f98ec2d13e0c3e7bc3ec30042f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882944"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Teams Erfahrung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-enabled-Instanz
===========================================

Microsoft-Teams ist Group Chat Software, den Hub für die Zusammenarbeit in Office 365. Es wird von der Gruppen von Office 365-Dienst zusammen mit SharePoint Online und OneDrive für Unternehmen für ihre Dateien Erfahrung bereitgestellt. In einer OneDrive for Business/SharePoint Online Multi-Geo-Instanz, in dem der Mandant auf viele geografische Standorte hinweg wie Nordamerika und Europa Australien, erweitert wird bildet die zugrunde liegenden Dateien Multi-Geo beachten, damit die Teams bei Datei auftreten Zusammenarbeit ist auch Multi-Geo berücksichtigen. Dies spielt eine wichtige führender für Teams Fläche Dateien über mehrere Geos in ihre Erfahrung systemeigene Dateien gehostet.

Beispielsweise eines Mandanten "Contoso" mit Europa als eine Satelliten Geo und Nordamerika als die zentralen Geo sieht ein Benutzers Europäischen Satelliten seinem OneDrive-Dateien im linken Bereich auf der Registerkarte Dateien zwar die Dateien in den Speicherort der Europa und der Stat United gehostet werden Es ist die zentrale Stelle des Mandanten. Darüber hinaus kann der Benutzer die zuletzt geöffneten Dateien unter der aktuellen Ansicht Blade zugreifen. Zuletzt verwendeten Dateien enthalten möglicherweise mit dem Benutzer von Benutzern in anderen Geos freigegebenen Dateien und möglicherweise in anderen Geo-Standorte, denen der Mandanten auf erweitert wird gesteuert werden. 

Ein bestimmtes Team Gruppe Website ist auch Multi-Geo berücksichtigen. D. h., wenn ein Benutzer Europäischen Satelliten ein Team erstellt, die entsprechende Website Gruppen in Europa Speicherort erstellt werden und die Dateien zugeordnet, dass Team Gruppe im Ruhezustand an diesem Speicherort gespeichert werden. Alle nachfolgenden Erfahrungen, wie eine neue Datei hochladen oder Bearbeiten der Datei werden auf diesen Europäischen Speicherort, halten umfassende Daten vor-Ort-Dateien verwendet werden. Dies wird alle von der zugrunde liegenden Foundation Office 365 Gruppen zunehmend Multi-Geo-fähigen ermöglicht.

Da Multi-Geo-Instanz eine einzelne globale Mandanten ist, werden während @ erwähnungen Satelliten Benutzer Lage zu sehen ihre Kollegen in der ganzen Welt, unabhängig davon, wo sie sich befinden. 

Beachten Sie, dass Unterhaltungen in Chats und Instant Messaging-Besprechungsnotizen innerhalb des Teams den Endbenutzer nicht Multi-Geo bewusst sind und alle werden gespeichert nur innerhalb der zentralen Speicherort des Mandanten. Chat Unterhaltungen werden nicht in der Regel auf Daten vor-Ort-Anforderungen angewendet.

Weitere Informationen zu Office 365 Multi-Geo finden Sie auf der [Microsoft Multi-Geo Funktionen Seite](https://aka.ms/multi-geo).