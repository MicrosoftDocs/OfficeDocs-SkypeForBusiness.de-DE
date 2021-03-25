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
ms.openlocfilehash: 5f01d71a119116268c5d03850e5e1d26a54ae8dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116853"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" bietet Einblicke in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams unternehmen. Sie können durch ungeplante Besprechungen (1:1 und Gruppenanrufe) sehen, wie viele Benutzer ungeplant kommunizieren. Sehen Sie sich an, wie viele Besprechungen ein Teams-Benutzer organisiert hat und an welchen Besprechungen ein Teams-Benutzer teilgenommen hat. Sehen Sie sich Details zu Bildschirm-, Video- und Audiominuten sowie Statistiken zur Chatkommunikation an, z. B. wie viele Benutzer auf Nachrichten antworten und Kanalnachrichten posten und wie viele Benutzer 1:1- oder Gruppenchatnachrichten verwenden.

## <a name="view-the-user-activity-report"></a>Anzeigen des Berichts "Benutzeraktivität"

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers die Option **Analytics & Berichte**  >  **Verwendungsberichte aus.** Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Teams-Benutzeraktivität aus.**
2. Wählen **Sie unter Datumsbereich** einen Bereich und dann **Bericht ausführen aus.**

    ![Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Benutzeraktivität" kann für Trends in den letzten 7 Tagen, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. In den Berichten wird in der Regel eine 24-Stunden-Latenz ab dem Zeitpunkt der Aktivität widergespiegelt. |
|**3**   |Zeitreihendatenpunkte im Diagramm zeigen unterschiedliche Nutzungsmetriken an, die beim Mandanten aggregiert werden. |
|**4**   |Tabellarische Daten stellten unterschiedliche Nutzungsmetriken pro Benutzer zusammen. |
|**5**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**6**   | Jede der Metriken, die in Diagrammen auf Mandantenebene dargestellt werden. Filtern Sie, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen **Sie Kanalnachrichten,** **Antworten,**  **Chatnachrichten** oder **Organisierte** Besprechungen aus, um informationen zu den einzelnen Nachrichten zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**7**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Wählen Sie den Anzeigenamen aus, um zur Seite "Benutzerdetails" im Microsoft Teams Admin Center zu wechseln.</li><li>**Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Antworten ist** die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li> <li>**Posten von** Nachrichten ist die Anzahl der eindeutigen Beiträge, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums gepostet hat.</li><li>**"Dringende** Nachrichten" ist die Anzahl der dringenden Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>**Die Summe der organisierten** Besprechungen ist die Summe einer <em></em> geplanten, wiederkehrenden, ungeplanten und nicht klassifizierten Besprechung, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die einmal organisiert werden,** sind die Anzahl der einmal geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die regelmäßig organisiert werden,** sind die Anzahl der besprechungsserienbesprechenden Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Adhoc organisierte** Besprechungen sind die Anzahl der ungeplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Die Gesamtzahl der** teilgenommenen Besprechungen ist die Summe der einmal <em></em> geplanten, wiederkehrenden, nicht geplanten und nicht klassifizierten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Besprechungen, die einmal geplant wurden,** ist die Anzahl der einmal geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Besprechungen, die an geplanten Besprechungen** teilgenommen haben, ist die Anzahl der besprechungsserienbesprechenden Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Anzahl der nicht** geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**1:1-Anrufe** sind die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Audiozeit** ist die Gesamtaudiozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Videozeit** ist die Gesamte Videozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Bildschirmfreigabezeit** ist die Gesamte Bildschirmfreigabezeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.</li><li>**Andere Aktivitäten** verfolgt, wenn der Benutzer als aktiv gilt, aber für Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und organisierte Besprechungen den Wert null hat. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanalnachrichtenbeitrag öffnet, aber nicht darauf antwortet, oder wenn ein Benutzer eine private Nachricht empfängt und liest, aber nicht darauf antwortet.</li> <li>**Nicht klassifizierte Besprechungen** sind die Besprechungen, die nicht als Terminplan, Besprechungsserie oder ungeplant klassifiziert werden können. Diese Zahlen sind kurz und können aufgrund manipulierter Telemetrieinformationen meist nicht identifiziert werden.</li> </ul>**Gruppenanrufe** wurden durch **adhoc** organisierte Besprechungen ersetzt, **an deren Besprechungen adhoc teilgenommen wurde.** Die Summe dieser beiden Werte entspricht dem, was durch **Gruppenaufrufe gemessen wurde.**
|**8**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie Nach Excel exportieren** aus, und wählen Sie dann auf der Registerkarte **Downloads** die Option **Herunterladen** aus, um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte Downloads mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen,  wird auch eine ID-Spalte angezeigt, die die Benutzer-ID darstellt. Eine Benutzer-ID ist in der Regel eine alphanumerische Zeichenfolge. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)