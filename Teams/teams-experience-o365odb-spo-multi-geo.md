---
title: Teams-Umgebung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-fähigen Mandanteneinheit
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Erfahren Sie mehr über die Verwendung von Teams in einer Office 365 OneDrive-und SharePoint Online-Multi-Geo-fähigen Mietdauer.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf2fac5249f2267c7813c1ba12aade279da094f3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570234"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Teams-Umgebung in einer Office 365 OneDrive und SharePoint Online Multi-Geo-fähigen Mandanteneinheit
===========================================

Microsoft Teams ist eine Gruppen-Chat-Software, der Hub für Teamarbeit in Office 365. Sie wird vom Office 365 Groups-Dienst zusammen mit SharePoint Online und OneDrive for Business für die Dateinutzung unterstützt. In einer OneDrive for Business/SharePoint Online-Multi-Geo-Mietdauer, in der der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien ausgeweitet wird, ist die zugrunde liegende Datei Erfahrung Multi-Geo-bewusst, sodass die Teams mit Datei vertraut sind. die Zusammenarbeit ist auch Multi-Geo-fähig. Hierbei handelt es sich um eine der wichtigsten Spitzenfunktionen für Teams, um Dateien, die über mehrere GEOSS gehostet werden, in der nativen Datei Oberfläche zu beleben.

In einer contoso-Mietdauer mit Europa als Satelliten Geo und Nordamerika als zentrales Geo sieht ein europäischer Satelliten Benutzer beispielsweise seine OneDrive-Dateien im linken Bereich unter der Registerkarte "Dateien", obwohl die Dateien im Europa-Datenspeicherort und im United stat gehostet werden. Es ist der zentrale Standort des Mandanten. Darüber hinaus kann der Benutzer auf die zuletzt verwendeten Dateien unter dem Blade für zuletzt verwendete Ansichten zugreifen. Aktuelle Dateien enthalten möglicherweise Dateien, die für den Benutzer von Benutzern in anderen GEOS freigegeben wurden, und möglicherweise an anderen geografischen Standorten, auf die der Mandant erweitert wird. 

Die Gruppen Website eines bestimmten Teams ist auch Multi-Geo-fähig. Das heißt, wenn ein europäischer Satelliten Benutzer ein Team erstellt, wird die entsprechende Gruppen Website am Standort Europa erstellt, und die Dateien, die dieser Team Gruppe zugeordnet sind, werden an diesem Speicherort beibehalten. Alle nachfolgenden Erfahrungen, wie das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden auf diesen europäischen Standort ausgerichtet, wobei das Versprechen einer Daten Residency für diese Dateien bleibt. Dies ist möglich, wenn die zugrunde liegenden Foundation Office 365-Gruppen multigeo-fähig werden.

Da es sich bei einer Multi-Geo-Mietdauer um einen einzigen globalen Mandanten handelt, können die Satelliten Nutzer während der @ Erwähnungen Ihre Kollegen aus der ganzen Welt sehen – ganz gleich, wo Sie sich befinden. 

Beachten Sie, dass Unterhaltungen in Chats und Besprechungsnotizen innerhalb der Teams nicht multigeo-fähig sind und alle nur innerhalb des zentralen Standorts des Mandanten aufbewahrt werden. In der Regel werden Chat Unterhaltungen nicht auf die Anforderungen von Daten Wohnsitz angewendet.

Weitere Informationen zu Office 365 Multi-Geo finden Sie auf der [Seite Microsoft Multi-Geo-Funktionen](https://aka.ms/multi-geo).