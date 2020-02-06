---
title: AppSharingStream-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: Die AppSharingStream-Tabelle enthält die Qualität der Erfahrungswerte für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811103"
---
# <a name="appsharingstream-table"></a>AppSharingStream-Tabelle
 
Die AppSharingStream-Tabelle enthält die Qualität der Erfahrungswerte für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Primär, fremd  <br/> |Das Datum und die Uhrzeit, zu der die Sitzung gestartet wurde.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Sequenzielle Kennung, die verwendet wird, um zwischen Sitzungen zu unterscheiden, die am gleichen Datum und zur gleichen Zeit gestartet wurden.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, fremd  <br/> | Siehe [medialinie-Tabelle](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**Datenstrom-Nr** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner des Anwendungsfreigabe Datenstroms.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Maximaler Jitter zwischen den Ankünften des RTP-Pakets. (Jitter ist ein Maß für die "Zittern" eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Der Höchstbetrag (in Millisekunden), der für ein echt Zeit Transport Protokoll Paket erforderlich ist, um zu einem anderen Endpunkt zu wechseln und dann zurückzukehren. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Maximale Rate des RTP-Paketverlusts (Real-Time Transport Protocol). (Paketverlust tritt auf, wenn RTP-Pakete, ein Protokoll, das für die Übertragung von Audio und Video über das Internet verwendet wird, das Ziel nicht erreicht haben.) In der Regel sind die großen Verlustraten auf Engpässe zurückzuführen. mangelnde Bandbreite; WLAN-Überlastung oder Störungen; oder einen überladenen Medienserver. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Die Anzahl der gesendeten Pakete.  <br/> |
|**Bandbreite** <br/> |int  <br/> ||Geschätzte einseitige Bandbreite, die am Ende der Sitzung zur Verfügung steht. In Bits pro Sekunde gemeldet.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Beschreibung der Anwendungsfreigabe Nutzlast.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Gesamtzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Anzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Anzahl von unidirektionalen Latenzzeiten. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Gesamtzahl der einseitigen Burst-Ereignisse. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Totale unidirektionale Burst Dichte. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Gesamtdauer des einseitigen Bursts. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtanzahl der einseitigen Lücken. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Gesamtdichte für einseitigen Abstand. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Gesamtdauer der einseitigen Lücke Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||Anwendungsrolle (mitbenutzender oder Viewer) und Inhaltstyp.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Gesamtverarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Durchschnittliche Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Maximale Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Burst Dichte in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Burst Dauer in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Lücken Dichte in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Eine geringe Spalt Dichte entspricht einer besseren Anzeige Erfahrung.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Lücken Dauer in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol). Kurze Lücken dauern sind mit einer besseren Anzeige Erfahrung identisch.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Gesamtrate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Maximale Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |in t  <br/> ||Burst-Vorkommen in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in der Rate der aufgenommenen Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Spalt Dichte in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Dauer der Lücke in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Der Gesamtprozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Der durchschnittliche Prozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Der maximale Prozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Burst Dichte für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Burst Dauer für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Lücken auftreten für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Lücken Dichte für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Abstands Dauer für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Gesamtzahl der Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Die durchschnittliche Anzahl von Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Die maximale Anzahl von Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Spalt Dichte in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Lücken Dauer in den Frames, die aus der grafikquelle ausgekratzt wurden.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Gesamtzahl der eingehenden Bilder, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Durchschnittliche eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Die maximale eingehende Kachel Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Abstands Dichte in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Lücken Dauer in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Gesamtzahl der eingehenden Bilder, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Die maximale eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurden.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Abstands Dichte in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Die Unterbrechungsdauer in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Gesamtanzahl der ausgehenden Kacheln für den Absender.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Durchschnittliche Ausgangs Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Maximale Anzahl der ausgehenden Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Abstands Dichte in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Abstands Dauer in der ausgehenden Kachel Rate für den Absender.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Die gesamte Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||durchschnittliche Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Maximale Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burst-Vorkommen in der Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Burst Dichte in der Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Burst Dauer in der Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Lücken Vorkommen in der ausgehenden Framerate für den Absender.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Abstands Dichte in der Ausgangsbildrate für den Absender.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Lücken Dauer in der ausgehenden Framerate für den Absender.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Durchschnittliche Höhe der Videoauflösung in Pixeln.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Durchschnittliche Breite der Videoauflösung in Pixeln.  <br/> |
|**Inbound** <br/> |bit  <br/> ||Durchschnittliche Bildwiederholrate (in Frames pro Sekunde) für eingehende Übertragungen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> ||Durchschnittliche Bildwiederholrate (in Frames pro Sekunde) für ausgehende Übertragungen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 bedeutet, dass die Datenstrom Richtung vom Aufrufer zu aufgerufen wird.  <br/> 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.  <br/> |
   

