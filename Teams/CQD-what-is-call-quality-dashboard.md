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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie mehr über das Anrufqualitätsdashboard (CQD) und wie Es wird verwendet, um Berichte zur Besprechungs- und Anrufqualität in Microsoft Teams.
ms.openlocfilehash: f87f8184b0417d04206d31780392f21dca387d10
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909556"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Was ist das Anrufqualitätsdashboard (CQD)?

Im Microsoft-Anrufqualitätsdashboard (CQD) – werden die Anruf- und Besprechungsqualität auf Organisationsebene für Microsoft Teams, Skype for Business Online und [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019 angezeigt.  

  
Die neueste Version des CQD verfügt über einen [NrT-Datenfeed (Near-Real-Time, NrT),](CQD-data-and-reports.md)d. h., dass Anrufdatensätze innerhalb von 30 Minuten nach Dem Ende eines Anrufs im CQD verfügbar sind.

Überall dort, wo das CQD Daten zur Identifizierbaren Information [(EUII)](CQD-data-and-reports.md#euii-data)enthält, werden diese auf die gleiche Weise verwaltet wie [EUII im Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

Das CQD soll Teams, Skype for Business- und Netzwerktechnikern die Anruf- und Besprechungsqualität auf Organisationsebene überwachen können. Mithilfe des AQD können Sie Ihr Netzwerk **optimieren,** um die Leistungsqualität zu verbessern. Wenn Sie informationen zu Anruf- und Besprechungsinformationen für einen bestimmten Benutzer einschauen **müssen,** verwenden Sie AQD-Daten in Verbindung mit der [Anrufanalyse pro Benutzer.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Mithilfe des Anrufqualitätsdqds können Sie beispielsweise feststellen, dass die schlechte Anrufqualität eines Benutzers (die Sie anhand der Benutzeranrufanalyse beobachtet haben) auf ein Netzwerkproblem liegt, das sich auch auf viele andere Benutzer auswirkt. Das CQD erfasst sowohl die Persönliche Anruferfahrung als auch die Gesamtqualität von Anrufen, die mit einem Anruf Teams oder Skype for Business. Mit dem AQD können allgemeine Muster sichtbar werden, sodass Netzwerktechniker fundierte Bewertungen der Anrufqualität vornehmen können. Das CQD bietet Berichte über Anrufqualitätsmetriken, die Ihnen einen Einblick in die allgemeine Anrufqualität, Server-Client-Datenströme, Client-Client-Datenströme und SLA zur [Sprachqualität geben.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Screenshot des Anrufqualitätsdashboards](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Im AQD empfehlen wir Ihnen, Gebäude- und Endpunktinformationen hochzuladen, mit deren Hilfe Sie Location-Enhanced-Berichte verwenden können, um die Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers zu analysieren. Die Daten können bewertet werden, um zu ermitteln, ob das Problem für einen einzelnen Benutzer isoliert ist oder ein größeres Benutzersegment betrifft. Zum Aktivieren der Gebäude- oder Endpunkt-spezifischen Ansichten [](CQD-upload-tenant-building-data.md) im AQD muss ein Administrator Gebäude- oder Endpunktinformationen auf der Seite AQD-Mandantendaten **Hochladen** hochladen.

![Screenshot des Anrufqualitätsdashboards für Location-Enhanced Berichte](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Verpassen Sie nicht [](quality-of-experience-review-guide.md) den Artikel Verwalten von Anrufen und Besprechungsqualität, der detaillierte Anleitungen für den Teams-Administrator oder Supporttechniker bietet, der für die Verwaltung der Dienstqualität in Ihrer Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden Power BI zum Analysieren von AQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Weitere [Informationen Power BI Sie unter Verwenden von AQD-Daten.](CQD-Power-BI-query-templates.md)



## <a name="related-topics"></a>Verwandte Themen

[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwalten der Anruf- und Besprechungsqualität mithilfe des Anrufqualitäts-AQD](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)


[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
