---
title: Datenstromklassifizierung im Anrufqualitäts-Dashboard
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Erfahren Sie, wie die Datenstromqualität im Anrufqualitäts-Dashboard für Microsoft-Teams und Skype for Business Online klassifiziert wird.
ms.openlocfilehash: a77ca0605589c99b88ba3287bf8febcc7514cbd1
ms.sourcegitcommit: e5a54e2ead0edd9e450bbed4b6e50b3cfd2e91c0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "21645308"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Datenstromklassifizierung im Anrufqualitäts-Dashboard

Mit dem Anrufqualitäts-Dashboard (AQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams- und Skype for Business-Diensten getätigt wurden. Unter diesem Thema finden Sie detaillierte Informationen über die Qualitätsklassifizierung von Mediendatenströmen. Weitere Informationen zum AQD und dessen Aktivierung finden Sie unter [Aktivieren und Verwenden des Anrufqualitäts-Dashboards](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Klassifizierungsdefinitionen

Datenstöme in AQD werden aufgrund der Werte der verfügbaren Schlüssel-Qualitätsmetriken als gut, schlecht oder nicht klassifiziert eingestuft. Die zur Klassifizierung des Datenstroms verwendeten Metriken und Bedingungen werden in den folgenden Tabellen aufgeführt. Mit den "Schlecht aufgrund"-Dimensionen von AQD können Sie verstehen, welche Metrik für eine schlechte Klassifizierung verantwortlich ist. Weitere Informationen zu diesen Dimensionen finden Sie unter [Dimensionen und Kennzahlen im Anrufqualitäts-Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Audio-Klassifizierung

Ein Audiodatenstrom wird als schlecht gekennzeichnet, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:

|**Metrik**|**Bedingung**|**Erklärung**|
|:-----|:-----|:-----|
|Durchschnittliche Audioleistungsminderung|> 1,0|Beeinträchtigung des durchschnittlichen MOS (Mean Opinion Score) für den Datenstrom. Gibt an, wie sehr sich Netzwerkverlust und Jitter auf die empfangene Audioqualität ausgewirkt haben.|
|Roundtrip|> 500|Durchschnittliche in Millisekunden berechnete Roundtripzeit bei der Netzwerkverteilung, wie in RFC3550 angegeben.|
|Paketverlustrate|> 0,1|Durchschnittlich Paketverlustrate für Datenstrom.|
|Jitter|> 30|Durchschnittliche Anzahl an Jitter-Daten für Datenstrom in Millisekunden.|
|Durchschnittliches Verhältnis der verborgenen Stichproben|> 0,07|Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Stichproben, die durch den verdeckten Paketverlust generiert wurden, zur Gesamtzahl der Audioframes.|

### <a name="video-classifier"></a>Video-Klassifizierung

Ein Videodatenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als gut oder schlecht gekennzeichnet:

|**Schritt #**|**Metrik**|**Bedingung**|**Klassifizierung, wenn die Bedingung wahr ist**|**Klassifizierung, wenn die Bedingung falsch ist**|**Klassifizierung, wenn die Metrik nicht verfügbar ist**|**Erklärung**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Durchschnittlicher Prozentsatz des lokalen Video-Frameverlusts|> 50 % |Schlecht|Gut|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Darin enthalten sind die aus Netzwerkverlusten wiederhergestellten Frames.|
|2|Video-Framerate Mittelw.|< 7|Schlecht|Gut|Mit Schritt 3 fortfahren|Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video-Post-FECPLR|> 0,15|Schlecht|Gut|Nicht klassifiziert|Paketverlustrate nach FEC wurde aggregiert über alle Videostreams und Codecs angewendet.|

### <a name="vbss-classifier"></a>VBSS-Klassifizierung

Ein VBSS-Videodatenstrom wird basierend auf dem Wert der ersten verfügbaren Metrik in der folgenden Reihenfolge als gut oder schlecht gekennzeichnet:

|**Schritt #**|**Metrik**|**Bedingung**|**Klassifizierung, wenn die Bedingung wahr ist**|**Klassifizierung, wenn die Bedingung falsch ist**|**Klassifizierung, wenn die Metrik nicht verfügbar ist**|**Erklärung**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Durchschnittlicher Prozentsatz des lokalen Video-Frameverlusts|> 50 % |Schlecht|Gut|Mit Schritt 2 fortfahren|Durchschnittlicher Prozentsatz der dem Benutzer angezeigten verlorenen Videodatenströme. Darin enthalten sind die aus Netzwerkverlusten wiederhergestellten Frames.|
|2|Durchschnittliche Video-Framerate|< 2|Schlecht|Gut|Mit Schritt 3 fortfahren|Durchschnittliche Anzahl der pro Sekunde empfangenen Frames für einen Videodatenstrom, die für die Dauer einer Sitzung verarbeitet wurden.|
|3|Video-Post-FECPLR|> 0,15|Schlecht|Gut|Nicht klassifiziert|Paketverlustrate nach FEC wurde aggregiert über alle Videostreams und Codecs angewendet.|

### <a name="application-sharing-classifier"></a>Anwendungsfreigabe-Klassifizierung

Ein Anwendungsfreigabedatenstrom wird als schlecht gekennzeichnet, wenn eine oder mehrere der folgenden Bedingungen erfüllt sind:

**Metrik**|**Bedingung**|**Erklärung**|
|:-----|:-----|:-----|
|Spoiled Tile Percent Total|> 36|Prozentsatz der Kacheln, die verworfen werden, anstatt an einen Remote-Peer gesendet zu werden (zum Beispiel von einem MCU zu einem Viewer). Verworfene (oder schlechte) Kacheln sind auf eine Beschränkung der Bandbreite zwischen Client und Server zurückzuführen.|
|Durchschnittliche AppSharing RDP-Kachelverarbeitungslatenz|> 400|Durchschnittliche Latenz in Millisekunden bei der Verarbeitung von Kacheln im RDP-Stapel auf dem Konferenzserver.|
|Durchschnittliches relatives unidirektionales AppSharing|> 1,75|Durchschnittliche relative unidirektionale Verzögerung zwischen den Endpunkten in Sekunden für Anwendungs-Teilungsströme.|

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
[Aktivieren und Verwenden des Anrufqualitäts-Dashboards (AQD)](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)
