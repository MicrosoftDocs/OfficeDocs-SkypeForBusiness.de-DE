---
title: Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
ms.openlocfilehash: 5d081853f9fc5c1106ce6906f31ddc10613ec9f9
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158962"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Wenn Sie für CQD-Berichte in Microsoft Teams die Verwendung von Power BI zum Abfragen und melden Ihrer Daten bevorzugen, laden Sie unsere CQD Power BI-Vorlagen herunter. Wenn Sie die Vorlagen in Power BI öffnen, werden Sie aufgefordert, sich mit ihren CQD-Administratoranmeldeinformationen anzumelden. Sie können diese Abfragevorlagen anpassen und an alle Personen in Ihrer Organisation verteilen, die über eine Power BI-Lizenz und CQD-Administratorberechtigungen verfügen.

Bevor Sie diese PBIT-Dateien verwenden können, müssen Sie [den Power BI Connector für Microsoft CQD](CQD-Power-BI-connector.md) mit der im [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)enthaltenen Datei *MicrosoftCallQuality. PQx* installieren. 

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffs Rolle](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) verfügen, um auf die Power BI-Berichte zuzugreifen. 

|  |  |
|---------|---------|
|CQD Helpdesk-Bericht. PBit     |Durch die Integration von Gebäude-und EUII-Daten ist dieser Bericht dazu vorgesehen, Ihnen den Einstieg in einen einzelnen Benutzer zu ermöglichen, um die Upstream-Ursache für die schlechte Anrufqualität für diesen Benutzer zu finden (beispielsweise befindet sich der Benutzer in einem Gebäude, in dem Netzwerkprobleme auftreten).         |
|CQD Location Enhanced Report. PBit     | Re-Imaginary CQD SPD-Standortberichte. Umfasst 9 Berichte, die Anrufqualität, WLAN-Nutzung, Zuverlässigkeit und die Bewertung meiner Anrufinformationen (RMA) mit zusätzlichen Drill-thrus durch Gebäude oder Nutzer.  Stellen Sie sicher, dass Sie die Gebäudedaten hochgeladen haben, um Ihre Berichterstellung zu maximieren.        |
|CQD Mobile Device Report. PBit     | Bietet Einblicke, die speziell auf Nutzer von mobilen Geräten abgestimmt sind, einschließlich Anrufqualität, Zuverlässigkeit und Bewertung meines Anrufs. Sehen Sie sich das Mobilfunknetz, das WLAN-Netzwerk und die Berichte für mobile Betriebssysteme an (Android, IOS).        |
|CQD PSTN Direct-Routing Bericht. PBit     |Bietet Einblicke speziell für PSTN-Anrufe, die Direktes Routing durchlaufen. Weitere Informationen finden Sie [unter Verwenden des CQD PSTN Direct-Routing Berichts](CQD-PSTN-report.md).         |
|CQD-Zusammenfassungsbericht. PBit     |Bessere Visualisierungen, verbesserte Präsentation, erhöhte Informationsdichte und Rolling dates. Diese Berichte erleichtern die Kennzeichnung von Ausreißer. Führen Sie einen Drilldown in die Anrufqualität nach Standort mit einer benutzerfreundlichen interaktiven Karte durch. 9 neue Berichte:</p>-Qualität insgesamt<br>-Gesamtzuverlässigkeit<br>-RMA (meinen Anruf abstimmen) insgesamt<br>-Konferenz Qualität<br>-P2P-Qualität<br>-Konferenz Zuverlässigkeit<br>-P2P-Zuverlässigkeit<br>-Konferenz-RMA<br>-P2P-RMA         |
|<strong>(Neu!)</strong> CQD Teams-Auslastungs Bericht. PBit     | Zeigt, wie Benutzer in Ihrer Organisation Teams verwenden und wie viel. Stellen Sie sicher, dass Sie die Gebäudedaten hochgeladen haben, um Ihre Berichterstellung zu maximieren. Weitere Informationen finden Sie unter [Verwenden des CQD Power BI-Berichts, um die Verwendung von Microsoft Teams anzuzeigen](CQD-teams-utilization-report.md).        |
|CQD-Benutzer Feedback (Bewertung meines Anrufs) Bericht. PBit     | Zeigt die Bewertung meiner Anrufdaten auf eine Weise an, die Sie ganz einfach verwenden können, um Anrufe für Ihre Organisation zu unterstützen. Querverweis mit Verbatims, um die Schulungsmöglichkeiten für Endnutzer zu erkennen.        |

> [!TIP]
> Nachdem Sie Ihre Power BI-Berichte für CQD-Daten eingerichtet haben, fügen Sie Sie als Registerkarte zu einem Kanal hinzu. Nachdem Sie in **+** einem Kanal ausgewählt haben, wählen Sie **Power BI** aus, und suchen Sie dann den Bericht. Weitere Informationen finden Sie unter [Einbetten eines Berichts mit der Registerkarte Power BI für Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams). Beachten Sie, dass nur Personen mit einer Power BI-Lizenz und CQD-Administratoranmeldeinformationen auf diese Berichte zugreifen können.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)
 
