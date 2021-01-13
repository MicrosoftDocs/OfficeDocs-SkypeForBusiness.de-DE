---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie den Bericht "Teams-Benutzeraktivität" im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Teams verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85d907e527f8b957abf1a5f3b8b9f0d8c5f44443
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809195"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" bietet Einblicke in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams ausführen. So kann man beispielsweise sehen, wie viele Benutzer ad hoc über ungeplante Besprechungen kommunizieren, die häufig als 1:1 bezeichnet werden, und Gruppenanrufe, Besprechungen, die ein Benutzer von Teams organisiert hat, und Besprechungen, an der ein Teambenutzer teilgenommen hat. Wir teilen Details zu Bildschirm-, Video- und Audiominuten sowie Chatkommunikationsstatistiken, z. B. wie viele Benutzer Kanalnachrichten beantworten und posten und wie viele Benutzer 1:1- oder Gruppenchatnachrichten verwenden.

## <a name="view-the-user-activity-report"></a>Anzeigen des Benutzeraktivitätsberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](https://docs.microsoft.com/microsoftteams/using-admin-roles).

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf "Analysefunktionen&   >  **Verwendungsberichte.** Wählen Sie **auf der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"Teams-Benutzeraktivität" aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht "Teams-Benutzeraktivität" werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität an. |
|**3**   |<ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. </li><li>Die Y-Achse gibt die Anzahl der Benutzer an, die an der Aktivität teilnehmen.</li></ul>Zeigen Sie mit der Maus auf den Punkt, der eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieser Aktivität an diesem angegebenen Datum zu sehen. |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **"1:1-Anrufe",** **"Kanalnachrichten"** oder **"Chatnachrichten",** um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern der Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Benutzer.   <ul><li>**"Benutzername"** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Bei Kanalnachrichten** handelt es sich um die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</li><li>**"Antwortnachrichten"** ist die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li> <li>**Bei "Nachrichten** posten" handelt es sich um die Anzahl der eindeutigen Beitrage, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Chatnachrichten** sind die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li><li>**Bei dringenden** Nachrichten handelt es sich um die Anzahl der dringenden Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>**Die Gesamtanzahl der** geplanten und ad-hoc-Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Bei organisierten** Besprechungen handelt es sich um die Anzahl der geplanten und ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Bei geplanten Besprechungen** handelt es sich um die Anzahl der geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Bei Besprechungen, die adhoc** organisiert werden, handelt es sich um die Anzahl von Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Die Teilnahme an** Besprechungen ist die Anzahl der geplanten und der Ad-hoc-Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Bei den geplanten Besprechungen** handelt es sich um die Anzahl der geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Teilnahme an Besprechungen** ist die Anzahl der Ad-hoc-Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**1:1-Anrufe** sind die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Audiozeit** ist die Gesamtaudiozeit, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Videozeit** ist die Videozeit, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Bildschirmfreigabezeit ist** die Gesamtdauer der Bildschirmfreigabe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teamaktivität teilgenommen hat.</li><li>**Andere Aktivitäten** werden verfolgt, wenn der Benutzer als aktiv betrachtet wird, aber für Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und organisierte Besprechungen den Wert 0 hat. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanalnachrichtenbeitrag öffnet, aber nicht darauf antwortet, oder wenn ein Benutzer eine private Nachricht empfängt und diese liest, aber nicht darauf antwortet.</li> </ul>Beachten **Sie,** dass Gruppenanrufe durch **"Adhoc** organisierte" und "Besprechungen" ersetzt wurden, an denen die Summe dieser beiden Werte entspricht, was durch Gruppenanrufe **gemessen wurde.** 
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf "Nach Excel exportieren",** und klicken Sie dann auf der Registerkarte **"Downloads"** auf "Herunterladen", um den Bericht herunterzuladen, sobald er bereit ist. <br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen, wird auch eine Spalte **"ID"** angezeigt, die die Team-ID darstellt. Eine Team-ID ist normalerweise eine alphanumerische Zeichenfolge. Wenn die **Spalte "ID"** als **"\n"** angezeigt wird, bedeutet dies, dass ein Benutzer die Daten zum Löschen angefordert hat. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
