---
title: Microsoft Teams – Benutzeraktivitätsbericht
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Teams Bericht "Benutzeraktivität" im Microsoft Teams Admin Center verwenden, um zu sehen, wie Die Benutzer in Ihrer Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd33b28f4157a6ba58ab2c4291bfa4ef558e97ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832989"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Teams Benutzeraktivitätsbericht bietet Einen Einblick in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams. Sie können in ungeplanten Besprechungen (1:1 und Gruppenanrufen) sehen, wie viele Benutzer ungeplant kommunizieren. Sehen Sie sich an, wie viele Teams ein Benutzer organisiert hat und an welchen Teams ein Benutzer teilgenommen hat. Zeigen Sie Details zu Bildschirm-, Video- und Audiominuten sowie Statistiken zur Chatkommunikation an, z. B. wie viele Benutzer Kanalnachrichten beantworten und veröffentlichen und wie viele Benutzer 1:1- oder Gruppenchatnachrichten verwenden.

> [!NOTE]
> Die Möglichkeit, einen Benutzeraktivitätsbericht zu planen, ist derzeit nicht verfügbar.

## <a name="view-the-user-activity-report"></a>Anzeigen des Benutzeraktivitätsberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option **Analyseanalyse**&  >  **Verwendungsberichte aus.** Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option Teams **aus.**
2. Wählen **Sie unter Datumsbereich** einen Bereich aus, und wählen Sie dann **Bericht ausführen aus.**

    ![Screenshot des berichts Teams Benutzeraktivitätsberichts im Teams Admin Center mit Callouts.](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Berichts Teams Benutzeraktivitätsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

| Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Teams Benutzeraktivitätsbericht werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität. |
|**3**   |Die Datenpunkte der Zeitreihen im Diagramm zeigen unterschiedliche Nutzungsmetriken, die im Mandanten zusammengefasst wurden. |
|**4**   |Tabellarische Daten stellten verschiedene Nutzungsmetriken dargestellt, die pro Benutzer zusammengefasst wurden. |
|**5**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**6**   | Jede Metrik, die in Diagramm auf Mandantenebene dargestellt wird. Filtern Sie, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen **Sie Kanalnachrichten**,  **Antwortnachrichten**, **Chatnachrichten** oder Organisierte Besprechungen aus, um die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**7**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Wählen Sie den Anzeigenamen aus, um zur Seite mit den Benutzerdetails im Microsoft Teams Admin Center zu wechseln.</li><li>**Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Antwortnachrichten** ist die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li> <li>**Posten von** Nachrichten ist die Anzahl der eindeutigen Beitragnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li><li>**Dringende** Nachrichten ist die Anzahl der dringenden Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>**Organisierte Gesamtbesprechungen** ist die Summe einer geplanten, wiederkehrenden, ungeplanten und nicht klassifizierten Besprechung, die ein Benutzer während des angegebenen Zeitraums organisiert hat. <em></em></li><li>**Besprechungen, die als "Einmal geplant"** organisiert werden, ist die Anzahl der einmal geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die eine geplante Besprechungsserie** organisieren, ist die Anzahl der Besprechungsserien, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die einDhoc organisieren,** ist die Anzahl der ungeplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Gesamtbesprechungen teilgenommen** ist die Summe der einmal geplanten, wiederkehrenden, ungeplanten und nicht klassifizierten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat. <em></em></li><li>**Die einmal angesetzten Besprechungen** sind die Anzahl der einmal geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die geplante Besprechungsserie ist** die Anzahl der Besprechungsserien, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Besprechungen, an dem ein** Benutzer während des angegebenen Zeitraums teilgenommen hat, ist die Anzahl der nicht geplanten Besprechungen.</li><li>**1:1-Anrufe** sind die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Audiozeit ist** die Gesamtaudiozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Videozeit** ist die Gesamtvideozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Bildschirmfreigabezeit ist** die Gesamte Bildschirmfreigabezeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Aktivität Teams hat.</li><li>**Andere Aktivitäten** werden nach verfolgt, wenn der Benutzer als aktiv betrachtet wird, aber für Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und organisierte Besprechungen den Wert Null besitzt. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanalnachrichtenbeitrag öffnet, aber nicht antwortet, oder wenn ein Benutzer eine private Nachricht empfängt und diese liest, aber nicht darauf antwortet.</li> <li>**Nicht klassifizierte Besprechungen** sind Besprechungen, die nicht als Zeitplan, Besprechungsserie oder ungeplant klassifiziert werden können. Diese sind kurz und können meistens aufgrund von manipulierten Telemetrieinformationen nicht identifiziert werden.</li> </ul>**Gruppenanrufe** wurden durch Besprechungen ersetzt, die **eindhoc** organisiert haben und **an Besprechungen teilgenommen haben.** Die Summe dieser beiden Werte entspricht dem, was durch **Gruppenaufrufe gemessen wurde.**
|**8**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie In Excel** exportieren aus, und  wählen Sie dann auf der Registerkarte **Downloads** die Option Herunterladen aus, um den Bericht herunterzuladen, wenn er bereit ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in einer Excel, wird auch eine **ID-Spalte** angezeigt, die die Benutzer-ID darstellt. Eine Benutzer-ID ist in der Regel eine alphanumerische Zeichenfolge. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisiert benutzerspezifische Daten

Um die Daten in Teams Benutzeraktivitätsbericht anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen (mithilfe von MD5-Hashes) wie Anzeigename, E-Mail-Adresse und AAD-ID im Bericht und beim Export ausgeblendet.

1. Wechseln Microsoft 365 Admin Center In diesem Fenster  zum Einstellungen Org Einstellungen , und wählen Sie unter Registerkarte Dienste die Option \> Berichte **aus.** 
    
2. Wählen **Sie Berichte** aus, und wählen Sie dann **anonyme Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Verwendungsberichte im Microsoft 365 Admin Center als Teams Admin Center angewendet.
  
3. Wählen Sie **Änderungen speichern aus.**

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
