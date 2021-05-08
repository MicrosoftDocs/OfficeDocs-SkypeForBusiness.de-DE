---
title: Stream classification in Call Quality Dashboard (CQD)
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Erfahren Sie, wie die Qualität des Datenstroms im Anrufqualitätsdashboard (Anrufqualitätsdashboard) für Microsoft Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909039"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Stream Classification in Call Quality Dashboard (CQD)

Mit dem Anrufqualitäts-Dashboard (AQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams- und Skype for Business-Diensten getätigt wurden. Unter diesem Thema finden Sie detaillierte Informationen über die Qualitätsklassifizierung von Mediendatenströmen. Weitere Informationen zum Anrufqualitätsdashboard und zur Einrichtung finden Sie unter [Einrichten des Anrufqualitätsdashboards.](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Streams im CQD werden basierend auf den Werten der verfügbaren Schlüsselqualitätsmetriken als "Gut", _"Schlecht"_ oder _"Nicht_ klassifiziert" klassifiziert. Die Metriken und Bedingungen, die zum Klassifizieren von Datenstrom verwendet werden, werden in den folgenden Tabellen angezeigt. Die Dimensionen "Schlecht fällig an" des CQD können verwendet werden, um zu verstehen, welche Metrik für die Klassifizierung _"Schlecht"_ verantwortlich ist. Weitere Informationen zu diesen Dimensionen finden Sie unter Im Anrufqualitätsdashboard verfügbare [Dimensionen und Measures.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Audio-Klassifizierung

Wenn eine oder mehrere der folgenden Bedingungen erfüllt sind, wird ein Audiodatenstrom als _"Schlecht" markiert:_

|Metrik|Szenario|Bedingung|Erklärung|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|Nutzlastbeschreibung ist nicht IMMER|> 1,0|Beeinträchtigung des durchschnittlichen MOS (Mean Opinion Score) für den Datenstrom. Wie stark sich Netzwerkverlust und Jitter auf die Qualität der empfangenen Audiodaten auswirken?|
|Round Trip|ALL|> 500|Durchschnittliche in Millisekunden berechnete Verteilungszeit des Roundtripnetzwerks. Details, die in [RFC3550 verfügbar sind.](https://tools.ietf.org/html/rfc3550)|
|Packet Loss Rate|ALL|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|ALL|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Ratio Concealed Samples Avg|Nutzlastbeschreibung ist nicht IMMER|> 0,07|Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Beispielen, die durch die Paketverlustreparatur generiert wurden, zur Gesamtzahl der Audioframes.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Classifier due to Freeze

Der Videodatenstrom wird  basierend _auf dem_ Wert einer Klassifizierungsergebnis, die generiert wurde, als "Gut" oder "Schlecht" markiert, um zu schätzen, dass für den Endbenutzer ein gesperrtes Video angezeigt wurde. Diese Klassifizierung ist nur für Microsoft Teams verfügbar.

|Schritt #|Metrik|Szenario|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client:Server|>0,246|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzeroberfläche, Fixieren der Dauer und Gesamtanruferfahrung generiert wird |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client:Client|>0,524|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzeroberfläche, Fixieren der Dauer und Gesamtanruferfahrung generiert wird |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Video-Klassifizierung
Ein Videodatenstrom wird  basierend _auf_ dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als "Gut" oder "Schlecht" markiert:

|Schritt #|Metrik|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt umfasst die aus Netzwerkverlusten wiederhergestellten Frames.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate nach der Anwendung von FEC auf alle Videodatenströme und -codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein VBSS-Datenstrom  wird  basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als "Gut" oder "Schlecht" markiert:

|Schritt # |Metrik |Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt umfasst die aus Netzwerkverlusten wiederhergestellten Frames.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate nach der Anwendung von FEC auf alle Videodatenströme und -codecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabe-Datenstrom wird als _"Schlecht"_ markiert, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:

| Metrik     | Bedingung | Erklärung |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Prozentsatz der Kacheln, die verworfen werden, anstatt an einen Remote-Peer gesendet zu werden (z. B. von der MCU an einen Viewer). Verworfene (oder nicht mehr verfügbare) Kacheln können durch Beschränkungen der Bandbreite zwischen Client und Server verursacht werden. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver. |
| AppSharing Relative OneWay Average | > 1,75 | Relative einwegverzögerung im Durchschnitt zwischen den Endpunkten in Sekunden für Anwendungsfreigabe-Datenströme. |
| | | |

## <a name="unclassified-streams"></a>Nicht klassifizierte Streams

Im CQD wird ein Datenstrom als _Nicht_ klassifiziert markiert, wenn die ICE-Konnektivität (Interactive Connectivity Connectivity) fehlschlägt oder nicht alle Metriken gemeldet werden, die zum Berechnen der Datenstromklassifizierung erforderlich sind.

Zum Prüfen von ICE-Verbindungsfehlern überprüfen Sie die Dimensionen "Erste ICE-Konnektivität" und "Zweite ICE-Konnektivität" für einen Wert "FEHLGESCHLAGEN". Wenn ein Wert einen Fehler angibt, wird der Datenstrom als _Unclassified gekennzeichnet._

Wenn die ICE-Konnektivität für einen _nicht klassifizierten_ Datenstrom erfolgreich war, gilt der Datenstrom wahrscheinlich als _Nicht klassifiziert,_ da keine Schlüsseldatenstrommetriken gemeldet wurden. Es gibt einige Gründe, warum diese Metriken nicht gemeldet werden können:

- **QoE-Berichte wurden** nicht empfangen – Die für die Klassifizierung verwendeten Metriken werden in einem QoE-Bericht gemeldet, der am Ende eines Anrufs gesendet wurde. Wenn dieser Bericht nicht erstellt wird (z. B. weil einige Endpunkte von Drittanbietern möglicherweise kein QoE senden) oder nicht gesendet werden konnten (z. B. aufgrund eines Netzwerkausfalls), kann das AQD den Datenstrom nicht klassifizieren.

  > [!TIP]
  > Mit der Dimension "QoE-Bericht verfügbar" können Sie feststellen, ob ein QoE-Bericht für einen Datenstrom empfangen wurde. Beachten Sie, dass diese Dimension den Wert "Wahr" haben wird, wenn ein QoE-Bericht von einem der beiden Endpunkte empfangen wurde. Ein QoE-Bericht von beiden Endpunkten ist erforderlich, um eine möglichst genaue Berichterstellung der Metriken zu ermöglichen.

- **Kurze Anrufe** – Kurze Anrufe haben möglicherweise nicht genügend Medienaktivitäten, um wichtige Datenstrommetriken zu berechnen. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.

  > [!TIP]
  > Die Dimensionen "Dauer (Sekunden)", "Dauer (Minuten)", "Dauer 5 Sekunden oder weniger" und "Dauer 60 Sekunden oder mehr" können zur Bestimmung der Dauer eines Datenstrom verwendet werden. Mithilfe der Messung "Durchschnittliche Anrufdauer" können Sie die durchschnittliche Dauer eines Satzes von Datenströmen berechnen.

- **Geringe Paketauslastung –** Wie beim Szenario "Kurzanruf" ist für die Berechnung von Keystreammetriken eine ausreichende Paketverwendung erforderlich. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.
  - Ein häufiges Szenario mit geringer Paketverwendung tritt auf, wenn ein Teilnehmer einer Besprechung beitritt, um dem Sprechteilnehmer zuzuhören, aber nie spricht (das Mikrofon ist für den größten Teil des Anrufs stummgeschaltet). Hier hat der an den Client eingehende Audiodatenstrom eine hohe Paketauslastung, während der vom Client ausgehende Audiodatenstrom nur eine geringe bis gar keine Paketverwendung hat. Die Dauer des Datenstroms kann eine Stunde oder länger dauern, aber die Paketverwendung des Datenstroms vom Client zum Server ist niedrig, da das Mikrofon stummgeschaltet wurde und ein _Nicht klassifizierter_ Datenstrom ergebnisset.

  > [!TIP]
  > Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.

## <a name="related-topics"></a>Verwandte Themen
[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwalten der Anruf- und Besprechungsqualität mithilfe des Anrufqualitäts-AQD](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
