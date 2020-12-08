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
description: Verwenden Sie Power BI zum Analysieren von CQD-Daten für Microsoft Teams.
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588328"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://www.microsoft.com/download/details.aspx?id=102291). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Wenn Sie für CQD-Berichte (Call Quality Dashboard) in Teams verwenden, wenn Sie Power BI zum Abfragen und melden Ihrer Daten verwenden möchten, laden Sie unsere CQD Power BI-Vorlagen herunter. Wenn Sie die Vorlagen in Power BI öffnen, werden Sie aufgefordert, sich mit ihren CQD-Administratoranmeldeinformationen anzumelden. Sie können diese Abfragevorlagen anpassen und an alle Personen in Ihrer Organisation verteilen, die über eine Power BI-Lizenz und CQD-Administratorberechtigungen verfügen.

Bevor Sie diese PBIT-Dateien verwenden können, müssen Sie [den Power BI Connector für Microsoft CQD](CQD-Power-BI-connector.md) mit der im [Download](https://www.microsoft.com/download/details.aspx?id=102291)enthaltenen Datei *MicrosoftCallQuality. PQx* installieren. 

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffs Rolle](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) verfügen, um auf die Power BI-Berichte zuzugreifen. 

|  |  |
|---------|---------|
|<strong>(Neu!)</strong> CQD Teams automatische Telefonzentrale & Anrufwarteschlange-Verlaufsbericht. PBit     |  Diese Vorlage enthält die folgenden drei Berichte:</p><li>Automatische Telefonzentrale – zeigt Analysen für Anrufe an, die in Ihre automatischen Telefonzentralen kommen.</li><li>Anrufwarteschlange – zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschlangen kommen.</li><li>Agent-Zeitachse – zeigt eine Zeitachsenansicht von Agents an, die in Anruf Warteschlangen anrufen aktiv sind.</li><br>Weitere Informationen finden Sie unter [automatische Telefonzentrale & Anrufwarteschlangen-Verlaufsbericht](aa-cq-cqd-historical-reports.md).        |
|CQD Helpdesk-Bericht. PBit     |Durch die Integration von Gebäude-und EUII-Daten ist dieser Bericht dazu vorgesehen, Ihnen den Einstieg in einen einzelnen Benutzer zu ermöglichen, um die Upstream-Ursache für die schlechte Anrufqualität für diesen Benutzer zu finden (beispielsweise befindet sich der Benutzer in einem Gebäude, in dem Netzwerkprobleme auftreten).         |
|CQD Location Enhanced Report. PBit     | Re-Imaginary CQD SPD-Standortberichte. Umfasst 9 Berichte, die Anrufqualität, WLAN-Nutzung, Zuverlässigkeit und die Bewertung meiner Anrufinformationen (RMA) mit zusätzlichen Drill-thrus durch Gebäude oder Nutzer.  Stellen Sie sicher, dass Sie die Gebäudedaten hochgeladen haben, um Ihre Berichterstellung zu maximieren.        |
|CQD Mobile Device Report. PBit     | Bietet Einblicke, die speziell auf Nutzer von mobilen Geräten abgestimmt sind, einschließlich Anrufqualität, Zuverlässigkeit und Bewertung meines Anrufs. Sehen Sie sich das Mobilfunknetz, das WLAN-Netzwerk und die Berichte für mobile Betriebssysteme an (Android, IOS).        |
|CQD PSTN Direct-Routing Bericht. PBit     |Bietet Einblicke speziell für PSTN-Anrufe, die Direktes Routing durchlaufen. Weitere Informationen finden Sie [unter Verwenden des CQD PSTN Direct-Routing Berichts](CQD-PSTN-report.md).         |
|CQD-Zusammenfassungsbericht. PBit     |Bessere Visualisierungen, verbesserte Präsentation, erhöhte Informationsdichte und Rolling dates. Diese Berichte erleichtern die Kennzeichnung von Ausreißer. Führen Sie einen Drilldown in die Anrufqualität nach Standort mit einer benutzerfreundlichen interaktiven Karte durch. 9 neue Berichte:</p>-Qualität insgesamt<br>-Gesamtzuverlässigkeit<br>-RMA (meinen Anruf abstimmen) insgesamt<br>-Konferenz Qualität<br>-P2P-Qualität<br>-Konferenz Zuverlässigkeit<br>-P2P-Zuverlässigkeit<br>-Konferenz-RMA<br>-P2P-RMA         |
|<strong>(Neu!)</strong> CQD Teams-Auslastungs Bericht. PBit     | Zeigt, wie Benutzer in Ihrer Organisation Teams verwenden und wie viel. Stellen Sie sicher, dass Sie die Gebäudedaten hochgeladen haben, um Ihre Berichterstellung zu maximieren. Weitere Informationen finden Sie unter [Verwenden des CQD Power BI-Berichts, um die Verwendung von Microsoft Teams anzuzeigen](CQD-teams-utilization-report.md).        |
|CQD-Benutzer Feedback (Bewertung meines Anrufs) Bericht. PBit     | Zeigt die Bewertung meiner Anrufdaten auf eine Weise an, die Sie ganz einfach verwenden können, um Anrufe für Ihre Organisation zu unterstützen. Querverweis mit Verbatims, um die Schulungsmöglichkeiten für Endnutzer zu erkennen.        |

> [!TIP]
> Nachdem Sie Ihre Power BI-Berichte für CQD-Daten eingerichtet haben, fügen Sie Sie als Registerkarte zu einem Kanal hinzu. Nachdem Sie **+** in einem Kanal ausgewählt haben, wählen Sie **Power BI** aus, und suchen Sie dann den Bericht. Weitere Informationen finden Sie unter [Einbetten eines Berichts mit der Registerkarte Power BI für Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams). Beachten Sie, dass nur Personen mit einer Power BI-Lizenz und CQD-Administratoranmeldeinformationen auf diese Berichte zugreifen können.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)
 
