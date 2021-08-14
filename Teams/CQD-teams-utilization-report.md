---
title: Anzeigen Microsoft Teams Nutzung in Power BI mithilfe von AQD-Daten
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
description: Verwenden Sie die Teams-Power BI, um auf Microsoft Teams Anrufqualitätsdashboard-Daten zu zugreifen, um die Microsoft Teams in Ihrer Organisation nachverfolgt.
ms.openlocfilehash: e32d321383621b4a961856ad091ba0497e41d7b27fa32925987a8bb093c7fc91
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352503"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Anzeigen Microsoft Teams Nutzung in Power BI mithilfe von AQD-Daten

Neu im März 2020 ist, dass wir unseren herunterladbaren Power BI-Abfragevorlagen für das [AQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen Bericht Teams Nutzung hinzugefügt haben. 

In den neuen berichten Teams Nutzungsberichte können Sie sehen, wie (und in welchem Prozent) Ihre Benutzer Microsoft Teams verwenden, indem Sie auf die Daten des Teams-Anrufqualitäts-Dashboards (AQD) zugreifen. Diese Berichte sollen ein zentraler Speicherort sein, zu dem Administratoren und Führungskräfte schnell auf diese Daten umgehen können.

Der bericht Teams "Power BI" besteht aus zwei primären Berichten: Zusammenfassung der Anrufanzahl **[und](#call-count-summary-report)** **[Zusammenfassung der Audiominuten.](#audio-minutes-summary-report)** Die [Berichte Tägliche Verwendung,](#daily-usage)Regionale [](#user-list) [Audiodetails,](#regional-audio-details) [Konferenzdetails](#conference-details) und Benutzerliste werden ins Spiel kommen, wenn ein Benutzer die Drilldownberichte nutzt, die in den folgenden Beschreibungen aufgeführt sind.

> [!NOTE]
> Gebäude- und Subnetzdaten müssen aufgefüllt werden, um regionale Filterfunktionen und Netzwerkfilterfunktionen bereitstellen zu können.

## <a name="call-count-summary-report"></a>Zusammenfassungsbericht für die Anrufanzahl

Auf der Hauptseite (Anrufanzahl-Zusammenfassung) wird sofort die Anzahl der Audio-, Video- und Bildschirmfreigabesitzungen für die letzten 30 und 90 Tage angezeigt, wie im Abschnittstitel angegeben. Die anfänglich angezeigten Daten sind für die gesamte Organisation und können mithilfe der Datenschnitt-Dropdownoptionen auf der linken Seite der Seite gefiltert werden.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report1.png)

1. Rechts neben den Datenschnittdropdowns ist die Anzahl der Aufrufe nach Medientyp während der letzten 30 Tage in eine interne/externe Ansicht aufgeschlüsselt. Der Screenshot oben zeigt, dass von außerhalb der Organisationsstandorte mehr Anrufe kommen, was unter Berücksichtigung der aktuellen globalen Umgebung sinnvoll ist.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report2.png)

1. Rechts neben dem Feld Anzahl der Medientypen wird die Monatliche Anrufanzahl nach Medientyp für die letzten 90 Tage angezeigt. Sie können mit der Maus auf jede Spalte und jeden Medientyp zeigen, um die Anzahl für einen vorherigen Monat oder den aktuellen Monat bis zum aktuellen Datum mit Informationen zum Verwendungstrend anzeigen.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report3.png)
 

1. Das mittlere Diagramm funktioniert wie das 90-Tage-Diagramm, bietet jedoch eine tägliche Nutzungsansicht für die letzten 30 Tage und ermöglicht es dem Benutzer, mit der rechten Maustaste zu klicken und Details für einen bestimmten Tag anzuzeigen.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report4.png)

Im unteren linken Abschnitt der Seite finden Sie eine Tabelle, in der die Gesamtwerte für jeden Medientyp im vergangenen Jahr enthalten sind. 
    ![Screenshot: Teams der ](media/CQD-teams-utilization-report5.png) ![ Nutzungsberichte: Teams Nutzungsberichte](media/CQD-teams-utilization-report6.png)   

Rechts neben der Tabelle zeigt ein Balkendiagramm Clients an, die in den letzten 30 Tagen am häufigsten (Anrufe/Datenströme) verwendet wurden.
   ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report7.png)

Im letzten Diagrammsatz für diese Seite wird jeder Medientyp einzeln angezeigt, mit einer Aufschlüsselung der Konferenz- und P2P-Nutzung. Die folgenden Diagramme zeigen, dass die Konferenznutzung im Vergleich zu P2P wesentlich höher ist.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Zusammenfassungsbericht für Audiominuten

Im Bericht Audiominutennutzung wird die gesamte Minutennutzung in verschiedenen Ansichten bereitgestellt. 

Die 30-Tage-Nutzungszusammenfassung wird neben den Datenschnitten so angezeigt, dass Textfelder einfach zu verwenden sind. Die oberste Zahl zeigt die Gesamtzahl der 30 Tage an, mit internen und externen Aufschlüsselungen darunter.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report9.png)

Das obere rechte Balkendiagramm bietet eine jahreslange Ansicht der Audioverwendung von Konferenzdaten. Zeigen Sie mit der Maus auf den Monat, um die Audiominuten der Konferenz zu sehen.

Um den Unterschied in P2P- und Konferenzaudio zu zeigen, werden im Diagramm unten links alle Audiodaten des letzten Jahres verwendet und zwischen den beiden Typen aufteilt.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report10.png)

Das letzte Diagramm für die Seite Audiominuten zeigt die Nutzung der Audiominuten bei einer globalen Kartenüberlagerung. Dieses Diagramm funktioniert nur, wenn Gebäude- und Subnetzdaten in den Mandanten hochgeladen werden. Die Überlagerung des Kreisdiagramms auf der Karte kann eingeblendet werden, um anschließend eine regionale Audioverwendung zu bieten.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Drillthroughfunktionen

Wie bereits erwähnt, können Benutzer einen Drilldown in die täglichen und regionalen Nutzungsberichte erstellen.

### <a name="daily-usage"></a>Tägliche Nutzung

Der Bericht "Tägliche Nutzung" ermöglicht es einem Administrator, Spitzennutzungszeiträume im Laufe eines Tages zu ermitteln. Zusätzlich zur Nutzung können wir auch das allgemeine Benutzerverhalten und das Feedback für diesen Tag erfassen.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report12.png)

Der tägliche Verwendungsbericht zeigt die Anzahl der Audio-, Video- und Bildschirmfreigaben für den ausgewählten Tag mit der zusätzlichen Möglichkeit an, zwischen internen und externen Verbindungen zu unterscheiden. Eine Aufschlüsselung von Konferenz und Peer-zu-Peer befindet sich direkt rechts neben dem Feld modality total (Gesamtmodalitäten). Oben rechts im Bericht finden Sie eine Liste der Konferenzen mit der zugehörigen ID und den Teilnehmern für den jeweiligen Tag. Die Konferenzliste bietet außerdem einen zusätzlichen Drilldown zum Bericht Konferenzdetails. GRAFIK ERSETZEN

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report13.png)

Mit dem Balkendiagramm im Mittelbereich kann der Benutzer Höchstwerte im Tagesverlauf erkennen. Benutzer können einen Drilldown in die Im Diagramm dargestellte Stunde anzeigen, in der der Benutzerlistenbericht für die Stunde angezeigt wird.

Rechts neben dem Balkendiagramm wird Benutzerfeedback in einem visuellen Format dargestellt. Zwar können Benutzerstimmungen subjektiv sein, sie bieten jedoch Einblicke, mit deren Hilfe potenzielle Probleme ermittelt werden können.

Die untere Tabelle enthält eine Reihe von Metriken für den Tag. Schlechte Prozentsätze zusammen mit Fehlerraten können für Administratoren potenzielle Verbesserungsbereiche bereitstellen. Jede Stunde kann auch einzeln ausgewählt werden, wie unten dargestellt.

Diese Daten können verwendet werden, um Regionen zu identifizieren, die während Spitzenzeiten Probleme haben.


Klicken Sie auf die Spalte für diesen Tag, um Metriken für diese Stunde anzuzeigen.
![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report14.png)
  
  1.  In der Tabelle unter dem Diagramm werden die Metriken für diese Stunde angezeigt. Dies kann nach einer beliebigen Spaltenüberschrift sortiert werden. wir wären jedoch daran interessiert, problematische Bereiche zu finden.  
    ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report15.png)
    
  2.  Wir sehen, dass in der IND-Region während dieses Zeitrahmens eine schlechte Videoleistung in Konferenzen auftritt. Anschließend können die Microsoft-Berichte im AQD-QER verwendet werden, um den problematischen Ort bei der Erkennen der Region und des Zeitrahmens zu eindärg zu machen.

### <a name="conference-details"></a>Konferenzdetails

Der Bericht Konferenzdetails bietet zusätzliche Einblicke in Besprechungen, von einer Teilnehmerliste bis zu den während der Sitzung verwendeten Medientypen.

Klicken Sie mit der rechten Maustaste auf die Teilnehmerleiste im Konferenz-ID-Diagramm auf der Seite Tägliche Verwendung, um einen Drilldown in die Konferenzdetails zu erhalten.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report24.png)

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report25.png)
  

Wir können die Teilnehmer der Konferenz sowie alle relevanten Informationen bis hin zu Paketverlust und Jitter zur Unterstützung potenzieller Problembehandlungsschritte in der unteren Tabelle sehen.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Regionale Audiodetails

Der Drilldown regionale Audiodetails zeigt speziell die Audiominutenverwendung für die ausgewählte Region. Benutzer mit Zugriff auf das AQD können Nutzungstrends für P2P- und Konferenzaudio in der ausgewählten Region sehen.

1.  Führen Sie auf der Seite Anrufanzahl-Zusammenfassung einen Drillthrough bis zu einem bestimmten Bereich durch die Tabelle aus.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report16.png)

2.  Wählen Sie die Zeile mit der Region aus, für die zusätzliche Informationen erforderlich sind.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report17.png)

3.  Die Datentrends zeigen, dass sehr viele Minuten im internen Netzwerk verwendet werden, bei Konferenzen ist die P2P-Nutzung weit verbreitet.
  ![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report18.png)

Der regionale Audiotrend kann verwendet werden, um zu zeigen, wie sich externe Einflusse auf die Welt auf Benutzer auswirken. Insbesondere würden wir derzeit davon aus gehen, dass sich die externe Nutzung für die Regionen EMEA und APAC erhöht, wenn die Mitarbeiter zur Remotearbeit aufgefordert werden.


### <a name="user-list"></a>Benutzerliste

Wie zu erwarten, werden mit dem Drilldown zur Benutzerliste benutzerspezifische Informationen für eine bestimmte Stunde angezeigt, die von der Person ausgewählt wurde, die den Bericht angezeigt hat. Auf den Bericht Benutzerliste kann über einen Drilldown im Diagramm Stündlich-Trends im Bericht tägliche Verwendung zugegriffen werden. Klicken Sie mit der rechten Maustaste auf die Stunde, für die zusätzliche Informationen erforderlich sind, und wählen Sie Drillthrough und Benutzerliste aus, wie unten dargestellt.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report19.png)

Im Bericht Benutzerliste werden interne/externe Konnektivität durch das Ringdiagramm in der oberen Mitte der Seite angezeigt. In der abbildung unten sehen Sie, dass ein großer Teil der Teilnahme außerhalb des Unternehmensnetzwerks besteht.

Oben rechts im Diagramm wird die Anzahl der Anrufe angezeigt, die von jedem Benutzer innerhalb dieser Stunde vorgenommen wurden.

![Screenshot: Teams Bericht zur Nutzung](media/CQD-teams-utilization-report20.png)

Die untere Tabelle enthält detaillierte Informationen zu den Sitzungen, an den jeder Benutzer während dieser Stunde teilgenommen hat. Die Spalte Fehlertyp ist nützlich, um zu ermitteln, was zu einem Drop-Aufruf führte. Die Spalten "Aufnahmegerät" und "Rendergerät" sind hilfreich, um zu ermitteln, warum ein Anruf mit einer schlechten Qualität gemeldet wurde.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
