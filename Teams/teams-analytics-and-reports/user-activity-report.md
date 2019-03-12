---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Erfahren Sie, wie mit der Teams User Activity Report im Microsoft-Teams, Administrationscenter finden Sie unter wie Teams von Benutzern in Ihrer Organisation verwendet wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 671f3cd5632712a9bc5cc08e15c04023a33ec052
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542631"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Teams User Activity Report bietet Ihnen einen Einblick in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams durchführen. Beispielsweise können Sie sehen, wie viele Benutzer über 1:1-Anrufe zu kommunizieren, wie viele Benutzer über DDE-Kanalnachrichten kommunizieren und wie viele Benutzer private Chatnachrichten beteiligen.

![Screenshot des Teams User Activity Report in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-reports-user-activity.png "Screenshot des Teams User Activity Report in der Verwaltungskonsole von Microsoft-Teams")

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Wechseln Sie zur Microsoft-Teams-Verwaltungskonsole im linken Navigationsbereich auf **Analytics &-Berichte**und wählen Sie dann unter **Bericht** **Benutzeraktivität Teams**. 
2. Geben Sie unter **Datumsbereich**wählen Sie einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**. 

## <a name="interpret-the-report"></a>Auswertung des Berichts

![Screenshot des Teams User Activity Report in der Microsoft-Teams-Verwaltungskonsole mit nummerierten Beschriftungen] (../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams User Activity Report in der Microsoft-Teams-Verwaltungskonsole mit nummerierten Beschriftungen")

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |User Activity Report Teams kann über die letzten 7 Tage oder 28 Tage nach Trends angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die x-Achse auf Diagramme ist des ausgewählten Datumsbereichs für den Bericht an. </li><li>Die y-Achse ist die Anzahl der Benutzer die Aktivität beteiligt sind.</li></ul>Bewegen Sie den Mauszeiger über den Punkt, das eine Aktivität auf einem vorgegebenen Datum sehen Sie die Anzahl der Instanzen dieser Aktivität an diesem bestimmten Datum darstellt. |
|**4**   |Sie können filtern, was Sie im Diagramm angezeigt, indem Sie auf ein Element in der Legende. Klicken Sie beispielsweise **1:1-anrufen**, **DDE-Kanal-Nachrichten**oder **Nachrichten Chat** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Ändern die Auswahl ändert nicht die Informationen in der Tabelle. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Auslastung durch Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können den Anzeigenamen So wechseln zur Seite des Benutzers in der Verwaltungskonsole von Microsoft-Teams klicken.</li><li>**1:1-anrufen** ist die Anzahl der 1:1-Anrufe, die der Benutzer teilgenommen während des angegebenen Zeitraums.</li><li>**DDE-Kanal-Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer gebucht in einem Chat Team während des angegebenen Zeitraums.</li> <li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums veröffentlicht.</li>  <li>**Letzte Aktivität** ist das Datum der letzten (UTC), das der Benutzer in einer Aktivität Teams verwendet wurde.</li> </ul>Um die Informationen anzeigen, die Sie in der Tabelle möchten, stellen Sie sicher, dass Sie die Spalten der Tabelle hinzufügen.
|**6**   |Wählen Sie zum Hinzufügen oder Entfernen von Spalten in der Tabelle **Spalten bearbeiten** . |
|**7**   |Wählen Sie **˙˙˙**, und **druckt Diagramm** , das Diagramm gedruckt. |

## <a name="related-topics"></a>Verwandte Themen
- [Teams Analysen und Berichte](teams-reporting-reference.md)
- [Bericht zur Verwendung der Teams](teams-usage-report.md)
- [Bericht zur Verwendung der Teams Gerät](device-usage-report.md)