---
title: Was ist das Anrufqualitätsdashboard (CQD)?
ms.author: serdars
author: SerdarSoysal
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
description: Erfahren Sie mehr über das Anrufqualitätsdashboard (CQD) und wie Sie es verwenden, um Berichte zur Besprechungs- und Anrufqualität in Microsoft Teams anzuzeigen.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094939"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Was ist das Anrufqualitätsdashboard (CQD)?

Das Microsoft Call Quality Dashboard (CQD) – zeigt die Anruf- und Besprechungsqualität auf Organisationsebene für Microsoft Teams, Skype for Business Online und [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019 an.  

  
Die neueste Version von CQD verfügt über einen [Nah-Echtzeit-Datenfeed (NRT),](CQD-data-and-reports.md)was bedeutet, dass Anrufdatensätze in CQD innerhalb von 30 Minuten nach Dem Ende eines Anrufs verfügbar sind.

Überall dort, wo CQD [EUII-Daten (User Identifiable Information,](CQD-data-and-reports.md#euii-data)Identifizierbare Informationen) enthält, wird sie in Microsoft [365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)auf die gleiche Weise wie EUII verwaltet.

CQD soll Teams-Administratoren, Skype for Business-Administratoren und Netzwerktechnikern dabei helfen, die Anruf- und Besprechungsqualität auf Organisationsebene zu überwachen. Mithilfe von CQD können Sie Ihr Netzwerk **optimieren,** um die Leistungsqualität zu steigern. Wenn Sie anruf- und besprechungsinformationen für einen bestimmten Benutzer suchen **müssen,** verwenden Sie CQD-Daten in Verbindung mit der [Anrufanalyse pro Benutzer.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Mithilfe von CQD können Sie beispielsweise feststellen, dass die schlechte Anrufqualität eines Benutzers (die Sie bei der Anrufanalyse pro Benutzer beobachtet haben) auf ein Netzwerkproblem liegt, das auch viele andere Benutzer betrifft. CQD erfasst sowohl die individuelle Anruferfahrung als auch die Gesamtqualität von Anrufen, die mit Teams oder Skype for Business vorgenommen werden. Bei CQD können allgemeine Muster sichtbar werden, sodass Netzwerktechniker fundierte Bewertungen der Anrufqualität vornehmen können. CQD stellt Berichte über Metriken zur Anrufqualität bereit, die Ihnen Einen Einblick in die allgemeine Anrufqualität, Server-Client-Datenströme, Client-Client-Datenströme und SLA für Sprachqualität [geben.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Screenshot des Anrufqualitätsdashboards.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In CQD empfehlen wir Ihnen, Gebäude- und Endpunktinformationen hochzuladen, mit denen Sie Location-Enhanced-Berichte verwenden können, um die Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers zu analysieren. Die Daten können ausgewertet werden, um festzustellen, ob das Problem für einen einzelnen Benutzer isoliert ist oder ein größeres Benutzersegment betrifft. Um gebäude- oder endpunktspezifische Ansichten in CQD [](CQD-upload-tenant-building-data.md) zu aktivieren, muss ein Administrator Gebäude- oder Endpunktinformationen auf die Seite CQD-Mandantendatenupload **hochladen.**

![Screenshot des Anrufqualitätsdashboards Location-Enhanced Berichte.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Verpassen Sie nicht [](quality-of-experience-review-guide.md) unseren Artikel Anruf- und Besprechungsqualität verwalten, der eine detaillierte Anleitung für den Teams-Administrator oder Supporttechniker bietet, der für die Verwaltung der Dienstqualität in Teams zuständig ist.

## <a name="older-version-of-cqd-cqdlynccom"></a>Ältere Version von CQD (CQD.lync.com)

Die aktuelle Version von CQD ( https://CQD.Teams.microsoft.com) ersetzt die ältere Version von CQD ( https://CQD.lync.com) . Sie können weiterhin CQD.lync.com (im Skype for Business Admin Center verfügbar), aber ab dem 1. Juli 2020 werden die Daten aus CQD verwendet. Teams.microsoft.com. Wir deaktivieren den Zugriff auf CQD.lync.com, sodass Sie zu CQD wechseln sollten. Teams.microsoft.com, wenn Sie dies noch nicht getan haben.

> [!IMPORTANT]
> Ab dem 1. Juli 2020 können Sie Ihre Gebäude- oder Abfragedaten aus dem alten CQD (CQD.lync.com) nicht mehr anzeigen oder ändern. Wenn Sie diese Daten noch nicht aus dem CQD.lync.com migriert haben und sie trotzdem benötigen, melden Sie ein Supportticket an.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Weitere Informationen finden Sie unter Verwenden von Power BI zum Analysieren von [CQD-Daten.](CQD-Power-BI-query-templates.md)



## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)


[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)