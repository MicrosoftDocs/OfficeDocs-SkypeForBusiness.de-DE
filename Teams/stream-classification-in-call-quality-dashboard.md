---
title: Datenstromklassifizierung im Anrufqualitäts-Dashboard
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Erfahren Sie, wie die Datenstromqualität im Anrufqualitäts-Dashboard für Microsoft-Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: a04843e45e444da34bf065c1cdfbf0a619be9406
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541720"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Datenstromklassifizierung im Anrufqualitäts-Dashboard

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Audio-Klassifizierung

Ein Audiodatenstrom wird als schlecht gekennzeichnet, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:

|**Metrik**|**Bedingung**|**Erklärung**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|> 500|Durchschnittliche in Millisekunden berechnete Roundtripzeit bei der Netzwerkverteilung, wie in RFC3550 angegeben.|
|Packet Loss Rate|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Ratio Concealed Samples Avg|> 0,07|Durchschnittliches Verhältnis zwischen der Anzahl von audio Frames mit ausgeblendeten Samples, generiert von Paketverlust und der Gesamtzahl der audio Frames Reparatur.|

### <a name="video-classifier"></a>Video-Klassifizierung

Ein Videodatenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als gut oder schlecht gekennzeichnet:

|**Schritt #**|**Metrik**|**Bedingung**|**Klassifizierung, wenn die Bedingung wahr ist**|**Klassifizierung, wenn die Bedingung falsch ist**|**Klassifizierung, wenn die Metrik nicht verfügbar ist**|**Erklärung**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Mit Schritt 2 fortfahren|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Paketverlustrate nach FEC angewendet wurde, werden alle Videostreams und Codecs aggregiert.|

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein VBSS-Videodatenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als gut oder schlecht gekennzeichnet:

|**Schritt #**|**Metrik**|**Bedingung**|**Klassifizierung, wenn die Bedingung wahr ist**|**Klassifizierung, wenn die Bedingung falsch ist**|**Klassifizierung, wenn die Metrik nicht verfügbar ist**|**Erklärung**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Mit Schritt 2 fortfahren|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Mit Schritt 3 fortfahren|Die Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Paketverlustrate nach FEC angewendet wurde, werden alle Videostreams und Codecs aggregiert.|

### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabedatenstrom wird als schlecht gekennzeichnet, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:


| **Metrik**                                     | **Bedingung** | **Erklärung**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Prozentsatz der Kacheln, die anstelle von (z. B. von der MCU für ein Betrachter) gesendet werden, remote Peer verworfen werden. Verworfene (oder beschädigte) Kacheln können durch Bandbreite Einschränkungen zwischen Client und Server verursacht werden. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Durchschnittliche unidirektionale relative Verzögerung zwischen den Endpunkten in Sekunden für die Anwendungsfreigabe Datenströme.                                                                                                                       |

## <a name="unclassified-streams"></a>Nicht klassifizierte Datenströme

In AQD wird ein Datenstrom als nicht klassifiziert gekennzeichnet, wenn die ICE-Konnektivität fehlschlägt oder wenn nicht alle für die Berechnung der Datenstromklassifizierung erforderlichen Metriken gemeldet werden.

Zum Prüfen von ICE-Verbindungsfehlern überprüfen Sie die Dimensionen "Erste ICE-Konnektivität" und "Zweite ICE-Konnektivität" für einen Wert "FEHLGESCHLAGEN". Wenn einer der beiden Werte einen Fehler anzeigt, wird der Datenstrom als nicht klassifiziert gekennzeichnet.

Wenn die ICE-Konnektivität für einen nicht klassifizierten Datenstrom erfolgreich war, wird der Datenstrom wahrscheinlich als nicht klassifiziert betrachtet, da Schlüssel-Datenstrommetriken nicht gemeldet wurden. Es gibt einige Gründe, warum diese Metriken nicht gemeldet werden können:

- **QoE-Berichte wurden nicht empfangen** - Die für die Klassifizierung verwendeten Metriken werden in einem QoE-Bericht angegeben, der am Ende eines Anrufs gesendet wird. Wenn dieser Bericht nicht erstellt wird (z. B. weil einige Endpunkte von Drittanbietern möglicherweise keine QoE senden) oder nicht gesendet werden konnte (z. B. wegen eines Netzwerkausfalls), kann AQD den Datenstrom nicht klassifizieren.

> [!TIP]
> Mit der Dimension "QoE-Bericht verfügbar" können Sie feststellen, ob ein QoE-Bericht für einen Datenstrom empfangen wurde. Beachten Sie, dass diese Dimension den Wert "Wahr" haben wird, wenn ein QoE-Bericht von einem der beiden Endpunkte empfangen wurde. Ein QoE-Bericht von beiden Endpunkten ist erforderlich, um eine möglichst genaue Berichterstellung der Metriken zu ermöglichen.

- **Kurzanrufe** - Kurzanrufe verfügen möglicherweise nicht über genügend Medienaktivität, um wichtige Datenstrommetriken zu berechnen. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.

> [!TIP]
> Die Dimensionen "Dauer (Sekunden)", "Dauer (Minuten)", "Dauer 5 Sekunden oder weniger" und "Dauer 60 Sekunden oder mehr" können zur Bestimmung der Dauer eines Datenstrom verwendet werden. Mithilfe der Messung "Durchschnittliche Anrufdauer" können Sie die durchschnittliche Dauer eines Satzes von Datenströmen berechnen.

- **Niedrige Paketauslastung** - Wie beim "Kurzanruf"-Szenario ist eine ausreichende Paketauslastung für die Berechnung von Schlüsselmetriken des Datenstroms erforderlich. Ohne diese Metriken ist AQD nicht in der Lage, den Datenstrom zu klassifizieren.
    - Ein häufiges Szenario mit geringer Paketauslastung tritt auf, wenn ein Benutzer an einer Besprechung teilnimmt, um dem Moderator zuzuhören, aber nie spricht (wahrscheinlich schaltet er das Mikrofon für den größten Teil des Anrufs stumm). In einem solchen Szenario hat ein Audiodatenstrom eine hohe Paketauslastung (Eingehend zum Client), während der andere wenig bis gar keine Paketauslastung hat (Ausgehend vom Client). In diesem Szenario kann die Dauer des Datenstroms eine Stunde oder länger sein, aber die Paketauslastung auf dem Datenstrom vom Client zum Server ist aufgrund der Stummschaltung des Mikrofons extrem gering, was zu einem nicht klassifizierten Datenstrom führt.

> [!TIP]
> Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.


## <a name="related-topics"></a>Verwandte Themen
[Aktivieren und Verwenden von Anrufen Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)
