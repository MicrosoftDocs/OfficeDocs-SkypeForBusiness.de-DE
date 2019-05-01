---
title: Microsoft Teams – Gerätenutzungsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erfahren Sie, wie mit den Teams Gerät Nutzungsbericht im Microsoft-Teams, Administrationscenter finden Sie unter Teams wie Benutzer in Ihrer Organisation herstellen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5b912a9a4d76fd1be2947cea6dd2750ddbaa49
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2019
ms.locfileid: "33495899"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Teams Gerät Verwendungsbericht in der Verwaltungskonsole von Microsoft-Teams, erhalten Sie Informationen zur Verbindung von Benutzern, Teams. Sie können den Bericht verwenden, sehen Sie die Geräte, die verwendet werden, in Ihrer Organisation, einschließlich wie viele Teams von ihren mobilen Geräten, die beim Klicken auf Go verwenden.  

![Screenshot des Nutzungsberichts Teams Gerät in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-reports-device-usage.png "Screenshot des Nutzungsberichts Teams Gerät in der Verwaltungskonsole von Microsoft-Teams")

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Wechseln Sie zur Microsoft-Teams-Verwaltungskonsole im linken Navigationsbereich auf **Analytics &-Berichte**und wählen Sie dann unter **Bericht** **Teams Gerät Usage**. 
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**. 

## <a name="interpret-the-report"></a>Interpretieren des Berichts

![Screenshot des Nutzungsberichts Teams Gerät in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-reports-device-usage-with-callouts.png "Screenshot des Nutzungsberichts Teams Gerät in der Microsoft-Teams-Verwaltungskonsole mit nummerierten Beschriftungen")

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Teams Gerät Verwendungsbericht kann für Trends über die letzten 7 Tage oder 28 Tage angezeigt werden.  |
|**2**   |Jeder Bericht besitzt Datum Wenn der Bericht generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die x-Achse des Diagramms stellt verschiedene Geräte (**Windows**, **Mac**, **iOS**, **Android-Telefon**) zum Verbinden mit Teams. </li><li>Die y-Achse ist die Anzahl der Benutzer des Geräts über den ausgewählten Zeitraum an.</li> </ul>Bewegen Sie den Mauszeiger über der Leiste, die ein Gerät, um die Anzahl der Benutzer mit dem Gerät herstellen Teams finden Sie unter darstellt.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der Gerät Auslastung durch Benutzer. <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können den Anzeigenamen So wechseln zur Seite des Benutzers in der Verwaltungskonsole von Microsoft-Teams klicken. </li><li>**Windows** ist aktiviert, wenn der Benutzer im Desktopclient Teams auf einem Windows-basierten Computer aktiv war.</li><li>**Mac** ist aktiviert, wenn der Benutzer im Desktopclient Teams auf einem Mac OS Computer aktiv war. </li> <li>**iOS** ist aktiviert, wenn der Benutzer auf dem Teams mobilen Client für iOS aktiv war.</li><li>**Android-Telefon** wird ausgewählt, wenn der Benutzer auf dem Teams mobilen Client für Android aktiv war. <li>**Letzte Aktivität** ist das Datum der letzten (UTC), das der Benutzer in einer Aktivität Teams verwendet wurde.</li> </ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht in eine CSV-Datei für die offline-Analyse exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf die Registerkarte **Downloads** **herunterladen** , um den Bericht herunterzuladen, sobald es vorliegt.<br>![Screenshot der Registerkarte Downloads exportiert herunterladen-Berichte anzeigen](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Verwandte Themen
- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Teams-Nutzungsbericht](teams-usage-report.md)
- [Teams-Benutzeraktivitätsbericht](user-activity-report.md)