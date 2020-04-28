---
title: Teams in einer Microsoft 365-oder Office 365 OneDrive-und SharePoint Online-Umgebung mit mehreren geografischen Funktionen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: In diesem Artikel erfahren Sie mehr über die Verwendung von Teams in einer Microsoft 365-oder Office 365 OneDrive-und SharePoint Online-mandantenfähigen Mandantenfähigkeit.
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
ms.openlocfilehash: 4e754177de6f08476c9160254f2334f6f3ac18d3
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903140"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Teams in einer Microsoft 365-oder Office 365 OneDrive-und SharePoint Online-Umgebung mit mehreren geografischen Funktionen
===========================================

Microsoft Teams ist eine Gruppen-Chat-Software, der Hub für Teamarbeit in Office 365. Sie wird vom Microsoft 365 Groups-Dienst zusammen mit SharePoint Online und OneDrive for Business für die Dateinutzung bereitgestellt. In einer OneDrive for Business/SharePoint Online-Multi-Geo-Mietdauer, in der der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien ausgeweitet wird, ist die zugrunde liegende Datei Erfahrung Multi-Geo-bewusst, daher ist die Team Erfahrung mit der Datei Zusammenarbeit auch Multi-Geo-fähig. Hierbei handelt es sich um eine der wichtigsten Spitzenfunktionen für Teams, um Dateien, die über mehrere GEOSS gehostet werden, in der nativen Datei Oberfläche zu beleben.

In einer contoso-Mietdauer mit Europa als Satelliten Geo und Nordamerika als zentrales Geo sieht ein europäischer Satelliten Benutzer beispielsweise seine OneDrive-Dateien im linken Bereich unter der Registerkarte "Dateien", obwohl die Dateien in der Europa-Datenposition gehostet werden und die Vereinigten Staaten der zentrale Standort des Mandanten sind. Darüber hinaus kann der Benutzer auf die zuletzt verwendeten Dateien unter dem Blade für zuletzt verwendete Ansichten zugreifen. Aktuelle Dateien enthalten möglicherweise Dateien, die für den Benutzer von Benutzern in anderen GEOS freigegeben wurden, und möglicherweise an anderen geografischen Standorten, auf die der Mandant erweitert wird. 

Die Gruppen Website eines bestimmten Teams ist auch Multi-Geo-fähig. Das heißt, wenn ein europäischer Satelliten Benutzer ein Team erstellt, wird die entsprechende Gruppen Website am Standort Europa erstellt, und die Dateien, die dieser Team Gruppe zugeordnet sind, werden an diesem Speicherort beibehalten. Alle nachfolgenden Erfahrungen, wie das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden auf diesen europäischen Standort ausgerichtet, wobei das Versprechen einer Daten Residency für diese Dateien bleibt. Dies wird durch die zugrunde liegenden Foundation Microsoft 365-Gruppen ermöglicht, die multigeo-fähig werden.

Da es sich bei einer Multi-Geo-Mietdauer um einen einzigen globalen Mandanten handelt, können die Satelliten Nutzer während der @ Erwähnungen Ihre Kollegen aus der ganzen Welt sehen – ganz gleich, wo Sie sich befinden. 

Beachten Sie, dass Unterhaltungen in Chats und Besprechungsnotizen innerhalb der Teams nicht multigeo-fähig sind und alle nur innerhalb des zentralen Standorts des Mandanten aufbewahrt werden. In der Regel werden Chat Unterhaltungen nicht auf die Anforderungen von Daten Wohnsitz angewendet.

Weitere Informationen zu Office 365 Multi-Geo finden Sie auf der [Seite Microsoft Multi-Geo-Funktionen](https://aka.ms/multi-geo).