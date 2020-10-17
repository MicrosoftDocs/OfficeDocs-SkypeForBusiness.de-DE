---
title: Stream-Klassifizierung im Dashboard für die Anrufqualität (CQD)
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
description: Erfahren Sie, wie die Datenstromqualität in das Anruf Qualitäts Dashboard (CQD) für Microsoft Teams und Skype for Business Online eingestuft wird.
ms.openlocfilehash: b27de2bb3dc62e8344b51d564f2c295a08f45932
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526352"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Stream-Klassifizierung im Dashboard für die Anrufqualität (CQD)

Das Anruf Qualitäts Dashboard (CQD) für Microsoft Teams und Skype for Business Online ermöglicht Ihnen, Einblicke in die Qualität von Anrufen zu gewinnen, die mit Microsoft Teams und Skype for Business-Diensten getätigt wurden. Dieses Thema enthält detaillierte Informationen zur Qualitäts Klassifizierung von Medienströmen. Weitere Informationen zu CQD und zur Einrichtung finden Sie unter [Einrichten der Anruf Qualitätssteuerung](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Streams in CQD werden basierend auf den Werten der verfügbaren Schlüssel Qualitäts Metriken als " _gut_", " _schlecht_" oder "nicht _klassifiziert_ " klassifiziert. Die Metriken und Bedingungen, die für die Klassifizierung von Datenstrom verwendet werden, werden in den folgenden Tabellen angezeigt. Die "CQD"-Dimensionen können verwendet werden, um zu verstehen, welche Metrik für eine _unzureichende_ Klassifizierung verantwortlich ist. Weitere Informationen zu diesen Dimensionen finden Sie unter [Dimensionen und Measures, die im Dashboard für die Anrufqualität verfügbar sind](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Audio-Klassifizierung

Wenn eine oder mehrere der folgenden Bedingungen erfüllt sind, wird ein Audiostream als " _schlecht_" gekennzeichnet:

|Metrik|Bedingung|Erklärung|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Durchschnittlicher Netzwerk-Mittelwert der Meinungs Bewertung für Datenstrom. Wie viel Netzwerk Verlust und Jitter die Qualität der empfangenen Audiodaten beeinträchtigt haben.|
|Round Trip|> 500|Durchschnittliche Roundtrip-Netzwerk Laufzeit, berechnet in Millisekunden. Einzelheiten sind in [rfc3550 angegeben](https://tools.ietf.org/html/rfc3550)verfügbar.|
|Packet Loss Rate|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Ratio Concealed Samples Avg|> 0,07|Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Beispielen, die durch die Paketverlustreparatur generiert wurden, zur Gesamtzahl der Audioframes.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Klassifizierung durch Einfrieren

Der Videostream wird basierend auf dem Wert eines Klassifizierungs Ergebnisses als "  _gut_ " oder " _schlecht_ " gekennzeichnet, um zu schätzen, dass der Endbenutzer ein gefrorenes Video erlebt hat. Diese Klassifizierung steht nur für Microsoft Teams-Produkt zur Verfügung.

|Schritt #|Metrik|Szenario|Bedingung |Klassifizierung, wenn die Bedingung wahr ist |Klassifizierung, wenn die Bedingung falsch ist |Klassifizierung, wenn die Metrik nicht verfügbar ist |Erklärung |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Schlechte Video Qualität durch Einfrieren der Klassifizierung |Is-Serverpaar ist Client: Server|>0,246|_Poor_|_Good_|_Unclassified_|Eine Punktzahl zwischen 0 und 1, die auf der Grundlage einer Kombination aus Benutzererfahrung, Statistiken für Freeze-Dauer und Anruferlebnis insgesamt generiert wird |
|2|Schlechte Video Qualität durch Einfrieren der Klassifizierung |Is-Server Paar ist Client: Client|>0,524|_Poor_|_Good_|_Unclassified_|Eine Punktzahl zwischen 0 und 1, die auf der Grundlage einer Kombination aus Benutzererfahrung, Statistiken für Freeze-Dauer und Anruferlebnis insgesamt generiert wird |
|  |  |  |  |  |  |  |

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
[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und-Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
