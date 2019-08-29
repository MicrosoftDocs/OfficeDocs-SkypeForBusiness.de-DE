---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Erfahren Sie, wie Sie im Microsoft Teams Admin Center den Bericht "Benutzeraktivitäten für Teams" verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d64937d76ad2b634509972f203992b50eb64ccff
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667091"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" gibt Ihnen einen Einblick in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams ausführen. So können Sie beispielsweise sehen, wie viele Benutzer über 1:1-Anrufe kommunizieren, wie viele Benutzer über Kanal Nachrichten kommunizieren und wie viele Benutzer an privaten Chatnachrichten teilnehmen.

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analyse #a0 Berichte**, und wählen Sie dann unter **Bericht**die Option **Teams-Benutzeraktivität**aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    Screenshot ![des Teams-Benutzer Aktivitätsberichts im Team Admin Center mit Beschriftungen] Screenshot (../media/teams-reports-user-activity-with-callouts.png "des Teams-Benutzer Aktivitätsberichts im Team Admin Center mit Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Benutzeraktivität" kann für Trends in den letzten 7 Tagen oder 28 Tagen angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. </li><li>Die Y-Achse gibt die Anzahl der Benutzer an, die an der Aktivität teilnehmen.</li></ul>Zeigen Sie auf den Punkt, der eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieser Aktivität an diesem angegebenen Datum anzuzeigen. |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **1:1-Anrufe**, **Kanal Nachrichten**oder **Chat Nachrichten** , um nur die Informationen anzuzeigen, die sich auf die einzelnen Einträge beziehen. Wenn Sie die Auswahl ändern, werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Verwendung durch den Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**1:1-Aufrufe** ist die Anzahl von 1:1-anrufen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Kanal Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</li> <li>**Chat Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li>  <li>**Letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Team Aktivität teilgenommen hat.</li> </ul>Beachten Sie, dass der Benutzername in der Tabelle als "--" angezeigt wird, wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen, wird auch eine **ID-** Spalte angezeigt, die die Team-ID darstellt. Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge. Wenn die Spalte " **ID** " als " **\n**" angezeigt wird, bedeutet dies, dass ein Benutzer die Löschung seiner Informationen beantragt hat. ||

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)