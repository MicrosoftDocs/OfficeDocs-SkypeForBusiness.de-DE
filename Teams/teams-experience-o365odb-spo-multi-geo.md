---
title: Teamerfahrung in einer Microsoft 365 Multi-Geo-fähigen Umgebung
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
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760538"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Erfahrungen mit Teams in einem Microsoft 365 Multi-Geo-fähigen Tenancy

Microsoft Teams ist eine Gruppenchatsoftware, der Hub für Teamarbeit in Microsoft 365 und Office 365. Es wird vom Microsoft 365-Gruppendienst zusammen mit SharePoint Online und OneDrive for Business für die Dateierfahrung unterstützt. In einem OneDrive for Business/SharePoint Online Multi-Geo-Mandanten, in dem der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien erweitert wird, ist die zugrunde liegende Dateierfahrung multi-geobewusst, daher ist die Erfahrung von Teams mit der Dateizusammenarbeit auch multi-geobewusst. Diese Funktionalität ist eine wichtige Spitzenfunktion für Teams, um Dateien, die in der systemeigenen Dateioberfläche über mehrere Geos gehostet werden, zu beoberflächen. Dazu gehören auch OneNote- und Wiki-Dateien.

In einem Contoso-Mandanten mit Europa als Satelliten geo und Nordamerika als zentralem Geo wird einem europäischen Satellitenbenutzer die #A0 unter der Registerkarte Dateien im linken Bereich angezeigt, obwohl die Dateien am Datenspeicherort Europa gehostet werden und die USA der zentrale Standort des Mandanten sind.  Außerdem kann der Benutzer unter dem Blatt Zuletzt verwendete Ansicht auf die zuletzt **verwendeten** Dateien zugreifen. Zuletzt verwendeten Dateien können Dateien enthalten, die von Benutzern an anderen Geostandorten freigegeben wurden. 

Die SharePoint-Website eines bestimmten Teams ist auch multi-geo-bewusst. Wenn also ein europäischer Satellitenbenutzer ein Team erstellt, wird die entsprechende SharePoint-Website am Standort Europa erstellt. Die Dateien, die diesem Team zugeordnet sind, werden an diesem Speicherort in Ruhe gehalten. Alle nachfolgenden Erfahrungen, z. B. das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden an diesem europäischen Speicherort gespeichert, um die Zusage der Datenresidenz für diese Dateien zu erhalten.

Da ein Multi-Geo-Mandanten ein einzelner globaler Mandant ist, können Satellitenbenutzer während @Erwähnungen ihre Kollegen aus der ganzen Welt sehen, ganz gleich, wo sie sich gerade befinden.

Unterhaltungen in Chats, Kanälen und Besprechungsnotizen/Chats innerhalb der Teams-Erfahrung sind nicht multi-Geo-bewusst und werden alle nur innerhalb des zentralen Speicherorts des Mandanten aufbewahrt. In der Regel werden Chatunterhaltungen nicht auf Anforderungen an die Datenresidenz angewendet. Weitere Informationen finden Sie unter [Speicherort von Daten in Microsoft Teams](location-of-data-in-teams.md).

Die Multi-Geo-Unterstützung für Teams steht auf der [Microsoft 365-Roadmap.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Weitere Informationen zu Multi-Geo finden Sie auf der [Seite Microsoft Multi-Geo-Funktionen.](https://aka.ms/multi-geo)
