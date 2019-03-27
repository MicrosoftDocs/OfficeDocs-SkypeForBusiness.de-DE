---
title: VideoStream-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Jeder Datensatz steht für einen Videodatenstrom. Eine Videomedien Zeile enthält in der Regel zwei Videostreams.
ms.openlocfilehash: d6eeeb96acc766859d6b57594bd11a5538593da3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881681"
---
# <a name="videostream-table"></a>VideoStream-Tabelle
 
Jeder Datensatz steht für einen Videodatenstrom. Eine Videomedien Zeile enthält in der Regel zwei Videostreams.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer medienzeile.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Fremd, Primär  <br/> |Beschreibung der Nutzlast. Finden Sie weitere Informationen der [PayloadDescription-Tabelle](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher netzwerkjitter aus Statistik (Real Time Control Protocol, RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler netzwerkjitter während der videositzung.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Videostream.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale paketverlustrate während des Anrufs.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Paketwert für den Videostream (Real-Time Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Bandbreitenschätzwerte für den Videostream.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Auflösung des Videos in Pixel Breite, Höhe multipliziert. Gemeldet als Zeichenfolge.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die videoframerate empfangen.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die videoframerate gesendet.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Die maximale Videobitrate während der videositzung.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |Der Prozentsatz der gesamten Videoframes, die verloren gegangen sind.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Nicht verfügbar.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||Der Prozentsatz der gesamten Videoframes, die verloren gegangen sind.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs, der in der Common Interchange Format (CIF)-Auflösung.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Prozentsatz des Anrufs in VGA-Auflösung.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Prozentsatz des Anrufs in HD720-Auflösung.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit ohne Frame-Löschung.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit B-Frame-Löschung.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BP-Frame-Löschung.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSP-Frame-Löschung.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSPI-Frame-Löschung.  <br/> |
|**Eingehend** <br/> |bit  <br/> | <br/> |Streamdaten empfangen auf Empfängerseite empfangen werden.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Streamdaten empfangen auf der Seite Absender empfangen werden.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die streamrichtung vom Anrufer zum angerufenen verläuft.  <br/> 0 bedeutet, dass die streamrichtung vom angerufenen zum Anrufer verläuft.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, wenn der Aufruf in einem Verlust Überlastung Zustand war.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz des Anrufs, in dem eine Überlastung aufgrund der verzögerten Ankunft von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit wenn der Anruf im Wettbewerb Netzwerkressourcen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Mindest-bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Größe des bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche bandbreitenschätzung während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Prozentsatz des Anrufs, wobei der Endpunkt bestimmt, dass die Netzwerkverbindung multiview-Video nicht unterstützen kann.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Die Gesamtmenge des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Dauer der unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Größe des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Insgesamt unidirektionale Bursts vorkommen. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Insgesamt unidirektionale Bursts Dichte. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Insgesamt unidirektionale Bursts Dauer. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Unidirektionale lückenvorkommen insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Unidirektionale lückendichte insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Unidirektionale lückendauer insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Rate, bei der Videopakete verlorengingen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Durchschnittliche reservierte Bandbreite für Video.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Ausländisch  <br/> |Typ des video-Codecs vom Absender verwendete. Finden Sie weitere Informationen der [CodecDescription-Tabelle](codecdescription.md) . <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Vom Absender verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Vom Absender verwendete auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche videoframerate bei der Übertragung vom Absender verwendete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Absender.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Absender.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl der vom Absender verwendeten Videostreams.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Ausländisch  <br/> |Video Codes vom Empfänger verwendet. Finden Sie weitere Informationen der [CodecDescription-Tabelle](codecdescription.md) . <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Vom anrufempfänger verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Vom anrufempfänger verwendete auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Framerate des Videostreams vom Empfänger verwendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate des anrufempfängers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate des anrufempfängers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl an Videostreams des anrufempfängers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Minimale Videostreams des anrufempfängers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Video Modus (beispielsweise Katalog oder einzelnen Datenstrom) für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Paketverlustrate nach dem Anwenden der vorwärtsfehlerkorrektur.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Prozentsatz der Zeit, die die Kennzeichen für dynamische Funktionen aktiv war.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Minimale Auflösung während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs unter dem Schwellenwert für geringe Bit von Rate (70 Kbit / s).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der unter dem Schwellenwert für geringe Framerate (7,5 Frames pro Sekunde, eingehend).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der bei geringster Auflösung aufgetreten ist.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Dauer des Anrufs in Sekunden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Gibt an, ob die Daten aus mehreren anrufen zusammengefasst wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

