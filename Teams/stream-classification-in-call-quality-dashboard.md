---
title: Datenstromklassifizierung im Anrufqualitätsdashboard (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Erfahren Sie, wie die Datenstromqualität im Anrufqualitätsdashboard (CQD) für Microsoft Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059256"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Streamklassifizierung im Anrufqualitätsdashboard (CQD)

Mit dem Anrufqualitäts-Dashboard (AQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams- und Skype for Business-Diensten getätigt wurden. Unter diesem Thema finden Sie detaillierte Informationen über die Qualitätsklassifizierung von Mediendatenströmen. Weitere Informationen zu CQD und dessen Einrichtung finden Sie unter [Einrichten des Anrufqualitätsdashboards](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Streams in CQD werden basierend auf den Werten der verfügbaren Schlüsselqualitätsmetriken als _"Gut_", "_Schlecht_" oder "_Nicht klassifiziert_" klassifiziert. Die Metriken und Bedingungen, die zum Klassifizieren des Datenstroms verwendet werden, werden in den folgenden Tabellen angezeigt. Die CQD-Dimensionen "Poor Due To" können verwendet werden, um zu verstehen, welche Metrik für eine _Schlechte_ Klassifizierung verantwortlich ist. Weitere Informationen zu diesen Dimensionen finden Sie [unter Dimensionen und Kennzahlen, die im Anrufqualitätsdashboard verfügbar sind](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Audio-Klassifizierung

Wenn eine oder mehrere der folgenden Bedingungen erfüllt sind und die Paketauslastung > 500 Pakete beträgt, wird ein Audiodatenstrom als _"Schlecht_" gekennzeichnet:

|Metrik|Szenario|Bedingung|Erklärung|
|:-----|:-----|:-----|:-----|
|Round Trip|ALLE|> 500|Durchschnittliche Roundtrip-Netzwerkverteilungszeit in Millisekunden. In [RFC3550](https://tools.ietf.org/html/rfc3550) verfügbare Details.|
|Packet Loss Rate|ALLE|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|ALLE|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
||||

### <a name="video-classifier-due-to-freeze"></a>Videoklassifizierer aufgrund von Freeze

Der Videodatenstrom wird basierend auf dem Wert einer generierten Klassifizierungsbewertung als  _"Gut_ " oder " _Schlecht_ " markiert, um zu schätzen, dass der Endbenutzer eingefrorenes Video erlebt hat. Dieser Klassifizierer ist nur für Microsoft Teams Produkt verfügbar.

|Schritt #|Metrik|Szenario|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzererfahrung, Einfrieren von Dauerstatistiken und gesamter Anruferfahrung generiert wird |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzererfahrung, Einfrieren von Dauerstatistiken und gesamter Anruferfahrung generiert wird |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Video-Klassifizierung
Ein Videostream wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als _"Gut_ " oder " _Schlecht_ " markiert:

|Schritt #|Metrik|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt enthält Frames, die von Netzwerkverlusten wiederhergestellt wurden.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate, nachdem FEC über alle Videodatenströme und Codecs aggregiert angewendet wurde.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein VBSS-Datenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als _"Gut_ " oder " _Schlecht_ " markiert:

|Schritt # |Metrik |Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|Codec ist NICHT H264S</br>Und</br>StreamDirection ist eingehend</br></br>Wenn FrameLoss 50 % >|_Poor_|_Good_|_Unclassified_|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt enthält Frames, die von Netzwerkverlusten wiederhergestellt wurden. FrameLoss wird nur zum Klassifizieren eingehender nicht-H264S-Datenströme verwendet.|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden. Gilt für alle ausgehenden Datenströme und streamDirection für H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabedatenstrom wird als _"Schlecht_ " gekennzeichnet, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:

| Metrik     | Bedingung | Erklärung |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Prozentsatz der Kacheln, die verworfen werden, anstatt sie an einen Remotepeer zu senden (z. B. von der MCU zu einem Viewer). Verworfene (oder beschädigte) Kacheln können durch Bandbreiteneinschränkungen zwischen Client und Server verursacht werden. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver. |
| AppSharing Relative OneWay Average | > 1.75 | Durchschnittliche relative unidirektionale Verzögerung zwischen den Endpunkten in Sekunden für Anwendungsfreigabedatenströme. |
| | | |

## <a name="unclassified-streams"></a>Nicht klassifizierte Streams

In CQD wird ein Datenstrom als _nicht klassifiziert_ gekennzeichnet, wenn die ICE-Konnektivität (Interactive Connectivity Establishment) fehlschlägt oder wenn nicht alle metriken gemeldet werden, die zum Berechnen der Datenstromklassifizierung erforderlich sind.

Zum Prüfen von ICE-Verbindungsfehlern überprüfen Sie die Dimensionen "Erste ICE-Konnektivität" und "Zweite ICE-Konnektivität" für einen Wert "FEHLGESCHLAGEN". Wenn einer der Werte auf einen Fehler hinweist, wird der Datenstrom als _nicht klassifiziert_ markiert.

Wenn die ICE-Konnektivität für einen _nicht klassifizierten_ Datenstrom erfolgreich war, wird der Datenstrom wahrscheinlich als _nicht klassifiziert_ betrachtet, da keine Schlüsseldatenstrommetriken gemeldet wurden. Es gibt einige Gründe, warum diese Metriken nicht gemeldet werden können:

- **QoE-Berichte wurden nicht empfangen** – Die für die Klassifizierung verwendeten Metriken werden in einem QoE-Bericht gemeldet, der am Ende eines Anrufs gesendet wurde. Wenn dieser Bericht nicht erstellt wird (z. B. weil einige Endpunkte von Drittanbietern QoE möglicherweise nicht senden) oder nicht gesendet werden konnte (z. B. aufgrund eines Netzwerkausfalls), kann CQD den Datenstrom nicht klassifizieren.

  > [!TIP]
  > Mit der Dimension "QoE-Bericht verfügbar" können Sie feststellen, ob ein QoE-Bericht für einen Datenstrom empfangen wurde. Beachten Sie, dass diese Dimension den Wert "Wahr" haben wird, wenn ein QoE-Bericht von einem der beiden Endpunkte empfangen wurde. Ein QoE-Bericht von beiden Endpunkten ist erforderlich, um eine möglichst genaue Berichterstellung der Metriken zu ermöglichen.

- **Kurzanrufe** – Kurze Anrufe verfügen möglicherweise nicht über genügend Medienaktivitäten, um wichtige Datenstrommetriken zu berechnen. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.

  > [!TIP]
  > Die Dimensionen "Dauer (Sekunden)", "Dauer (Minuten)", "Dauer 5 Sekunden oder weniger" und "Dauer 60 Sekunden oder mehr" können zur Bestimmung der Dauer eines Datenstrom verwendet werden. Mithilfe der Messung "Durchschnittliche Anrufdauer" können Sie die durchschnittliche Dauer eines Satzes von Datenströmen berechnen.

- **Geringe Paketauslastung** – Wie beim Szenario "kurzer Anruf" ist für die Berechnung von Schlüsseldatenstrommetriken eine ausreichende Paketauslastung erforderlich. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.
  - Ein häufiges Szenario mit geringer Paketauslastung tritt auf, wenn ein Teilnehmer an einer Besprechung teilnimmt, um den Referenten zu hören, aber nie spricht (das Mikrofon ist für den größten Teil des Anrufs stummgeschaltet). Hier hat der an den Client eingehende Audiodatenstrom eine hohe Paketauslastung, während der vom Client ausgehende Audiodatenstrom nur wenig bis gar keine Paketauslastung aufweist. Die Dauer des Datenstroms kann eine Stunde oder länger dauern, aber die Paketauslastung des Datenstroms vom Client zum Server ist niedrig, da das Mikrofon stummgeschaltet wurde, und ein _nicht klassifizierter_ Datenstrom ergibt sich.

  > [!TIP]
  > Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.

## <a name="related-topics"></a>Verwandte Themen
[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
