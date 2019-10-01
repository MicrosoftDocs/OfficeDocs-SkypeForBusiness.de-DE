---
title: Datenstromklassifizierung im Anrufqualitäts-Dashboard
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Erfahren Sie, wie die Datenstromqualität im Anrufqualitäts-Dashboard für Microsoft-Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: 6ed59111eea2c14da321cf1467b021980a223ec0
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328331"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Datenstromklassifizierung im Anrufqualitäts-Dashboard

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Streams in CQD werden basierend auf den Werten der verfügbaren Schlüssel Qualitäts Metriken als " _gut_", " _schlecht_" oder "nicht _klassifiziert_ " klassifiziert. Die Metriken und Bedingungen, die für die Klassifizierung von Datenstrom verwendet werden, werden in den folgenden Tabellen angezeigt. Die "CQD"-Dimensionen können verwendet werden, um zu verstehen, welche Metrik für eine _unzureichende_ Klassifizierung verantwortlich ist. Weitere Informationen zu diesen Dimensionen finden Sie unter [Dimensionen und Measures, die im Dashboard für die Anrufqualität verfügbar sind](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Audio-Klassifizierung

Wenn eine oder mehrere der folgenden Bedingungen erfüllt sind, wird ein Audiostream als " _schlecht_" gekennzeichnet:

|Metrik|Bedingung|Erklärung|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Beeinträchtigung des durchschnittlichen MOS (Mean Opinion Score) für den Datenstrom. Wie viel Netzwerk Verlust und Jitter die Qualität der empfangenen Audiodaten beeinträchtigt haben.|
|Round Trip|> 500|Durchschnittliche Roundtrip-Netzwerk Laufzeit, berechnet in Millisekunden. Einzelheiten sind in [rfc3550 angegeben](https://tools.ietf.org/html/rfc3550)verfügbar.|
|Packet Loss Rate|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Ratio Concealed Samples Avg|> 0,07|Durchschnittliches Verhältnis der Anzahl von Audioframes mit verborgenen Samples, die durch Paketverlust-Heilung an die Gesamtzahl der Audioframes generiert wurden.|
||||

### <a name="video-classifier"></a>Video-Klassifizierung

Ein Videostream wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als " _gut_ " oder " _schlecht_ " gekennzeichnet:

|Schritt #|Metrik|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Mittelwert umfasst Frames, die von Netzwerk Verlusten wiederhergestellt werden.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate, nachdem FEC auf alle Videodatenströme und-Codecs aggregiert wurde.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein schlechte VBSS-Datenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als " _gut_ " oder " _schlecht_ " gekennzeichnet:

|Schritt # |Metrik |Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Der Mittelwert umfasst Frames, die von Netzwerk Verlusten wiederhergestellt werden.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Paketverlustrate, nachdem FEC auf alle Videodatenströme und-Codecs aggregiert wurde.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabe Datenstrom ist als " _schlecht_ " gekennzeichnet, wenn mindestens eine der folgenden Bedingungen erfüllt ist:

| Metrik     | Bedingung | Erklärung |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Prozentsatz der Kacheln, die verworfen werden, anstatt an einen Remotepeer gesendet zu werden (beispielsweise von der MCU zu einem Viewer). Verworfene (oder verdorbene) Kacheln können durch Bandbreiteneinschränkungen zwischen Client und Server verursacht werden. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver. |
| AppSharing Relative OneWay Average | > 1,75 | Durchschnittliche relative unidirektionale Verzögerung zwischen den Endpunkten in Sekunden für Anwendungsfreigabe Datenströme. |
| | | |

## <a name="unclassified-streams"></a>Nicht klassifizierte Datenströme

In CQD wird ein Datenstrom als "nicht _klassifiziert_ " gekennzeichnet, wenn die Verbindung zwischen der Interaktions Einrichtung (ICE) fehlschlägt oder wenn alle zur Berechnung der Datenstrom Klassifizierung erforderlichen Metriken nicht gemeldet werden.

Zum Prüfen von ICE-Verbindungsfehlern überprüfen Sie die Dimensionen "Erste ICE-Konnektivität" und "Zweite ICE-Konnektivität" für einen Wert "FEHLGESCHLAGEN". Wenn einer der beiden Werte einen Fehler angibt, wird der Datenstrom als nicht _klassifiziert_markiert.

Wenn die Ice-Konnektivität für einen nicht _klassifizierten_ Datenstrom erfolgreich war, wird der Datenstrom wahrscheinlich als nicht _klassifiziert_ angesehen, da Schlüsseldaten Strom Metriken nicht gemeldet wurden. Es gibt einige Gründe, warum diese Metriken nicht gemeldet werden können:

- **QoE-Berichte wurden nicht empfangen** – die für die Klassifizierung verwendeten Metriken werden in einem QoE-Bericht gemeldet, der am Ende eines Anrufs gesendet wird. Wenn dieser Bericht nicht erstellt wird (beispielsweise weil einige Drittanbieter-Endpunkte möglicherweise keine QoE-Nachricht senden) oder nicht gesendet werden konnten (beispielsweise aufgrund eines Netzwerkausfalls), kann CQD den Datenstrom nicht klassifizieren.

> [!TIP]
> Mit der Dimension "QoE-Bericht verfügbar" können Sie feststellen, ob ein QoE-Bericht für einen Datenstrom empfangen wurde. Beachten Sie, dass diese Dimension den Wert "Wahr" haben wird, wenn ein QoE-Bericht von einem der beiden Endpunkte empfangen wurde. Ein QoE-Bericht von beiden Endpunkten ist erforderlich, um eine möglichst genaue Berichterstellung der Metriken zu ermöglichen.

- **Kurze Anrufe** – kurze Anrufe haben möglicherweise nicht genügend Medienaktivitäten, um wichtige Datenstrom Metriken zu berechnen. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.

> [!TIP]
> Die Dimensionen "Dauer (Sekunden)", "Dauer (Minuten)", "Dauer 5 Sekunden oder weniger" und "Dauer 60 Sekunden oder mehr" können zur Bestimmung der Dauer eines Datenstrom verwendet werden. Mithilfe der Messung "Durchschnittliche Anrufdauer" können Sie die durchschnittliche Dauer eines Satzes von Datenströmen berechnen.

- **Niedrige Paket Auslastung** – wie im Szenario "Short Call" ist für die Berechnung von Schlüsseldaten Strom Metriken eine ausreichende Paket Nutzung erforderlich. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.
  - Ein häufiges Szenario für niedrige Paket Auslastung tritt auf, wenn ein Teilnehmer einer Besprechung Beitritt, um den Referenten zu hören, aber nie spricht (das Mikrofon ist für die meisten Anrufe stumm geschaltet). Hier verfügt der für den Client eingehende Audiostream über eine große Paket Auslastung, während der vom Client ausgehende Audiostream nur wenig bis gar keine Paket Nutzung hat. Die Dauer des Datenstroms kann eine Stunde oder länger sein, die Paket Auslastung des Datenstroms vom Client zum Server ist jedoch gering, da das Mikrofon stumm geschaltet wurde und ein nicht _klassifizierter_ Datenstrom entsteht.

> [!TIP]
> Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.

## <a name="related-topics"></a>Verwandte Themen

[Aktivieren und Verwenden des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)
