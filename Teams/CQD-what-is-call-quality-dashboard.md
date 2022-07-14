---
title: Was ist das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)?
author: CarolynRowe
ms.author: crowe
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
description: Erfahren Sie mehr über das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) und dessen Verwendung, um Berichte zur Besprechungs- und Anrufqualität in Microsoft Teams anzuzeigen.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790070"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Was ist das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)?

Das Microsoft Call Quality Dashboard (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) – Zeigt die Anruf- und Besprechungsqualität auf **organisationsweiter Ebene** für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 an. 

  
Die neueste Version von CQD verfügt über einen [Nahezu-Echtzeit-Datenfeed (NRT](CQD-data-and-reports.md)), was bedeutet, dass Anrufdatensätze innerhalb von 30 Minuten nach Dem Ende eines Anrufs in CQD verfügbar sind.

Wo immer CQD Informationen [zu Endbenutzern (EUII)](CQD-data-and-reports.md#euii-data) enthält, wird sie auf die gleiche Weise wie [EUII in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview) verwaltet.

CQD soll Teams-Administratoren, Skype for Business Administratoren und Netzwerktechnikern dabei helfen, die Anruf- und Besprechungsqualität auf organisationsweiter Ebene zu überwachen. Sie verwenden CQD, um **Ihr Netzwerk zu optimieren** , um die Leistungsqualität zu steigern. Wenn Sie sich mit Anruf- und Besprechungsinformationen für einen **bestimmten Benutzer** befassen müssen, verwenden Sie CQD-Daten in Verbindung mit der [Anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) pro Benutzer.

Mit CQD können Sie beispielsweise feststellen, dass die schlechte Anrufqualität eines Benutzers (die Sie mithilfe der Anrufanalyse pro Benutzer festgestellt haben) auf ein Netzwerkproblem zurückzuführen ist, das auch viele andere Benutzer betrifft. CQD erfasst sowohl die individuelle Anruferfahrung als auch die Gesamtqualität von Anrufen, die mit Teams oder Skype for Business getätigt werden. Mit CQD können allgemeine Muster sichtbar werden, sodass Netzwerktechniker fundierte Bewertungen der Anrufqualität vornehmen können. CQD bietet Berichte über Anrufqualitätsmetriken, die Ihnen Einblicke in die allgemeine Anrufqualität, Server-Client-Streams, Client-Client-Streams und [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) für Sprachqualität geben. 
  
![Screenshot des Anrufqualitäts-Dashboards.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In CQD empfehlen wir Ihnen, Gebäude- und Endpunktinformationen hochzuladen, mit denen Sie Location-Enhanced Berichte verwenden können, um die Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers zu analysieren. Die Daten können bewertet werden, um festzustellen, ob das Problem für einen einzelnen Benutzer isoliert ist oder sich auf ein größeres Segment von Benutzern auswirkt. Um gebäude- oder endpunktspezifische Ansichten in CQD zu aktivieren, muss ein Administrator [Gebäude- oder Endpunktinformationen](CQD-upload-tenant-building-data.md) auf die Seite zum Hochladen von CQD-Mandantendaten hochladen.

![Screenshot der Location-Enhanced-Berichte des Anrufqualitätsdashboards.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Verpassen Sie nicht unseren Artikel " [Anruf- und Besprechungsqualität verwalten](quality-of-experience-review-guide.md) ", der ausführliche Anleitungen für den Teams-Administrator oder Supporttechniker bietet, der für die Verwaltung der Servicequalität in Teams verantwortlich ist.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Lesen [Verwenden Sie Power BI, um CQD-Daten zu analysieren](CQD-Power-BI-query-templates.md) , um mehr zu erfahren.



## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)


[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
