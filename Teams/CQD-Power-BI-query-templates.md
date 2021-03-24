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
localization_priority: Normal
description: Verwenden Sie Power BI, um CQD-Daten für Microsoft Teams zu analysieren.
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096521"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://www.microsoft.com/download/details.aspx?id=102291). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Laden Sie für Anrufqualitätsdashboardberichte (CQD) in Teams unsere CQD Power BI-Vorlagen herunter, wenn Sie Power BI lieber zum Abfragen und Melden Ihrer Daten verwenden möchten. Wenn Sie die Vorlagen in Power BI öffnen, werden Sie aufgefordert, sich mit Ihren CQD-Administratoranmeldeinformationen zu anmelden. Sie können diese Abfragevorlagen anpassen und an alle Personen in Ihrer Organisation verteilen, die über eine Power BI-Lizenz und CQD-Administratorberechtigungen verfügen.

Bevor Sie diese PBIT-Dateien verwenden können, müssen Sie den Power BI Connector für [Microsoft CQD](CQD-Power-BI-connector.md) mit der im Download enthaltenen *MicrosoftCallQuality.pqx-Datei* [installieren.](https://www.microsoft.com/download/details.aspx?id=102291) 

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffsrolle verfügen,](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) um auf die Power BI-Berichte zu zugreifen. 

|  |  |
|---------|---------|
|<strong>(Neu!)</strong> CQD Teams automatische Telefonzentrale & Call Queue Historical Report.pbit     |  Diese Vorlage enthält die folgenden drei Berichte:</p><li>automatische Telefonzentrale – Zeigt Analysen für Anrufe an, die in Ihre automatischen Telefon telefonieren.</li><li>Anrufwarteschlange – Zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschlangen kommen.</li><li>Agentzeitachse – zeigt eine Zeitachsenansicht von Agenten an, die in Anrufwarteschlange-Anrufen aktiv sind.</li><br>Weitere Informationen finden Sie unter [automatische Telefonzentrale & Verlaufsbericht der Anrufwarteschlange.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |In diesem Bericht werden Gebäude- und EUII-Daten integriert, damit Sie einen Drilldown von einem einzelnen Benutzer erstellen können, um die Ursache für die schlechte Anrufqualität für diesen Benutzer im Upstream zu finden (beispielsweise befindet sich der Benutzer in einem Gebäude, in dem Netzwerkprobleme auftreten).         |
|CQD Location Enhanced Report.pbit     | CQD SPD-Standortberichte neu ein imaginieren. Enthält 9 Berichte, die Informationen zur Anrufqualität, zum Erstellen von WLAN, zur Zuverlässigkeit und zum Bewerten meines Anrufs (RMC) mit zusätzlichen Drillthrus von Building oder vom Benutzer bereitstellen.  Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Ihre Berichterstellungserfahrung zu maximieren.        |
|CQD Mobile Device Report.pbit     | Bietet Einblicke speziell für Benutzer mobiler Geräte, einschließlich Anrufqualität, Zuverlässigkeit und Bewerten meines Anrufs. Anzeigen von Berichten über mobile Netzwerke, WLAN-Netzwerke und mobile Betriebssysteme (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Bietet Einblicke speziell für PSTN-Anrufe, die über Direct Routing gehen. Weitere Informationen finden Sie unter [Verwenden des CQD PSTN Direct Routing Berichts](CQD-PSTN-report.md).         |
|CQD-Zusammenfassungsbericht.pbit     |Bessere Visualisierungen, verbesserte Präsentation, höhere Informationsdichte und Rolldaten. Diese Berichte erleichtern das Bezeichnern von Ausreißern. Drilldowns zur Anrufqualität nach Standort mit einer einfach zu bedienende interaktive Karte. 9 neue Berichte:</p>– Qualität insgesamt<br>– Zuverlässigkeit insgesamt<br>- RMC (Bewerten meines Anrufs) Insgesamt<br>- Konferenzqualität<br>- P2P-Qualität<br>- Konferenzzuverlässigkeit<br>- P2P-Zuverlässigkeit<br>- Konferenz RMC<br>- P2P RMC         |
|<strong>(Neu!)</strong> CQD Teams Utilization Report.pbit     | Zeigt, wie Benutzer in Ihrer Organisation Teams verwenden und wie viel. Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Ihre Berichterstellungserfahrung zu maximieren. Weitere Informationen finden Sie unter Verwenden des [CQD Power BI-Berichts zum Anzeigen der Microsoft Teams-Nutzung.](CQD-teams-utilization-report.md)        |
|CQD-Benutzerfeedback (Bewerten meines Anrufs) Report.pbit     | Zeigt "Meine Anrufdaten bewerten" auf eine Weise an, die Sie ganz einfach verwenden können, um Anrufe für Ihre Organisation zu unterstützen. Querverweis mit ausführlichen Angaben, um Möglichkeiten für die Endbenutzererziehung zu identifizieren.        |

> [!TIP]
> Nachdem Sie Ihre Power BI-Berichte für CQD-Daten eingerichtet haben, fügen Sie sie als Registerkarte zu einem Kanal hinzu. Nachdem Sie **+** in einem Kanal ausgewählt haben, wählen Sie Power BI **aus,** und suchen Sie den Bericht. Weitere Informationen finden Sie unter [Einbetten eines Berichts mit der Registerkarte Power BI für Teams.](/power-bi/service-embed-report-microsoft-teams) Denken Sie daran, dass nur Personen mit einer Power BI-Lizenz und CQD-Administratoranmeldeinformationen auf diese Berichte zugreifen können.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)
