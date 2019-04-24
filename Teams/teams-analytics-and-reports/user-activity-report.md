---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
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
ms.openlocfilehash: d5ad6021f03b200e1f3216238a81cc3b691171fd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225034"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Teams User Activity Report bietet Ihnen einen Einblick in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams durchführen. Beispielsweise können Sie sehen, wie viele Benutzer über 1:1-Anrufe zu kommunizieren, wie viele Benutzer über DDE-Kanalnachrichten kommunizieren und wie viele Benutzer private Chatnachrichten beteiligen.

![Screenshot des Teams User Activity Report in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-reports-user-activity.png "Screenshot des Teams User Activity Report in der Verwaltungskonsole von Microsoft-Teams")

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Wechseln Sie zur Microsoft-Teams-Verwaltungskonsole im linken Navigationsbereich auf **Analytics &-Berichte**und wählen Sie dann unter **Bericht** **Benutzeraktivität Teams**. 
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**. 

## <a name="interpret-the-report"></a>Interpretieren des Berichts

![Screenshot des Teams User Activity Report in der Microsoft-Teams-Verwaltungskonsole mit nummerierten Beschriftungen] (../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams User Activity Report in der Microsoft-Teams-Verwaltungskonsole mit nummerierten Beschriftungen")

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |User Activity Report Teams kann über die letzten 7 Tage oder 28 Tage nach Trends angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die x-Achse auf Diagramme ist des ausgewählten Datumsbereichs für den Bericht an. </li><li>Die y-Achse ist die Anzahl der Benutzer die Aktivität beteiligt sind.</li></ul>Bewegen Sie den Mauszeiger über den Punkt, das eine Aktivität auf einem vorgegebenen Datum sehen Sie die Anzahl der Instanzen dieser Aktivität an diesem bestimmten Datum darstellt. |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise **1:1-anrufen**, **DDE-Kanal-Nachrichten**oder **Nachrichten Chat** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Ändern die Auswahl ändert nicht die Informationen in der Tabelle. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Auslastung durch Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können den Anzeigenamen So wechseln zur Seite des Benutzers in der Verwaltungskonsole von Microsoft-Teams klicken.</li><li>**1:1-anrufen** ist die Anzahl der 1:1-Anrufe, die der Benutzer teilgenommen während des angegebenen Zeitraums.</li><li>**DDE-Kanal-Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer gebucht in einem Chat Team während des angegebenen Zeitraums.</li> <li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums veröffentlicht.</li>  <li>**Letzte Aktivität** ist das Datum der letzten (UTC), das der Benutzer in einer Aktivität Teams verwendet wurde.</li> </ul>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**7**   |Wählen Sie **˙˙˙** und dann **Diagramm drucken** aus, um das Diagramm zu drucken. |

## <a name="related-topics"></a>Verwandte Themen
- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Teams-Nutzungsbericht](teams-usage-report.md)
- [Teams-Gerätenutzungsbericht](device-usage-report.md)