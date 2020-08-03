---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie im Microsoft Teams Admin Center den Bericht "Benutzeraktivitäten für Teams" verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Teams verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 907491aab660bacd0b619b385aaef3a9309cc121
ms.sourcegitcommit: 9d60f403b42d2fdef91cdfa3caf50179a49561df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536837"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" gibt Einblicke in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams ausführen. So können Sie beispielsweise sehen, wie viele Benutzer auf Ad-hoc-Basis mit ungeplanten Besprechungen kommunizieren, die gemeinhin als 1:1-und Gruppenanrufe, Besprechungen, die ein Teams-Benutzer organisiert hat, und Besprechungen, an denen ein Team Benutzer teilgenommen hat. Wir geben Details zu Bildschirm-, Video-und audiominuten und Chat-Kommunikationsstatistiken frei, wie beispielsweise, wie viele Benutzer auf Kanal Nachrichten Antworten und diese senden, und wie viele Benutzer an 1:1-oder Gruppen-Chatnachrichten teilnehmen.

## <a name="view-the-user-activity-report"></a>Anzeigen des Benutzer Aktivitätsberichts

Sie müssen ein Team Dienstadministrator sein, um diese Änderungen vornehmen zu können. Informationen zum Abrufen von Administratorrollen und-Berechtigungen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics & Berichte**  >  **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **Teams-Benutzeraktivität**aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Benutzer Aktivitätsberichts im Team Admin Center mit Beschriftungen](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams-Benutzer Aktivitätsberichts im Team Admin Center mit Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Benutzeraktivität" kann für Trends in den letzten 7 Tagen, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. In den Berichten wird normalerweise eine 24-Latenzzeit von der Aktivität reflektiert. |
|**3**   |<ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. </li><li>Die Y-Achse gibt die Anzahl der Benutzer an, die an der Aktivität teilnehmen.</li></ul>Zeigen Sie auf den Punkt, der eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieser Aktivität an diesem angegebenen Datum anzuzeigen. |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **1:1-Anrufe**, **Kanal Nachrichten**oder **Chat Nachrichten** , um nur die Informationen anzuzeigen, die sich auf die einzelnen Einträge beziehen. Wenn Sie die Auswahl ändern, werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Verwendung durch den Benutzer.   <ul><li>**Username** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Kanal Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</li><li>**Antwortnachrichten** ist die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Team Kanal gepostet hat.</li> <li>**Posten Nachrichten** ist die Anzahl der eindeutigen Beitrags Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Team Kanal gepostet hat.</li><li>**Chat Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li><li>**Dringende Nachrichten** ist die Anzahl dringender Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>" **Gesamt Besprechungen** " ist die Gesamtzahl der geplanten und Ad-hoc-Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Organisierte Besprechungen** ist die Anzahl der geplanten und Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>" **Organisierte Besprechungen** " ist die Anzahl der geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>" **Organisierte Besprechungen** " ist die Anzahl der Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Teilnahme an Besprechungen** ist die Nummer der geplanten und der Ad-hoc-Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Geplante Besprechungen** ist die Anzahl der geplanten Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Teilnahme an Besprechungen Adhoc** ist die Anzahl von Ad-hoc-Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**1:1-Aufrufe** ist die Anzahl von 1:1-anrufen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Audiozeit** ist die Gesamt-Audiozeit, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Video Zeit** ist die Gesamt Video Zeit, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>Die **Bildschirmfreigabe Zeit** ist die gesamte Bildschirmfreigabe Zeit, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Team Aktivität teilgenommen hat.</li><li>**Andere Aktivitäten** werden nachverfolgt, wenn der Benutzer als aktiv eingestuft wird, aber für Chatnachrichten, 1:1-Anrufe, Kanal Nachrichten, Gesamt Besprechungen und organisierte Besprechungen einen Wert von NULL aufweist. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanal Nachrichtenbeitrag öffnet, aber nicht darauf antwortet oder wenn ein Benutzer eine private Nachricht empfängt und diese liest, aber nicht darauf reagiert.</li> </ul>Beachten Sie, dass **Gruppenanrufe** durch **Adhoc-Sitzungen** ersetzt wurden und an **Adhoc-Sitzungen teilgenommen**haben, bei denen die Summe dieser beiden Werte dem entspricht, was von **Gruppen anrufen**gemessen wurde.
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen, wird auch eine **ID-** Spalte angezeigt, die die Team-ID darstellt. Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge. Wenn die Spalte " **ID** " als " **\n**" angezeigt wird, bedeutet dies, dass ein Benutzer die Löschung seiner Informationen beantragt hat. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
