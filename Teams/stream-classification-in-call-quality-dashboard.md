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
description: Erfahren Sie, wie die Datenstromqualität im Anrufqualitätsdashboard für Microsoft Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909039"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Stream Classification in Call Quality Dashboard (CQD)

Mit dem Anrufqualitätsdashboard (CQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams und Skype for Business-Diensten hergestellt werden. Dieses Thema enthält ausführliche Informationen zur Qualitätsklassifizierung von Medienstreams. Weitere Informationen zum Anrufqualitätsdashboard und zur Einrichtung finden Sie unter "Einrichten [des Anrufqualitätsdashboards".](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Datenströme im AQD werden basierend auf den Werten der verfügbaren Schlüsselqualitätsmetriken als "Gut", "Schlecht" oder _"Nicht_ klassifiziert" klassifiziert. Die Metriken und Bedingungen, die zum Klassifizieren des Datenstroms verwendet werden, werden in den folgenden Tabellen angezeigt. Die Dimensionen "Poor Due To" des CQD können verwendet werden, um zu verstehen, welche Metrik für eine Klassifizierung _"Schlecht" verantwortlich_ ist. Weitere Informationen zu diesen Dimensionen finden Sie unter "Im Anrufqualitätsdashboard verfügbare Dimensionen und [Measures".](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Audio-Klassifizierung

Wenn mindestens eine der folgenden Bedingungen erfüllt ist, wird ein Audiodatenstrom als _"Schlecht" markiert:_

|Metrik|Szenario|Bedingung|Erklärung|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|Payload Description is not ODER|> 1,0|Beeinträchtigung des durchschnittlichen MOS (Mean Opinion Score) für den Datenstrom. Wie stark sich Netzwerkverlust und Jitter auf die Qualität der empfangenen Audiodaten auswirken?|
|Round Trip|ALL|> 500|Durchschnittliche in Millisekunden berechnete Roundtrip-Netzwerkverteilungszeit. Details, die in [RFC3550 verfügbar sind.](https://tools.ietf.org/html/rfc3550)|
|Packet Loss Rate|ALL|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|ALL|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Ratio Concealed Samples Avg|Payload Description is not ODER|> 0,07|Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Beispielen, die durch die Paketverlustreparatur generiert wurden, zur Gesamtzahl der Audioframes.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Classifier aufgrund von Freeze

Der Videodatenstrom wird  _basierend_ auf dem Wert einer klassifizierungsorientierten Bewertung als "Gut" oder "Schlecht" gekennzeichnet, um zu schätzen, dass für den Endbenutzer ein fixiertes Video zu sehen ist. Diese Klassifizierung ist nur für Microsoft Teams-Produkt verfügbar.

|Schritt #|Metrik|Szenario|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client: Server|>0,246|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzeroberfläche, Fixieren der Dauer und Gesamtanruferfahrung generiert wird |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client: Client|>0,524|_Poor_|_Good_|_Unclassified_|Eine Bewertung zwischen 0 und 1, die basierend auf einer Kombination aus Benutzeroberfläche, Fixieren der Dauer und Gesamtanruferfahrung generiert wird |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Video-Klassifizierung
Ein Videodatenstrom wird  basierend _auf_ dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als "Gut" oder "Schlecht" gekennzeichnet:

|Schritt #|Metrik|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt enthält Frames, die aus Netzwerkverlusten wiederhergestellt wurden.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate nach der Anwendung von FEC auf alle Videodatenströme und -codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein VBSS-Datenstrom  wird  basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als "Gut" oder "Schlecht" gekennzeichnet:

|Schritt # |Metrik |Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Durchschnitt enthält Frames, die aus Netzwerkverlusten wiederhergestellt wurden.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate nach der Anwendung von FEC auf alle Videodatenströme und -codecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabedatenstrom wird als _"Schlecht" markiert,_ wenn mindestens eine der folgenden Bedingungen erfüllt ist:

| Metrik     | Bedingung | Erklärung |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Prozentsatz der Kacheln, die verworfen und nicht an einen Remote peer gesendet werden (z. B. von der MCU an einen Viewer). Verworfene (oder nicht mehr verfügbare) Kacheln können durch Bandbreiteneinschränkungen zwischen Client und Server verursacht werden. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver. |
| AppSharing Relative OneWay Average | > 1,75 | Durchschnittliche relative, one-way-Verzögerung zwischen den Endpunkten in Sekunden für Anwendungsfreigabe-Datenströme. |
| | | |

## <a name="unclassified-streams"></a>Nicht klassifizierte Datenströme

Im CQD wird ein Datenstrom als _"Nicht klassifiziert"_ markiert, wenn die Konnektivität mit interactive Connectivity Connectivity (ICE) fehlschlägt oder wenn nicht alle Metriken gemeldet werden, die zum Berechnen der Datenstromklassifizierung erforderlich sind.

Zum Prüfen von ICE-Verbindungsfehlern überprüfen Sie die Dimensionen "Erste ICE-Konnektivität" und "Zweite ICE-Konnektivität" für einen Wert "FEHLGESCHLAGEN". Wenn ein Wert auf einen Fehler hinweist, wird der Datenstrom als _"Unclassified" gekennzeichnet._

Wenn die Konnektivität mit ICE für einen _nicht klassifizierten_ Datenstrom erfolgreich war, wird der Datenstrom wahrscheinlich als _nicht_ klassifiziert betrachtet, da keine Schlüsseldatenstrommetriken gemeldet wurden. Es gibt einige Gründe, warum diese Metriken nicht gemeldet werden können:

- **Die Berichte zu QoE wurden** nicht empfangen – Die für die Klassifizierung verwendeten Metriken werden in einem am Ende eines Anrufs gesendeten QoE-Bericht gemeldet. Wenn dieser Bericht nicht erstellt wird (z. B. weil einige Endpunkte von Drittanbietern möglicherweise QoE nicht senden) oder nicht gesendet werden konnten (z. B. aufgrund eines Netzwerkausfalls), kann das AQD den Datenstrom nicht klassifizieren.

  > [!TIP]
  > Mit der Dimension "QoE-Bericht verfügbar" können Sie feststellen, ob ein QoE-Bericht für einen Datenstrom empfangen wurde. Beachten Sie, dass diese Dimension den Wert "Wahr" haben wird, wenn ein QoE-Bericht von einem der beiden Endpunkte empfangen wurde. Ein QoE-Bericht von beiden Endpunkten ist erforderlich, um eine möglichst genaue Berichterstellung der Metriken zu ermöglichen.

- **Kurze Aufrufe** – Kurze Aufrufe haben möglicherweise nicht genügend Medienaktivitäten, um wichtige Datenstrommetriken zu berechnen. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.

  > [!TIP]
  > Die Dimensionen "Dauer (Sekunden)", "Dauer (Minuten)", "Dauer 5 Sekunden oder weniger" und "Dauer 60 Sekunden oder mehr" können zur Bestimmung der Dauer eines Datenstrom verwendet werden. Mithilfe der Messung "Durchschnittliche Anrufdauer" können Sie die durchschnittliche Dauer eines Satzes von Datenströmen berechnen.

- **Geringe Paketverwendung –** Wie beim Szenario "Kurzer Anruf" ist für die Berechnung von Keystreammetriken eine ausreichende Paketverwendung erforderlich. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.
  - Ein häufiges Szenario mit geringer Paketverwendung tritt auf, wenn ein Teilnehmer einer Besprechung beitritt, um den Präsentierenden anzuhören, aber nie spricht (das Mikrofon ist für den größten Teil des Anrufs stummgeschaltet). Hier hat der an den Client eingehende Audiodatenstrom eine hohe Paketverwendung, während der vom Client ausgehende Audiodatenstrom nur geringe bis gar keine Paketverwendung hat. Die Dauer des Datenstroms kann eine Stunde oder länger dauern, aber die Paketauslastung des Datenstroms  vom Client zum Server ist niedrig, da das Mikrofon stummgeschaltet wurde und ein nicht klassifizierter Datenstrom ergebnisset.

  > [!TIP]
  > Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.

## <a name="related-topics"></a>Verwandte Themen
[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Daten und Berichte zum AQD](CQD-data-and-reports.md)

[Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
