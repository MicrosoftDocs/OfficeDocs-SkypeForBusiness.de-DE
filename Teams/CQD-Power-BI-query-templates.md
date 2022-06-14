---
title: Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Verwenden Sie Power BI, um CQD-Daten für Microsoft Teams zu analysieren.
ms.openlocfilehash: 7d951c0e96f98c343a388e536311bf00890e5302
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056955"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://www.microsoft.com/download/details.aspx?id=102291). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Wenn Sie für CQD-Berichte (Call Quality Dashboard) in Teams lieber Power BI verwenden möchten, um Ihre Daten abzufragen und zu melden, laden Sie unsere CQD-Power BI-Vorlagen herunter. Wenn Sie die Vorlagen in Power BI öffnen, werden Sie aufgefordert, sich mit Ihren CQD-Administratoranmeldeinformationen anzumelden. Sie können diese Abfragevorlagen anpassen und an alle Personen in Ihrer Organisation verteilen, die über eine Power BI-Lizenz und CQD-Administratorberechtigungen verfügen.

Bevor Sie diese PBIT-Dateien verwenden können, müssen Sie [den Power BI Connector für Microsoft CQD](CQD-Power-BI-connector.md) mithilfe der im [Download](https://www.microsoft.com/download/details.aspx?id=102291) enthaltenen Datei *"MicrosoftCallQuality.pqx*" installieren. 

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffsrolle](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) für den Zugriff auf die Power BI Berichte verfügen. 

|Pbit |Beschreibung |
|:----------|:---------|
|<strong>(Neu!)</strong> QER.pbit     |  Mit der QER-Vorlage (Quality of Experience Report) können Kunden proaktiv Probleme identifizieren, die sich auf die Teams Besprechungs- und Anruferfahrung auswirken, bevor sie eskalieren. Darüber hinaus werden Berichte bereitgestellt, mit denen Administratoren schnell auf eskalierende Probleme reagieren und die Frage "Was ist während der Besprechung passiert?" beantworten können.  Diese Vorlage enthält die folgenden Berichte:</p><li>Suche – Ermöglicht die Suche nach Besprechungs-URL, Konferenz-ID, Subnetz oder UPN.</li><li>Besprechungsintegritätsdetails – detaillierte Metriken für eine einzelne Besprechung.</li><li>Benutzerintegritätsdetails – detaillierte Metriken für einen einzelnen Benutzer.</li><li>Medienintegrität – Allgemeine Übersicht über wichtige Integritätsindikatoren (Key Health Indicators, KHI) für die allgemeine Mandantenbesprechung und anrufintegrität.</li><li>Medieneinrichtung – Analysieren von Medieneinrichtungsfehlern.</li><li>Mediensicherheit – Analysieren sie Probleme mit der Mediensicherheit.</li><li>Audio/Video/Sharing Health – Überprüfen Sie khIs auf mittlerer Ebene für Audio, Video oder Freigabestatus.</li><li>Audio/Video/Freigabe-Integritätsdetails – Detaillierte Metriken zum Audio-, Video- oder Freigabestatus überprüfen.</li><li>VPN – Überprüfen Sie die Auswirkungen von VPN auf die Besprechungsintegrität. (Geschätztes oder zugeordnetes VPN)</li><li>Top 10 Berichte – Identifizieren Sie Problembereiche in Ihrem Mandanten.</li><li>Dailies – überprüfen Sie den täglichen Bericht der KHIs.</li><li>Nutzung – Besprechungs- und Anrufnutzung.</li><li>Benutzerfeedback – Feedback zur Benutzerumfrage überprüfen, auch als "Meinen Anruf bewerten" bezeichnet.</li><li>Transport – Identifizieren Sie Netzwerke, die UDP blockieren.</li><li>Geräte – Überprüfen Sie die Auswirkungen von Geräten.</li><li>Clients – Überprüfen Sie clientorientierte Metriken.</li><li>Gebäudedaten – Überprüfen Sie die Gebäudedatendatei in CQD.</li><li>PSTN-Integrität und Benutzerdetails – zwei Berichte, die eine allgemeine Zusammenfassung sowie die individuelle Benutzerintegrität für PSTN-basierte Anrufe bereitstellen.</li><li>Netzwerkmetriken – zwei Berichte, in denen unformatierte Netzwerkmetrikdetails für Jitter, Paketverlust und Latenz angezeigt werden.</li>  |
|CQD Teams Automatische Telefonzentrale & Anrufwarteschleifenverlaufsbericht.pbit     |  Diese Vorlage enthält die folgenden drei Berichte:</p><li>Automatische Telefonzentrale – zeigt Analysen für Anrufe an, die in Ihre automatischen Telefonzentralen eingehen.</li><li>Anrufwarteschleife – zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschleifen eingehen.</li><li>Agent-Zeitachse – zeigt eine Zeitachsenansicht der Agents an, die in Anrufen der Anrufwarteschleife aktiv sind.</li><br>Weitere Informationen finden Sie unter ["Automatische Telefonzentrale & Anrufwarteschleifenverlaufsbericht"](aa-cq-cqd-historical-reports.md). |
|CQD Helpdesk Report.pbit     |Dieser Bericht integriert Gebäude- und EUII-Daten und ermöglicht es Ihnen, einen Drillup von einem einzelnen Benutzer auszuführen, um die Upstream-Ursache für eine schlechte Anrufqualität für diesen Benutzer zu finden (z. B. befindet sich der Benutzer in einem Gebäude, in dem Netzwerkprobleme auftreten). |
|CQD Location Enhanced Report.pbit     | Neubilden von CQD SPD-Standortberichten. Enthält 9 Berichte, die Informationen zur Anrufqualität, Zum Erstellen von WLAN, Zuverlässigkeit und Rate My Call (RMC) mit zusätzlichen Drill-Thrus by Building oder nach Benutzer bereitstellen. Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Die Berichterstellung zu maximieren. |
|CQD Mobile Device Report.pbit     | Bietet Einblicke speziell für Benutzer mobiler Geräte, einschließlich Anrufqualität, Zuverlässigkeit und "Meinen Anruf bewerten". Anzeigen von Berichten zu Mobilnetzwerken, WLAN-Netzwerken und mobilen Betriebssystemen (Android, iOS). |
|CQD PSTN Direct Routing Report.pbit     |Bietet Einblicke speziell für PSTN-Anrufe, die direct Routing durchlaufen. Weitere Informationen finden [Sie unter Verwenden des CQD-PSTN-Direct Routing-Berichts](CQD-PSTN-report.md). |
|CQD Summary Report.pbit     |Bessere Visualisierungen, verbesserte Präsentation, erhöhte Informationsdichte und rollierende Datumsangaben. Diese Berichte erleichtern das Identifizieren von Ausreißern. Führen Sie einen Drilldown in die Anrufqualität nach Standort mit einer einfach zu bedienenden interaktiven Karte durch. Neun neue Berichte:</p>- Qualität insgesamt<br>- Zuverlässigkeit insgesamt<br>- RMC (Meinen Anruf bewerten) Insgesamt<br>- Konferenzqualität<br>- P2P-Qualität<br>- Konferenzsicherheit<br>- P2P-Zuverlässigkeit<br>- Konferenz-RMC<br>- P2P RMC         |
|CQD Teams Utilization Report.pbit     | Zeigt, wie Benutzer in Ihrer Organisation Teams verwenden und wie viel. Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Die Berichterstellung zu maximieren. Weitere Informationen finden Sie unter [Verwenden von CQD Power BI Bericht zum Anzeigen Microsoft Teams Auslastung](CQD-teams-utilization-report.md). |
|CQD-Benutzerfeedback (Rate My Call) Report.pbit     | Zeigt "Meine Anruf bewerten"-Daten auf eine Weise an, die Sie ganz einfach verwenden können, um Anrufe für Ihre Organisation zu unterstützen. Querverweis mit ausführlichen Informationen zur Identifizierung von Bildungschancen für Endbenutzer. |

> [!TIP]
> Nachdem Sie Ihre Power BI Berichte für CQD-Daten eingerichtet haben, fügen Sie sie als Registerkarte zu einem Kanal hinzu. Nachdem Sie in einem Kanal ausgewählt **+** haben, wählen Sie **Power BI** aus, und suchen Sie dann ihren Bericht. Weitere Informationen finden Sie im [Bericht "Einbetten" mit der Registerkarte Power BI für Teams](/power-bi/service-embed-report-microsoft-teams). Denken Sie daran, dass nur Personen mit einer Power BI-Lizenz und CQD-Administratoranmeldeinformationen auf diese Berichte zugreifen können.

## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)
