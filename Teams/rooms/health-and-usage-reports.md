---
title: Integritäts- und Nutzungsberichte
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Reporting node data for health and usage of reports
f1keywords: ''
ms.openlocfilehash: 400da9dca104bb5ff743a8c032d3997bd282e25a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757128"
---
# <a name="health-and-usage-reports"></a>Integritäts- und Nutzungsberichte

Der Berichterstellungsknoten enthält Daten für den Status und die Nutzung Ihrer verwalteten Microsoft-Räume und Diensterkenntnisse. **Die 

**Übersicht** zeigt mandantenweite Integritätstrends Ihrer Räume. Auf der Registerkarte " **Integrität** " wird eine Liste der Räume mit den entsprechenden Integritätsdaten angezeigt. Die Raumnutzung basierend auf Kalenderinformationen und Anrufqualitätsdaten wird auf der Registerkarte **"Nutzung"** angezeigt.
## <a name="navigating-reports"></a>Navigieren in Berichten

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

Im Abschnitt "Übersicht" werden wichtige Aspekte der Besprechungsraumverwaltung grafisch dargestellt. Die Diagramme ändern sich je nach ausgewählter Zeitspanne oder ausgewählter Gruppe. Um die Zeitspanne zu ändern, klicken Sie auf das Dropdownmenü.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

Um die Gruppe zu ändern, klicken Sie im Banner auf das Dropdownmenü "Gruppenauswahl".

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>Tickets nach Kategorie

Der Donut zeigt die Gesamtanzahl der Tickets an, die für den ausgewählten Zeitraum und die ausgewählte Gruppe ausgelöst wurden (Standardwert sind sieben Tage, alle Gruppen). Tickets werden in den Hauptkategorien "Audio", "Anzeige", "Peripheriegeräte", "Konnektivität", "Versionsverwaltung" und "Kunde gemeldet" dargestellt.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

Bei Auswahl wird ein Flyout für die detaillierte Ansicht für Tickets dieser Kategorie angezeigt.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

Im Flyout ist es möglich, die Ticketliste nach der Unterkategorie zu filtern, indem der jeweilige Teil des Donuts ausgewählt wird. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

Um zurück zu navigieren, klicken Sie entweder auf den Donut oder oben links auf den Breadcrumb.

Um zu einem bestimmten Ticket in dieser Listenansicht zu navigieren, klicken Sie auf den Link unter dem **Supportticket-Colum**.
### <a name="ticket-history"></a>Ticketverlauf

Das Ticketverlaufsdiagramm zeigt einen Vergleich der Vorfälle, die Ihnen oder Microsoft über den angegebenen Zeitraum zugewiesen wurden.

> [!NOTE]
> Wenn ein Ticket an einem Tag den Besitzer ändert, wird das Ticket für den Großteil des Tages gezählt, wer die Zuordnung besitzt. Wenn Sie das Ticket z. B. zu einem frühen Zeitpunkt des Tages zu Microsoft zuweisen, zählt das Ticket in Richtung **"Microsoft** zugewiesen" für den Tag.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->
### <a name="health-history"></a>Integritätsverlauf

Dieses Diagramm zeigt die durchschnittliche Integrität (Definition im Abschnitt "Integrität") für alle Räume im Mandanten sowie die durchschnittliche Integrität für alle MMR-Kunden auf täglicher Basis. Sie können die durchschnittliche Integrität für bis zu 90 Tage anzeigen.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->
### <a name="most-reliableleast-reliable-rooms"></a>Die zuverlässigsten/am wenigsten zuverlässigen Räume:

Zwei Tabellen zeigen die zuverlässigsten und am wenigsten zuverlässigen Räume basierend auf der Gesundheit. Wählen Sie für die vollständige Listenansicht "Integrität" aus, und sortieren Sie die Liste nach der Spalte "Integrität".

### <a name="rooms-history"></a>Chatroomverlauf: 
Bietet eine historische Ansicht der im Dienst registrierten Räume und bietet eine vergleichende Ansicht der Räume, die im selben Zeitraum fehlerfrei oder nicht überwacht wurden.
## <a name="health"></a>Integrität

Um zum Integritätsbericht für alle Räume zu navigieren, wählen Sie "Berichte" und dann "  **Integrität**" aus.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

Bei der Integritätsbewertung handelt es sich um eine Metrik, die dazu bestimmt ist, Räume anzuzeigen, die am wahrscheinlichsten zu Frustration bei Endbenutzern führen. Ein Raum kann für einen bestimmten Tag entweder gesund oder ungesund sein. Es gilt als ungesund, wenn ein Ticket oder viele Tickets den Raum während der Nichtwartungszeit (Ortszeit 5:00 -21:00 Uhr) für mehr als 20 Minuten beeinträchtigt haben. Wenn beispielsweise ein Ticket um 5:00 Uhr geöffnet, aber um 5:15 Uhr geschlossen wird, gilt der Raum weiterhin als fehlerfrei. Wenn jedoch ein zweites Ticket von 09:00 Uhr bis 9:10 Uhr aufgetreten wäre, würde der Raum für den Tag als ungesund angesehen. Wenn ein Ticket von 5:00 Uhr bis 05:21 Uhr aufgetreten ist, gilt es für den Tag als fehlerhaft.

> [!NOTE]
> Die Integrität für den Tag wird einmal täglich um 12:00 Uhr UTC-Zeit aggregiert. Bei Kunden in der Nähe der internationalen Datumszeile kann die Integritätsaggregation in der Mitte des Arbeitstags auftreten.

> [!NOTE]
> Räume, die integriert werden, werden für die Liste der Räume auf der Registerkarte "Integrität" ausgeblendet und zählen nicht zur durchschnittlichen Integrität des Mandanten.

Wenn Sie auf einen raum klicken, der in dieser Ansicht aufgeführt ist, werden weitere Details angezeigt.

Das Balkendiagramm zeigt die Anzahl der Tickets an jedem Tag an. Die an dem jeweiligen Tag geöffneten Tickets werden blau angezeigt. Vor dem jeweiligen Tag geöffnete Tickets werden in Orange angezeigt. Wenn Sie auf einen Tag im Diagramm klicken, werden das Kreisdiagramm und die Tabelle auf die relevanten Tickets gefiltert. Um den Filter umzukehren, navigieren Sie mit den Breadcrumbs, oder klicken Sie auf das Diagramm.

Die Kategorisierung von Tickets wird im Donutdiagramm dargestellt. Die Interaktion mit diesem Filter filtert das Zeitachsendiagramm und die Tabelle. Um den Filter umzukehren, navigieren Sie mit den Breadcrumbs, oder klicken Sie auf das Diagramm.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

In der Ansicht "Auswirkungen auf die Besprechung" werden geplante Besprechungen angezeigt, bei denen ein Ticket mit dem Schweregrad "Wichtig" oder "Kritisch" geöffnet war. Ziel dieser Ansicht ist es, eine Annäherung an Besprechungen bereitzustellen, bei denen die Teilnehmer Probleme haben könnten.

In der Ansicht "Auswirkungen auf die Besprechung" werden geplante Besprechungen angezeigt, bei denen ein Ticket mit dem Schweregrad "Wichtig" oder "Kritisch" geöffnet war. Ziel dieser Ansicht ist es, eine Annäherung an Besprechungen bereitzustellen, bei denen die Teilnehmer Probleme haben könnten.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

Auf der Registerkarte "Einstellungen" werden die Metadaten des Chatrooms angezeigt, z. B. Hardwareinformationen, Geräteeinstellungen, BIOS-Informationen, App-Einstellungen und Speicherort.

## <a name="usage"></a>Verwendung

Um den Nutzungsbericht für alle Räume anzuzeigen, wählen Sie **"Berichte >Nutzung**" aus.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

Die Schlagzeilen geben ein paar Einblicke:

- Gesamtanzahl der Räume in Ihrem Mandanten
- Wie viele haben keine gebuchten Besprechungen, entweder offline oder online?
- Prozentsatz der Auslastung von Räumen im gesamten Mandanten
- Gesamtanzahl der gebuchten Besprechungen über Exchange
- Prozentsatz der gebuchten Besprechungen, die einen Skype- oder Teams-Link enthielten
- Gesamtzahl der Anrufe mit Raumteilnahme
-   Aggregierte Anrufleistungsbewertung von allen Anrufen, die mit der Qualität "Gut" klassifiziert wurden, für alle Anrufe. 

Unterhalb der Überschriftenmetriken befindet sich eine Tabelle mit Räumen mit entsprechenden Metriken. Wählen Sie einen Raum aus, um weitere Nutzungsdetails anzuzeigen. Die Metriken in der Tabelle werden in der folgenden Tabelle beschrieben.

| Spalte |  Beschreibung |
|--------| -------------------|
| Nutzung   | Prozentsatz der Zeit, in der der Raum während der Geschäftszeiten im ausgewählten Zeitraum gebucht wurde. Ex. Zeitraum auf 7 Tage festgelegt. 80% Nutzung über die Mittel, die das Zimmer für 32/40 Stunden gebucht wurde |
| Online gebucht |   Von den gebuchten Besprechungen, deren Prozentsatz mit Teams aktiviert wurde. Ex. 10 Besprechungen wurden gebucht. Davon hatten 8 einen Teams Link. Online gebucht = 80% |
| Geplante Besprechungen | Absolute Anzahl der im Raum geplanten Besprechungen |
| Gesamtzahl der Anrufe | Absolute Anzahl der Anrufe mit dem Raum als Teilnehmer. |
Anrufleistung |  Prozentsatz der Anrufe mit der Bewertung "Gut". Jeder Anruf wird ausgewertet und erhält die Bewertung "Gut", "Schlecht", "Unbekannt". Diese Metrik wird aus guten Anrufen/Gesamtaufrufen berechnet. |

Die Nutzung wird am Ende jedes Tages um Mitternacht (00:00 Uhr) Ortszeit des Besprechungsraumgeräts berechnet. Die Auslastung wird basierend auf der gesamt gebuchten Besprechungszeit für diesen Tag dividiert durch 8 Stunden berechnet.
## <a name="usage-details-of-a-room"></a>Nutzungsdetails eines Raums
 
Wenn Sie in der Listenansicht auf einen Raum klicken, wird ein Flyout mit detaillierteren Informationen angezeigt. Unter der Registerkarte "Nutzung" des Flyouts befindet sich ein Diagramm, in dem die Nutzungszeit der letzten fünf Werktage angezeigt wird. Für jeden Tag gibt es zwei Balken: Blau stellt die gebuchte Besprechungszeit dar; Lila steht für die geplante Zeit Teams/Skype aktivierten Besprechungen. Unten werden die durchschnittlichen Besprechungsbuchungen und die Dauer der letzten fünf Werktage berechnet.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

**Die** Anruftabelle zeigt Besprechungen an, an denen der Raum an einem Teams Anruf teilgenommen hat. Die Raumaudioqualität wird nur für den Raum ausgewertet, nicht für alle Teilnehmer. Um die Anrufqualität für alle Teilnehmer eines bestimmten Anrufs anzuzeigen, wählen Sie einen Anruf aus, indem Sie auf die Startzeit klicken. 

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

Wenn Sie Datenstromdetails für den Raum anzeigen möchten, klicken Sie auf die Sitzungsstartzeit.