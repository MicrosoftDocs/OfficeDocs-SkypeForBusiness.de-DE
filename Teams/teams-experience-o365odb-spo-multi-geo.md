---
title: Teams umgebung in einer Microsoft 365 mit mehreren geofähigen Umgebungen
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
description: In diesem Artikel erfahren Sie mehr über die Verwendung von Teams in einer Microsoft 365 mit mehreren geofähigen Umgebungen.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760538"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams erfahrung in einem Microsoft 365 mit mehreren geofähigen Mandrechten

Microsoft Teams ist Gruppenchatsoftware, der Hub für Teamarbeit in Microsoft 365 und Office 365. Es wird vom Dienst "Microsoft 365 Groups" sowie SharePoint Online und OneDrive for Business die Dateierfahrung unterstützt. In einem OneDrive for Business/SharePoint Online Multi-Geo-Mandanten, bei dem der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien erweitert wird, ist die zugrunde liegende Dateierfahrung multige geobewusst, daher ist die Teams-Erfahrung bei der Dateizusammenarbeit auch multige geobewusst. Diese Funktionalität ist eine wichtige Funktion am oberen Rand, um Teams, die in der systemeigenen Dateioberfläche auf mehreren Geos gehostet werden, bereitzustellen. Dies schließt auch OneNote- und Wiki-Dateien ein.

In einem Contoso-Mandanten mit Europa als Satelliten-Geo und Nordamerika als zentraler Geo kann ein benutzer eines  europäischen Satelliten die OneDrive-Dateien auf der Registerkarte Dateien im linken Bereich sehen, obwohl die Dateien am Datenspeicherort "Europa" gehostet werden und die USA der zentrale Standort des Mandanten sind. Außerdem kann der Benutzer unter dem Blatt "Zuletzt verwendet" auf die zuletzt **verwendeten** Dateien zugreifen. Die zuletzt verwendeten Dateien können Dateien enthalten, die von Benutzern an anderen Geostandorten freigegeben wurden. 

Die Teamwebsite eines bestimmten SharePoint ist ebenfalls geobewusst. Wenn also ein Benutzer eines europäischen Satelliten ein Team erstellt, wird die entsprechende SharePoint am Standort Europa erstellt. Die diesem Team zugeordneten Dateien werden an diesem Speicherort gespeichert. Alle nachfolgenden Erfahrungen, z. B. das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden an diesem europäischen Speicherort gespeichert und halten die Zusage zur Datenspeicherung für diese Dateien ein.

Da es sich bei einem Mandanten mit mehreren Geo-Geos um einen einzigen globalen Mandanten handelt, können Satellitenbenutzer während @Erwähnungen ihre Kollegen auf der ganzen Welt sehen, ganz gleich, wo sie sich gerade befinden.

Unterhaltungen in Chats, Kanälen und Besprechungs-Chatnotizen/-chats innerhalb der Teams-Benutzererfahrung sind nicht geobewusst und werden alle nur innerhalb der zentralen Position des Mandanten gehalten. Chatunterhaltungen werden in der Regel nicht auf Anforderungen an die Datenspeicherung angewendet. Weitere Informationen finden Sie unter [Speicherort von Daten in Microsoft Teams.](location-of-data-in-teams.md)

Multi-Geo-Unterstützung für Teams steht in der Roadmap [Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Weitere Informationen zu Multi-Geo finden Sie auf der [Seite mit Microsoft Multi-Geo-Funktionen.](https://aka.ms/multi-geo)
