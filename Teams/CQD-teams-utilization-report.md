---
title: Anzeigen der Verwendung von Microsoft Teams in Power BI mithilfe von CQD-Daten
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Verwenden Sie die Teams Usage Power BI-Berichte, um auf Microsoft Teams Call Quality Dashboard (CQD)-Daten zu zugreifen, um die Verwendung von Microsoft Teams in Ihrer Organisation zu verfolgen.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095039"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Anzeigen der Verwendung von Microsoft Teams in Power BI mithilfe von CQD-Daten

Neu im März 2020 haben wir unseren herunterladbaren Power BI-Abfragevorlagen für [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen Bericht "Teams-Nutzung" hinzugefügt. 

In diesen neuen Berichten zur Nutzung von Teams können Sie sehen, wie (und wie viel) Ihre Benutzer Microsoft Teams verwenden, indem Sie auf CQD-Daten (Teams Call Quality Dashboard) zugreifen. Diese Berichte sollen ein zentraler Ort sein, an den administratoren und Unternehmensführer schnell zu diesen Daten wechseln können.

Der Power BI-Bericht "Teams-Nutzung" besteht aus zwei primären Berichten: Zusammenfassung der **[Anrufanzahl und](#call-count-summary-report)** **[Zusammenfassung der Audiominuten.](#audio-minutes-summary-report)** Die [Berichte tägliche Nutzung,](#daily-usage)Regionale [](#user-list) [Audiodetails,](#regional-audio-details) [Konferenzdetails](#conference-details) und Benutzerliste werden ins Spiel kommen, wenn ein Benutzer die Drilldownberichte nutzt, die in den nachstehenden Beschreibungen aufgeführt sind.

> [!NOTE]
> Gebäude- und Subnetzdaten müssen aufgefüllt werden, um regionale Filterfunktionen und Netzwerkfilterfunktionen bereitstellen zu können.

## <a name="call-count-summary-report"></a>Zusammenfassungsbericht "Anrufanzahl"

Auf der Hauptseite (Anrufanzahlzusammenfassung) wird sofort die Anzahl der Audio-, Video- und Bildschirmfreigabesitzungen in den letzten 30 und 90 Tagen angezeigt, wie im Abschnittstitel angegeben. Die anfänglich angezeigten Daten sind für die gesamte Organisation und können mithilfe der Dropdownoptionen für Datenschnitte auf der linken Seite gefiltert werden.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report1.png)

1. Rechts neben den Datenschnitt dropdowns wird die Anzahl der Anrufe nach Medientyp in einer internen/externen Ansicht in den letzten 30 Tagen aufschlüsselt. Wir können im obigen Screenshot sehen, dass mehr Anrufe von außerhalb der Organisationsstandorte kommen, was unter Berücksichtigung der aktuellen globalen Umgebung sinnvoll ist.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report2.png)

1. Rechts neben dem Feld Medientypanzahl wird die monatliche Anrufanzahl nach Medientyp für die letzten 90 Tage angezeigt. Jede Spalte und jeder Medientyp kann mit dem Mauszeiger darauf zeigen, um die Anzahl für einen vorherigen Monat oder den aktuellen Monat bis zum aktuellen Datum mit Informationen zum Nutzungstrend zu zeigen.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report3.png)
 

1. Das mittlere Diagramm funktioniert wie das 90-Tage-Diagramm, stellt jedoch eine tägliche Nutzungsansicht für die letzten 30 Tage zur Verfügung und ermöglicht es dem Benutzer, mit der rechten Maustaste zu klicken und einen Drilldown in Details für einen bestimmten Tag zu erstellen.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report4.png)

Im unteren linken Abschnitt der Seite finden Sie eine Tabelle, die die Gesamtwerte für jeden Medientyp im letzten Jahr enthält. 
    ![Screenshot: Berichte zur Nutzung von Teams ](media/CQD-teams-utilization-report5.png) ![ Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report6.png)   

Rechts neben der Tabelle zeigt ein Balkendiagramm Clients an, die in den letzten 30 Tagen am häufigsten verwendet wurden (Anrufe/Datenströme).
   ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report7.png)

Die letzte Gruppe von Diagrammen für diese Seite zeigt jeden Medientyp einzeln an, mit einer Aufschlüsselung, die die Konferenz- und P2P-Nutzung zeigt. Die folgenden Diagramme zeigen, dass die Anzahl der Konferenznutzung im Vergleich zu P2P deutlich höher ist.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Zusammenfassungsbericht "Audiominuten"

Im Nutzungsbericht "Audiominuten" wird die Gesamtminutennutzung über ein paar verschiedene Ansichten bereitgestellt. 

Die 30-tägige Nutzungszusammenfassung wird neben den Datenschnitten als einfach zu verwendende Textfelder angezeigt. Die oberste Zahl zeigt die Gesamtsumme von 30 Tagen mit internen und externen Aufschlüsselungen darunter.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report9.png)

Das Diagramm der oberen rechten Leiste bietet eine jahreslange Ansicht der Audionutzung von Konferenzkonferenzen. Zeigen Sie mit der Maus auf den Monat, um die Audiominuten der Konferenz zu zeigen.

Um den Unterschied bei P2P- und Konferenzaudio zu zeigen, werden im unteren linken Diagramm alle Audiodaten für das vergangene Jahr verwendet und zwischen den beiden Typen aufbricht.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report10.png)

Das letzte Diagramm für die Seite Audiominuten zeigt die Audiominutennutzung auf einer globalen Kartenüberlagerung. Dieses Diagramm funktioniert nur, wenn Gebäude- und Subnetzdaten in den Mandanten hochgeladen werden. Die Kreisdiagrammüberlagerung auf der Karte kann ge drilledert werden, um anschließend die regionale Audionutzung zu bieten.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Drill-Through-Funktionen

Wie bereits erwähnt, können Benutzer einen Drilldown in den täglichen und regionalen Nutzungsberichten erstellen.

### <a name="daily-usage"></a>Tägliche Nutzung

Der Bericht Tägliche Nutzung ermöglicht es einem Administrator, Spitzenverbrauchszeiträume im Laufe eines Tages zu identifizieren. Neben der Nutzung können wir auch die allgemeine Benutzerstimmung und das Feedback für diesen Tag erfassen.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report12.png)

Im Bericht tägliche Nutzung wird die Anzahl der Audio-, Video- und Bildschirmfreigaben für den ausgewählten Tag angezeigt, mit der zusätzlichen Möglichkeit, zwischen internen und externen Verbindungen zu unterscheiden. Eine Aufschlüsselung von Konferenz und Peer zu Peer befindet sich direkt rechts neben dem Gesamtfeld modalität. Oben rechts im Bericht finden Sie eine Liste der Konferenzen mit der zugehörigen ID und den Teilnehmern für den Tag. Die Konferenzliste enthält außerdem einen zusätzlichen Drilldown zum Konferenzdetails-Bericht. ERSETZEN DER GRAFIK

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report13.png)

Das Balkendiagramm im Mittelpunktbereich ermöglicht es dem Benutzer, Spitzenverbrauchszeiträume im Laufe eines Tages zu identifizieren. Benutzer können einen Drilldown auf die im Diagramm dargestellte Stunde machen, in der der Bericht "Benutzerliste" für die Stunde angezeigt wird.

Rechts neben dem Balkendiagramm wird Benutzerfeedback in einem visuellen Format dargestellt. Die Benutzerstimmung kann zwar subjektiv sein, bietet jedoch Einsichten, mit deren Hilfe potenzielle Probleme identifiziert werden können.

Die untere Tabelle enthält einen Bereich von Metriken für den Tag. Schlechte Prozentsätze zusammen mit Fehlerraten können einem Administrator potenzielle Verbesserungsbereiche bieten. Jede Stunde kann auch einzeln ausgewählt werden, wie unten gezeigt.

Diese Daten können verwendet werden, um Regionen zu identifizieren, die zu Spitzenzeiten Probleme haben.


Klicken Sie auf die Spalte für diesen Tag, um Metriken für diese Stunde anzuzeigen.
![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report14.png)
  
  1.  In der Tabelle unterhalb des Diagramms werden die Metriken für diese Stunde angezeigt. Dies kann nach einer beliebigen Spaltenüberschrift sortiert werden. wir wären jedoch daran interessiert, problematische Bereiche zu finden.  
    ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report15.png)
    
  2.  Wir sehen, dass in der IND-Region während dieses Zeitrahmens eine schlechte Videoleistung in Konferenzen auftritt. Anschließend können die CQD-QER-Microsoft-Berichte verwendet werden, um den problematischen Ort zu verengungen, da die Region und der Zeitrahmen identifiziert wurden.

### <a name="conference-details"></a>Konferenzdetails

Der Bericht "Konferenzdetails" bietet zusätzliche Einblicke in Besprechungen, von einer Teilnehmerliste bis zu den während der Sitzung verwendeten Medientypen.

Klicken Sie mit der rechten Maustaste auf die Teilnehmerleiste im Konferenz-ID-Diagramm auf der Seite Tägliche Nutzung, um einen Drilldown zu den Konferenzdetails zu erhalten.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report24.png)

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report25.png)
  

Wir können die Teilnehmer der Konferenz sowie alle relevanten Informationen bis hin zu Paketverlust und Jitter sehen, um potenzielle Problembehandlungsbemühungen in der unteren Tabelle zu unterstützen.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Regionale Audiodetails

Im Drilldown "Regionale Audiodetails" wird speziell die Audiominutennutzung für die ausgewählte Region angezeigt. Benutzer mit Zugriff auf CQD können Nutzungstrends für P2P- und Konferenzaudio in der ausgewählten Region sehen.

1.  Führen Sie auf der Seite Anrufanzahlszusammenfassung einen Drillthrough durch die Tabelle zu einem bestimmten Bereich aus.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report16.png)

2.  Wählen Sie die Zeile mit dem Bereich aus, für den zusätzliche Informationen erforderlich sind.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report17.png)

3.  Die Datentrends zeigen eine erhebliche Anzahl von Minuten, die im internen Netzwerk verwendet werden, und Konferenzen übertreffen die P2P-Nutzung weit.
  ![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report18.png)

Der regionale Audiotrend kann verwendet werden, um zu zeigen, wie Benutzer von externen Einfluss auf die Welt beeinflusst werden. Gerade jetzt erwarten wir, dass die externe Nutzung für die Emea- und APAC-Regionen steigt, und die Mitarbeiter werden aufgefordert, remote zu arbeiten.


### <a name="user-list"></a>Benutzerliste

Der Drilldown "Benutzerliste" enthält, wie zu erwarten, benutzerspezifische Informationen für eine bestimmte Stunde, die von der Person ausgewählt wurde, die den Bericht angezeigt hat. Auf den Bericht "Benutzerliste" kann über einen Drilldown im Diagramm "Stundentrends" im Bericht "Tägliche Nutzung" zugegriffen werden. Klicken Sie mit der rechten Maustaste auf die Stunde, zu der zusätzliche Informationen benötigt werden, und wählen Sie Drill through und Benutzerliste aus, wie unten gezeigt.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report19.png)

Der Bericht Benutzerliste zeigt die interne/externe Konnektivität über das Ringdiagramm in der oberen Mitte der Seite an. In der nachstehenden Abbildung ist zu sehen, dass außerhalb des Unternehmensnetzwerks ein großer Teil der Teilnahme besteht.

Die obere rechte Seite des Diagramms zeigt die Anzahl der Anrufe, die von jedem Benutzer innerhalb dieser Stunde vorgenommen wurden.

![Screenshot: Berichte zur Nutzung von Teams](media/CQD-teams-utilization-report20.png)

Die untere Tabelle enthält detaillierte Informationen zu den Sitzungen, an der jeder Benutzer während dieser Stunde teilgenommen hat. Die Spalte Fehlertyp ist hilfreich, um zu ermitteln, was zu einem Dropaufruf führte. Die Spalten Aufnahme- und Rendergerät sind hilfreich, um zu ermitteln, warum ein Anruf gemeldet wurde, der eine schlechte Qualität hat.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
