---
title: Anzeigen der Nutzung von Microsoft Teams in Power BI mithilfe von CQD-Daten
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Verwenden Sie die Power BI-Berichte zur Teams-Nutzung, um auf CQD-Daten (Call Quality Dashboard) von Microsoft Teams zuzugreifen, um die Nutzung von Microsoft Teams in Ihrer Organisation nachzuverfolgen.
ms.openlocfilehash: bd579fa3f57c6e3b50a363eb77523f577c750efb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270690"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Anzeigen der Nutzung von Microsoft Teams in Power BI mithilfe von CQD-Daten

Der Bericht "Teams-Nutzung" ist als Teil unserer herunterladbaren [Power BI-Abfragevorlagen für CQD](https://www.microsoft.com/download/details.aspx?id=102291) verfügbar. 

In diesem Bericht können Sie sehen, wie (und wie viel) Ihre Benutzer Microsoft Teams verwenden, indem Sie auf CQD-Daten (Call Quality Dashboard) von Teams zugreifen. Diese Berichte sollen ein zentraler Ort sein, zu dem sowohl Administratoren als auch Unternehmensleiter schnell zu diesen Daten wechseln können. Beachten Sie, dass wir [aufgrund der Art der Telemetrie der Anrufqualität nicht auf diese Daten für konkrete Zahlen vertrauen](CQD-frequently-asked-questions.md#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that).

Der Power BI-Bericht "Teams-Nutzung" besteht aus zwei primären Berichten: **[Anrufanzahlzusammenfassung](#call-count-summary-report)** und **[Audiominutenzusammenfassung](#audio-minutes-summary-report)**. Die Berichte ["Tägliche Nutzung"](#daily-usage), ["Regionale Audiodetails](#regional-audio-details)", ["Konferenzdetails](#conference-details) " und " [Benutzerliste](#user-list) " kommen ins Spiel, wenn ein Benutzer die Drilldownberichte nutzt, die in den nachstehenden Beschreibungen aufgeführt sind.

> [!NOTE]
> Gebäude- und Subnetzdaten müssen aufgefüllt werden, um regionale und Netzwerkfilterfunktionen bereitzustellen.

## <a name="call-count-summary-report"></a>Zusammenfassender Anrufanzahlbericht

Auf der Hauptseite (Anrufanzahlzusammenfassung) wird sofort die Anzahl der Audio-, Video- und Bildschirmfreigabesitzungen während der letzten 30 und 90 Tage bereitgestellt, wie im Abschnittstitel angegeben. Die anfänglich angezeigten Daten sind für die Gesamte Organisation vorgesehen und können mithilfe der Datenschnitt-Dropdownoptionen auf der linken Seite der Seite gefiltert werden.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report1.png)

1. Rechts neben den Datenschnittdropdowns wird die Anzahl der Aufrufe nach Medientyp in einer internen/externen Ansicht in den letzten dreißig Tagen aufgeschlüsselt. Wir können durch den obigen Screenshot sehen, dass es mehr Aufrufe von außerhalb der Organisation gibt, was unter Berücksichtigung der aktuellen globalen Umgebung sinnvoll ist.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report2.png)

1. Rechts neben dem Feld "Anzahl der Medientypen" wird die anzahl der monatlichen Anrufe nach Medientyp für die letzten 90 Tage angezeigt. Auf jede Spalte und jeden Medientyp kann mit der Maus darauf gezeigt werden, um die Anzahl für einen vorherigen Monat oder den aktuellen Monat bis zum aktuellen Datum anzuzeigen, wodurch Informationen zum Nutzungstrend bereitgestellt werden.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report3.png)
 

1. Das mittlere Diagramm funktioniert wie das 90-Tage-Diagramm, bietet jedoch eine tägliche Nutzungsansicht für die letzten 30 Tage und ermöglicht es einem Benutzer, mit der rechten Maustaste zu klicken und Details für einen bestimmten Tag zu detailieren.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report4.png)

Im unteren linken Abschnitt der Seite finden Sie eine Tabelle, die Die Gesamtwerte für jeden Medientyp im letzten Jahr enthält. 
    ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report5.png)
    ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report6.png)   

Rechts neben der Tabelle zeigt ein Balkendiagramm Clients mit der meisten Verwendung (Anrufe/Datenströme) für die letzten 30 Tage.
   ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report7.png)

Die letzten Diagramme für diese Seite zeigen jeden Medientyp einzeln an, mit einer Aufschlüsselung der Konferenz und der P2P-Nutzung. Die folgenden Diagramme zeigen, dass die Konferenznutzung im Vergleich zu P2P deutlich höher ist.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Zusammenfassender Bericht über Audiominuten

Im Nutzungsbericht "Audiominuten" wird die Gesamtminutennutzung über einige verschiedene Ansichten bereitgestellt. 

Wir haben die dreißigtägige Nutzungszusammenfassung neben den Datenschnitten so einfach zu verwendenden Textfeldern angezeigt. Die oberste Zahl zeigt die Gesamtsumme von dreißig Tagen an, wobei die internen und externen Aufschlüsselungen darunter liegen.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report9.png)

Das obere rechte Balkendiagramm bietet eine jahreslange Ansicht der Konferenzaudionutzung. Zeigen Sie mit der Maus auf den Monat, um die Audiominuten der Konferenz anzuzeigen.

Um den Unterschied zwischen P2P- und Konferenzaudio anzuzeigen, nimmt das diagramm unten links alle Audiodaten für das vergangene Jahr auf und hebt es zwischen den beiden Typen auf.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report10.png)

Das letzte Diagramm für die Seite "Audiominuten" zeigt die Verwendung von Audiominuten auf einer globalen Kartenüberlagerung an. Dieses Diagramm funktioniert nur, wenn Gebäude- und Subnetzdaten in den Mandanten hochgeladen werden. Die Kreisdiagrammüberlagerung auf der Karte kann mit Drilldowns versehen werden, wodurch die regionale Audionutzung ermöglicht wird.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Drill-Through-Funktionen

Wie bereits erwähnt, können Benutzer einen Drilldown in die täglichen und regionalen Nutzungsberichte ausführen.

### <a name="daily-usage"></a>Tägliche Nutzung

Der Bericht "Tägliche Nutzung" ermöglicht es einem Administrator, Spitzenverbrauchszeiträume im Laufe eines Tages zu identifizieren. Zusätzlich zur Nutzung sind wir auch in der Lage, die allgemeine Benutzerstimmung und das Feedback für diesen Tag zu erfassen.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report12.png)

Der Bericht "Tägliche Nutzung" zeigt die Anzahl der Audio-, Video- und Bildschirmfreigaben für den ausgewählten Tag mit der zusätzlichen Möglichkeit zur Unterscheidung zwischen interner und externer Konnektivität an. Eine Konferenz- und Peer-to-Peer-Aufschlüsselung befindet sich direkt rechts neben dem Modalitäts-Gesamtfeld. Oben rechts im Bericht finden Sie eine Liste der Konferenzen mit der zugehörigen ID und den Teilnehmern für den Tag. Die Konferenzliste enthält auch einen zusätzlichen Drilldown zum Bericht "Konferenzdetails". GRAFIK ERSETZEN

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report13.png)

Das Balkendiagramm im Mittleren Bereich ermöglicht es dem Benutzer, Spitzenverbrauchszeiträume im Laufe eines Tages zu identifizieren. Benutzer können einen Drilldown in die Stunde ausführen, die im Diagramm dargestellt wird, in der der Benutzerlistenbericht für die Stunde angezeigt wird.

Rechts neben dem Balkendiagramm wird Benutzerfeedback in einem visuellen Format dargestellt. Die Benutzerstimmung kann zwar subjektiv sein, bietet jedoch Einblicke, die verwendet werden können, um potenzielle Probleme zu identifizieren.

Die untere Tabelle enthält eine Reihe von Metriken für den Tag. Schlechte Prozentsätze und Fehlerraten können einem Administrator potenzielle Verbesserungsmöglichkeiten bieten. Jede Stunde kann auch einzeln ausgewählt werden, wie unten dargestellt.

Diese Daten können verwendet werden, um Regionen zu identifizieren, die in Spitzenzeiten Probleme haben.


Klicken Sie auf die Spalte für diesen Tag, um Metriken für diese Stunde anzuzeigen.
![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report14.png)
  
  1.  In der Tabelle unterhalb des Diagramms werden die Metriken für diese Stunde angezeigt. Dies kann nach jeder Spaltenüberschrift sortiert werden. wir wären jedoch daran interessiert, problematische Bereiche zu finden.  
    ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report15.png)
    
  2.  Wir sehen, dass in der IND-Region während dieses Zeitraums in Konferenzen eine schlechte Videoleistung auftritt. Anschließend können die CQD-QER-Microsoft-Berichte verwendet werden, um den problematischen Standort einzugrenzen, da die Region und der Zeitrahmen identifiziert wurden.

### <a name="conference-details"></a>Konferenzdetails

Der Bericht "Konferenzdetails" bietet zusätzliche Einblicke für Besprechungen, von einer Teilnehmerliste bis hin zu den während der Sitzung verwendeten Medientypen.

Klicken Sie im Konferenz-ID-Diagramm auf der Seite "Tägliche Nutzung" mit der rechten Maustaste auf die Teilnehmerleiste einer Konferenz, um einen Drilldown zu den Konferenzdetails zu erhalten.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report24.png)

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report25.png)
  

Wir können die Teilnehmer der Konferenz sowie alle relevanten Informationen bis hin zu Paketverlust und Jitter anzeigen, um potenzielle Problembehandlungsbemühungen in der unteren Tabelle zu unterstützen.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Regionale Audiodetails

Der Drilldown "Regionale Audiodetails" zeigt speziell die Audiominutennutzung für die ausgewählte Region an. Benutzer mit Zugriff auf CQD können Nutzungstrends für P2P- und Konferenzaudio in der ausgewählten Region sehen.

1.  Führen Sie auf der Seite "Anrufanzahlzusammenfassung" einen Drilldown zu einem bestimmten Bereich durch die Tabelle durch.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report16.png)

2.  Wählen Sie die Zeile mit dem Bereich aus, für den zusätzliche Informationen erforderlich sind.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report17.png)

3.  Die Datentrends zeigen eine erhebliche Anzahl von Minuten, die im internen Netzwerk verwendet werden, wobei Konferenzen die P2P-Verwendung weit übersteigen.
  ![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report18.png)

Der regionale Audiotrend kann verwendet werden, um zu zeigen, wie Benutzer von externen Einflüssen in der Welt betroffen sind. Insbesondere würden wir im Moment davon ausgehen, dass die externe Nutzung für die Regionen EMEA und APAC mit personen, die zur Remotearbeit aufgefordert werden, zunehmen wird.


### <a name="user-list"></a>Benutzerliste

Der Drilldown "Benutzerliste" enthält, wie zu erwarten, benutzerspezifische Informationen für eine bestimmte Stunde, die von der Person ausgewählt wird, die den Bericht anzeigt. Auf den Bericht "Benutzerliste" kann über einen Drilldown im Diagramm "Stündliche Trends" im Bericht "Tägliche Verwendung" zugegriffen werden. Klicken Sie mit der rechten Maustaste auf die Stunde, für die zusätzliche Informationen erforderlich sind, und wählen Sie Drill through und Benutzerliste aus, wie unten dargestellt.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report19.png)

Der Bericht "Benutzerliste" zeigt die interne/externe Konnektivität über das Ringdiagramm in der oberen Mitte der Seite an. Wir können sehen, dass es eine große Beteiligung von außerhalb des Unternehmensnetzwerks in der folgenden Abbildung gibt.

Oben rechts im Diagramm wird die Anzahl der Anrufe angezeigt, die von jedem Benutzer innerhalb dieser Stunde getätigt wurden.

![Screenshot: Teams-Nutzungsberichte.](media/CQD-teams-utilization-report20.png)

Die untere Tabelle enthält detaillierte Informationen zu den Sitzungen, an denen jeder Benutzer während dieser Stunde teilgenommen hat. Die Spalte "Fehlertyp" ist nützlich, um zu bestimmen, was dazu geführt hat, dass ein Aufruf abfällt. Die Spalten "Aufnahmegerät" und "Rendergerät" sind hilfreich, um zu ermitteln, warum ein Anruf mit schlechter Qualität gemeldet wurde.


## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](./monitor-call-quality-qos.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
