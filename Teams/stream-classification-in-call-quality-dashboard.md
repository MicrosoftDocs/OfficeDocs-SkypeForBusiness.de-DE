---
title: Datenstromklassifizierung im Anrufqualitäts-Dashboard
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
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
ms.openlocfilehash: 43c3e876b041e8a586b43d21f049731e3450a1a4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374325"
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
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Durchschnittliche unidirektionale relative Verzögerung zwischen den Endpunkten in Sekunden für die Anwendungsfreigabe Datenströme.                                                                                                                       |

## <a name="unclassified-streams"></a>Nicht klassifizierte Datenströme

In AQD wird ein Datenstrom als nicht klassifiziert gekennzeichnet, wenn die ICE-Konnektivität fehlschlägt oder wenn nicht alle für die Berechnung der Datenstromklassifizierung erforderlichen Metriken gemeldet werden.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> Mit der Dimension "Paketauslastung" und der Messung "Durchschnittliche Paketauslastung" kann die Paketaktivität eines Datenstroms bestimmt werden.


## <a name="related-topics"></a>Verwandte Themen
[Aktivieren und Verwenden von Anrufen Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)
