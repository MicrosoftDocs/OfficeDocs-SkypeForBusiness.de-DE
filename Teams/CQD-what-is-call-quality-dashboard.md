---
title: Was ist das Anruf Qualitäts Dashboard (CQD)?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie mehr über das Anruf Qualitäts Dashboard (CQD) und wie Sie es verwenden können, um Berichte über die Qualität von Besprechungen und anrufen in Microsoft Teams anzuzeigen.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088243"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Was ist das Anruf Qualitäts Dashboard (CQD)?

Das Microsoft Call Quality-Dashboard (CQD) – [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) zeigt die Anruf-und Besprechungs Qualität auf **organisationsweiter Ebene**für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019. 

  
Die neueste Version von CQD verfügt über einen [fast-Echtzeit-Datenfeed (NRT)](CQD-data-and-reports.md), was bedeutet, dass anrufdatensätze innerhalb von 30 Minuten nach dem Ende eines Anrufs in CQD zur Verfügung stehen.

Unabhängig davon, wo CQD [Endbenutzer-identifizierbare Daten (EUII)](CQD-data-and-reports.md#euii-data)enthält, wird es auf die gleiche Weise wie [EUII in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)verwaltet.

CQD wurde entwickelt, um Teams-Administratoren, Skype for Business-Administratoren und Netzwerk Ingenieuren zu helfen, die Anruf-und Besprechungs Qualität auf organisationsweiter Ebene zu überwachen. Sie verwenden CQD, damit Sie **Ihr Netzwerk optimieren** können, um die Leistungsqualität zu steigern. Wenn Sie die Anruf-und Besprechungsinformationen für einen **bestimmten Benutzer**untersuchen müssen, verwenden Sie CQD-Daten in Verbindung mit der pro-Benutzer- [anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md).

So können Sie beispielsweise mithilfe von CQD feststellen, dass die schlechte Anrufqualität eines Benutzers (die Sie bei der Verwendung der pro-Benutzer-anrufanalyse beobachtet haben) auf ein Netzwerkproblem zurückzuführen ist, das auch viele andere Benutzer betrifft. CQD erfasst sowohl die individuelle Anruf Erfahrung als auch die Gesamtqualität von anrufen, die über Teams oder Skype for Business getätigt wurden. Bei CQD können die allgemeinen Muster deutlich werden, sodass Netzwerkingenieure fundierte Bewertungen der Anrufqualität vornehmen können. CQD stellt Berichte über Anruf Qualitäts Metriken bereit, mit denen Sie Einblicke in die allgemeine Anrufqualität, Server-Client-Streams, Client-Client-Streams und [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)für die Sprachqualität erhalten. 
  
![Screenshot des Dashboards für die Anrufqualität.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In CQD empfehlen wir Ihnen, Gebäude-und Endpunktinformationen hochzuladen, sodass Sie mithilfe von Standort optimierten Berichten die Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers analysieren können. Die Daten können ausgewertet werden, um festzustellen, ob das Problem für einen einzelnen Benutzer isoliert ist oder ein größeres Segment von Benutzern betrifft. Damit Sie Gebäude-oder Endpunkt spezifische Ansichten in CQD aktivieren können, muss ein Administrator [Gebäude-oder Endpunktinformationen](CQD-upload-tenant-building-data.md) auf der CQD-Seite für **Mandantendaten** hochladen.

![Screenshot der Standort optimierten Berichte des Anruf Qualitäts Dashboards](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Verpassen Sie nicht unseren Artikel " [Anruf-und Besprechungs Qualität verwalten](quality-of-experience-review-guide.md) ", der detaillierte Anleitungen für den Team-Administrator oder Support-Techniker bietet, der für die Verwaltung der Dienstqualität in Microsoft Teams verantwortlich ist.

## <a name="older-version-of-cqd-cqdlynccom"></a>Ältere Version von CQD (CQD.lync.com)

Die aktuelle Version von CQD ( https://CQD.Teams.microsoft.com) ersetzt die ältere Version von CQD ( https://CQD.lync.com) . Sie können weiterhin CQD.lync.com verwenden (im Skype for Business Admin Center verfügbar), aber ab dem 1. Juli 2020 werden die Daten von CQD verwendet. Teams.Microsoft.com. Wir werden den Zugriff auf CQD.lync.com bald deaktivieren, daher sollten Sie zu CQD wechseln. Teams.Microsoft.com, wenn dies noch nicht geschehen ist.

> [!IMPORTANT]
> Ab dem 1. Juli 2020 können Sie Ihre Gebäude-oder Abfrage Daten aus dem alten CQD (CQD.lync.com) nicht mehr anzeigen oder ändern. Wenn Sie diese Daten noch nicht von CQD.lync.com migriert haben und Sie dennoch benötigen, melden Sie ein Support Ticket.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Lesen [verwenden Sie Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md) , um weitere Informationen zu erhalten.



## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Einrichten des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und-Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstrom Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)


[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)