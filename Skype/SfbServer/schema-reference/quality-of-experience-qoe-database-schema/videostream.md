---
title: VideoStream-Tabelle
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
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Jeder Datensatz steht für einen Videostream. Eine Video medienzeile enthält in der Regel zwei Videostreams.
ms.openlocfilehash: 7eca8335ccf6905d3f80dd6ad8a5ccf00b749b39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804235"
---
# <a name="videostream-table"></a>VideoStream-Tabelle
 
Jeder Datensatz steht für einen Videostream. Eine Video medienzeile enthält in der Regel zwei Videostreams.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R, auf die in der [Tabelle "medialinie](medialine-0.md)" verwiesen wird  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|**Datenstrom-Nr** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer medienzeile  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Fremd, primär  <br/> |Nutzlast-Beschreibung. Weitere Informationen finden Sie in der [PayloadDescription-Tabelle](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler Netzwerk Jitter während der Videositzung.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtrip-Zeit von RTCP-Statistiken  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtrip-Zeit für den Videostream.  <br/> |
|**PacketLossRate** <br/> |Dezimal (5; 4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |Dezimal (5; 4)  <br/> | <br/> |Maximaler Paketverlust während des Anrufs.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Paketanzahl für den Videostream (Echt Zeit Transport Protokoll, RTP).  <br/> |
|**Bandbreite** <br/> |int  <br/> | <br/> |Bandbreiten Schätzungen für den Videostream.  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |Auflösung des Videos in Pixel Breite multipliziert mit Höhe des Pixels. Als Zeichenfolge gemeldet.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Durchschnittliche Bitrate des Videodatenstroms.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |Dezimal (9; 4)  <br/> | <br/> |Die empfangene Videobildrate.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |Dezimal (9; 4)  <br/> | <br/> |Die Videobildrate wird gesendet.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Die maximale Video-Bitrate während der Videositzung.  <br/> |
|**VideoFrameLossRate** <br/> |Dezimal (9; 4)  <br/> | <br/> |Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Nicht verfügbar.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |Dezimal (9; 4)  <br/> ||Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs, der sich in der CIF-Auflösung (Common Interchange Format) befand.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs mit VGA-Auflösung.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs, der mit der HD720-Auflösung erfolgte.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer ohne Frame-Drop  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit B-Frame-Abwurf.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BP-Frame-Drop.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSP Frame Drop.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSPI Frame Drop.  <br/> |
|**Inbound** <br/> |bit  <br/> | <br/> |Datenstrom auf Empfängerseite wird empfangen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Datenstrom auf Absenderseite wird empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die Datenstrom Richtung vom Aufrufer zu aufgerufen wird.  <br/> 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Engpass Zustand befand.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verspätete Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, zu der der Anruf im Wettbewerb um Netzwerkressourcen erfolgte.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimaler Grad der Bandbreitenschätzung, gemessen während des Anrufs.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung MultiView-Video nicht unterstützenkann.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Gesamtzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Anzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Anzahl von unidirektionalen Latenzzeiten. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Gesamtzahl der einseitigen Burst-Ereignisse. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Totale unidirektionale Burst Dichte. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Gesamtdauer des einseitigen Bursts. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtanzahl der einseitigen Lücken. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Gesamtdichte für einseitigen Abstand. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Gesamtdauer der einseitigen Lücke Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**VideoPacketLossRate** <br/> |Dezimal (9; 4)  <br/> ||Die Rate, mit der Videopakete verloren gegangen sind.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Der durchschnittliche Umfang der für Video zugewiesenen Bandbreite.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Fremd  <br/> |Der Typ der vom Absender verwendeten Video-Codecs. Weitere Informationen finden Sie in der [CodecDescription-Tabelle](codecdescription.md) . <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Vom Absender verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Die vom Absender verwendete auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Übertragungsrate für Video-Frames, die vom Absender verwendet wird.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Die maximale Bitrate für den Absender.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Absender.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl der vom Absender verwendeten Videodatenströme.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Fremd  <br/> |Vom Empfänger verwendete Video Codes. Weitere Informationen finden Sie in der [CodecDescription-Tabelle](codecdescription.md) . <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Vom Empfänger verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Vom Empfänger verwendete auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Maximale Videodatenströme für den Empfänger.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Minimale Videodatenströme für den Empfänger.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Video Modus (beispielsweise Katalog oder einzelner Datenstrom) für den Empfänger.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Die Paketverlustrate, nachdem die weiter Leitungsfehler Korrektur angewendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Der Prozentsatz der Zeit, zu der das Flag für dynamische Funktionen aktiv war.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||Minimale Auflösung während des Anrufs gemessen.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Der Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Bitraten (70 Kbit/s).  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**Framerate (** <br/> |float  <br/> ||Der Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Bildrate (7,5 Frames pro Sekunde, eingehend).  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Der Prozentsatz des Anrufs, der mit der niedrigsten Auflösung erfolgte.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Die Länge des Anrufs in Sekunden.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Gibt an, ob die Daten aus mehreren anrufen aggregiert wurden.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

