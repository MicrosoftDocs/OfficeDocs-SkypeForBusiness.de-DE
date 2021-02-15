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
ms.openlocfilehash: f02d2f8751b8059f435164158d5c97fb6766a286
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196913"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" bietet Einblicke in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams unternehmen. Sie können in ungeplanten Besprechungen (1:1 und Gruppenanrufen) sehen, wie viele Benutzer ungeplant kommunizieren. Sehen Sie sich an, wie viele Besprechungen ein Benutzer von Teams organisiert hat und an welchen Besprechungen ein Benutzer teilgenommen hat. Zeigen Sie Details zu Bildschirm-, Video- und Audiominuten sowie Statistiken zur Chatkommunikation an, z. B. wie viele Benutzer Kanalnachrichten beantworten und posten und wie viele Benutzer 1:1- oder Gruppenchatnachrichten verwenden.

## <a name="view-the-user-activity-report"></a>Anzeigen des Benutzeraktivitätsberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](https://docs.microsoft.com/microsoftteams/using-admin-roles).

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers die Option **"Analyseanalyse" &**  >  **Verwendungsberichte aus.** Wählen Sie **auf der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"Teams-Benutzeraktivität" aus.**
2. Wählen **Sie unter "Datumsbereich"** einen Bereich und dann "Bericht **ausführen" aus.**

    ![Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht "Teams-Benutzeraktivität" werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. In den Berichten wird in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität widergespiegelt. |
|**3**   |Zeitreihendatenpunkte im Diagramm zeigen unterschiedliche Nutzungsmetriken, die im Mandanten zusammengefasst sind. |
|**4**   |Tabellarische Daten stellten verschiedene Nutzungsmetriken dargestellt, die pro Benutzer zusammengefasst wurden. |
|**5**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**6**   | Jede der Metriken, die im Diagramm auf Mandantenebene dargestellt werden. Filtern Sie, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen **Sie Kanalnachrichten,**  **Antwortnachrichten,** **Chatnachrichten** oder organisierte Besprechungen aus, um die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**7**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Benutzer.   <ul><li>**Der Anzeigename** ist der Anzeigename des Benutzers. Wählen Sie den Anzeigenamen aus, um zur Seite mit den Benutzerdetails im Microsoft Teams Admin Center zu wechseln.</li><li>**Bei Kanalnachrichten** handelt es sich um die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**"Antwortnachrichten"** ist die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li> <li>**Bei "Nachrichten** posten" handelt es sich um die Anzahl der eindeutigen Beitrage, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Chatnachrichten** sind die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li><li>**Bei dringenden** Nachrichten handelt es sich um die Anzahl der dringenden Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>**"Organisierte Besprechungen** insgesamt" ist die Summe einer geplanten, <em></em> periodischen, ungeplanten und nicht klassifizierten Besprechung, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die als einmal geplant organisiert** werden, sind die Anzahl der einmal geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Bei Besprechungen, die eine Serie organisiert** haben, handelt es sich um die Anzahl der Besprechungsserien, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Bei Besprechungen, die adhoc** organisiert werden, handelt es sich um die Anzahl der ungeplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**"Gesamtbesprechungen** teilgenommen" ist die Summe der einmal geplanten, <em></em> wiederkehrenden, ungeplanten und nicht klassifizierten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die einmal geplante Teilnahme an** Besprechungen ist die Anzahl der einmal geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die geplanten Besprechungsserien** sind die Anzahl der besprechungsserienbesprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Teilnahme an Besprechungen** ist die Anzahl der ungeplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**1:1-Anrufe** sind die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Audiozeit** ist die Gesamtaudiozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Videozeit** ist die Videozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Bildschirmfreigabezeit ist** die Bildschirmfreigabezeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teamaktivität teilgenommen hat.</li><li>**Andere Aktivitäten** werden verfolgt, wenn der Benutzer als aktiv betrachtet wird, aber für Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und organisierte Besprechungen den Wert 0 hat. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanalnachrichtenbeitrag öffnet, aber nicht darauf antwortet, oder wenn ein Benutzer eine private Nachricht empfängt und diese liest, aber nicht darauf antwortet.</li> <li>**Nicht klassifizierte Besprechungen** sind diejenigen, die nicht als Terminplan, Besprechungsserie oder ungeplant klassifiziert werden können. Diese sind kurz und können aufgrund manipulierter Telemetrieinformationen meistens nicht identifiziert werden.</li> </ul>**Gruppenanrufe** wurden durch **"Meetings organized adhoc"** ersetzt, an **deren Besprechungen teilgenommen wurde.** Die Summe dieser beiden Werte entspricht dem, was von **Gruppenaufrufen gemessen wurde.**
|**8**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie "Nach Excel exportieren"** und  dann auf der Registerkarte **"Downloads"** die Option "Herunterladen" aus, um den Bericht herunterzuladen, wenn er bereit ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen,  sehen Sie auch eine ID-Spalte, die die Benutzer-ID darstellt. Eine Benutzer-ID ist normalerweise eine alphanumerische Zeichenfolge. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
