---
title: Teams in einer Microsoft 365 Multi-Geo-fähigen Umgebung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: In diesem Artikel erfahren Sie mehr über die Verwendung von Teams in einer Microsoft 365 Multi-Geo-fähigen Umgebung.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122245"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams in einem Microsoft 365 Multi-Geo-fähigen Tenancy

Microsoft Teams ist Die Software für Gruppenchats ist der Hub für Teamarbeit in Microsoft 365 und Office 365. Es wird vom Microsoft 365-Gruppendienst zusammen mit SharePoint Online und OneDrive for Business unterstützt, um die Dateierfahrung zu verbessern. In einem Multi-Geo-Mandanten von OneDrive for Business/SharePoint Online, in dem der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien erweitert wird, ist die zugrunde liegende Dateierfahrung multige geobewusst, daher ist die #A0 mit Dateizusammenarbeit auch multige geobewusst. Diese Funktionalität ist eine wichtige Funktion am oberen Rand für Teams, um Dateien, die in der systemeigenen Dateioberfläche über mehrere Geos hinweg gehostet werden, bereitzustellen. Dies schließt auch OneNote- und Wiki-Dateien ein.

In einem Mandanten von Contoso, in dem Europa als Satelliten-Geo und Nordamerika als zentraler #A0  verwendet wird, werden einem europäischen Satellitenbenutzer seine #A1 auf der Registerkarte "Dateien" im linken Bereich angezeigt, obwohl die Dateien am #A2 gehostet werden und die VEREINIGTEn Staaten der zentrale Standort des Mandanten sind. Außerdem kann der Benutzer unter dem Blatt "Zuletzt verwendete Ansicht" auf die zuletzt **verwendeten** Dateien zugreifen. Die zuletzt verwendeten Dateien können Dateien enthalten, die von Benutzern an anderen Geostandorten freigegeben wurden. 

Die SharePoint-Website eines bestimmten Teams ist ebenfalls geobewusst. Das heißt, wenn ein benutzer eines europäischen Satelliten ein Team erstellt, wird die entsprechende SharePoint-Website am Standort Europa erstellt. Die Dateien, die diesem Team zugeordnet sind, werden an diesem Speicherort gespeichert. Alle nachfolgenden Erfahrungen, z. B. das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden an diesem europäischen Speicherort gespeichert, und es wird die Zusage zur Datenspeicherung für diese Dateien eingehalten.

Da ein Multi-Geo-Mandanten ein einzelner globaler Mandant ist, können Satellitenbenutzer während @Erwähnungen ihre Kollegen auf der ganzen Welt sehen, ganz gleich, wo sie sich gerade befinden.

Unterhaltungen in Chats, Kanalnachrichten und Besprechungsnotizen/Chats innerhalb der Teamerfahrung sind nicht geobewusst und werden alle nur innerhalb des zentralen Standorts des Mandanten aufbewahrt. Chatunterhaltungen werden in der Regel nicht auf Anforderungen an die Datenspeicherung angewendet. Weitere Informationen finden Sie unter ["Speicherort der Daten in Microsoft Teams".](location-of-data-in-teams.md)

Weitere Informationen zu Multi-Geo finden Sie auf der [Seite "Microsoft Multi-Geo-Funktionen".](https://aka.ms/multi-geo)
