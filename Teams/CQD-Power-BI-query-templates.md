---
title: Verwenden Power BI zum Analysieren von AQD-Daten für Microsoft Teams
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
description: Verwenden Power BI zum Analysieren von AQD-Daten für Microsoft Teams.
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013769"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Verwenden Power BI zum Analysieren von AQD-Daten für Microsoft Teams

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://www.microsoft.com/download/details.aspx?id=102291). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Wenn Sie für Anrufqualitätsdashboard-Berichte (Anrufqualitätsdashboard) in Teams lieber Power BI zum Abfragen und Melden Ihrer Daten verwenden möchten, laden Sie unsere CQD-Power BI herunter. Wenn Sie die Vorlagen in Power BI öffnen, werden Sie aufgefordert, sich mit Ihren Administratoranmeldeinformationen für das AQD anmelden. Sie können diese Abfragevorlagen anpassen und an jeden in Ihrer Organisation verteilen, der über Power BI-Lizenz und Administratorberechtigungen für AQD verfügt.

Bevor Sie diese PBIT-Dateien verwenden können, müssen Sie den Power BI Connector für [Microsoft CQD](CQD-Power-BI-connector.md) mithilfe der im Download enthaltenen Datei *"MicrosoftCallQuality.pqx"* [installieren.](https://www.microsoft.com/download/details.aspx?id=102291) 

Stellen Sie sicher, dass Sie über die richtige Zugriffsrolle für [AQD verfügen,](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) um auf die Power BI zugreifen zu können. 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong>(Neu!)</strong> CQD Teams automatische Telefonzentrale & Call Queue Historical Report.pbit     |  Diese Vorlage enthält die folgenden drei Berichte:</p><li>Automatische Telefonzentrale – zeigt Analysen für Anrufe an, die in Ihre automatischen Telefonzentralen eingehen.</li><li>Anrufwarteschleife – zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschleifen eingehen.</li><li>Agent-Zeitachse – zeigt eine Zeitachsenansicht der Agents an, die in Anrufen der Anrufwarteschleife aktiv sind.</li><br>Weitere Informationen finden Sie unter [Verlaufsbericht automatische Telefonzentrale & Anrufwarteschleife.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Dieser Bericht dient zum Integrieren von Gebäude- und EUII-Daten und soll Es Ihnen gestatten, einen Drilldown eines einzelnen Benutzers zu erstellen, um die Ursache für eine schlechte Anrufqualität in Upstream zu finden (z. B. wenn sich der Benutzer in einem Gebäude befindet, in dem Netzwerkprobleme auftreten).         |
|CQD Location Enhanced Report.pbit     | Wiedererstelle von Standortberichten für CQD SPD Enthält 9 Berichte, die Informationen zu Anrufqualität, WLAN, Zuverlässigkeit und Bewerten von Anrufen mit zusätzlichen Drillthruss durch Gebäude oder Benutzer bereitstellen.  Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Die Berichterstellung zu maximieren.        |
|CQD Mobile Device Report.pbit     | Bietet Einblicke, die speziell für Benutzer mobiler Geräte optimiert wurden, einschließlich Anrufqualität, Zuverlässigkeit und Anrufrate. Anzeigen von Berichten über Mobilnetzwerke, WLAN-Netzwerke und Betriebssysteme für mobile Geräte (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Bietet einblicke speziell für PSTN-Anrufe, die über Direct Routing gehen. Weitere Informationen finden Sie unter [Verwenden des PSTN-Direktroutingberichts](CQD-PSTN-report.md)für AQD.         |
|CQD-Zusammenfassungsbericht.pbit     |Bessere Visualisierungen, verbesserte Präsentation, höhere Informationsdichte und Rolldaten. Diese Berichte vereinfachen das Bezeichnern von Ausreißern. Führen Sie mithilfe einer einfach zu bedienende interaktiven Karte einen Drilldown in die Anrufqualität nach Standort durch. 9 neue Berichte:</p>- Quality Overall<br>- Zuverlässigkeit insgesamt<br>- RMC (Rate My Call, Meinen Anruf bewerten) Insgesamt<br>- Konferenzqualität<br>- P2P-Qualität<br>– Konferenzzuverlässigkeit<br>- P2P Zuverlässigkeit<br>- Conference RMC<br>- P2P RMC         |
|<strong>(Neu!)</strong> CQD Teams Utilization Report.pbit     | Zeigt, wie Benutzer in Ihrer Organisation Teams und wie viel. Stellen Sie sicher, dass Sie die Gebäudedaten hochladen, um Die Berichterstellung zu maximieren. Weitere Informationen finden Sie unter Verwenden [des AQD-Power BI zum Anzeigen Microsoft Teams Nutzung](CQD-teams-utilization-report.md).        |
|CQD User Feedback (Rate My Call) Report.pbit     | Zeigt die Daten zum Bewerten meines Anrufs in einer Weise an, mit der Sie Anrufe für Ihre Organisation problemlos unterstützen können. Querverweis mit Ausführlichkeit, um Möglichkeiten für die Ausbildung von Endbenutzern zu identifizieren.        |

> [!TIP]
> Nachdem Sie Ihre AQD-Power BI eingerichtet haben, fügen Sie sie als Registerkarte zu einem Kanal hinzu. Nachdem Sie die Option in einem Kanal ausgewählt haben, wählen **+** **Power BI** aus, und suchen Sie den Bericht. Weitere Informationen finden Sie unter [Einbetten eines Berichts auf der Registerkarte](/power-bi/service-embed-report-microsoft-teams)Power BI für Teams. Denken Sie daran, dass nur Power BI mit einer Lizenz und Administratoranmeldeinformationen für AQD auf diese Berichte zugreifen können.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)
