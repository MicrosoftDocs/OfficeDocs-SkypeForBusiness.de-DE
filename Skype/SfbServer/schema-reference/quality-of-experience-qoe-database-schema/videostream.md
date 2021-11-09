---
title: VideoStream-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Jeder Datensatz stellt einen Videostream dar. Eine Videomedienzeile enthält in der Regel zwei Videostreams.
ms.openlocfilehash: 5e1b566db7ee3f79219835055d6e617beeea6da6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863252"
---
# <a name="videostream-table"></a>VideoStream-Tabelle
 
Jeder Datensatz stellt einen Videostream dar. Eine Videomedienzeile enthält in der Regel zwei Videostreams.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R, auf das aus der [MediaLine-Tabelle](medialine-0.md)verwiesen wird.  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|**VideoPayloadDescription** <br/> |Smallint  <br/> |Fremd, Primär  <br/> |Nutzlastbeschreibung. Weitere Informationen finden Sie in der [PayloadDescription-Tabelle.](payloaddescription.md) <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximale Netzwerk-Jitter während der Videositzung.  <br/> |
|**Roundtrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Videostream.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Paketwert für den Videostream (Real Time Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Bandbreitenvoranschläge für den Videodatenstrom.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die empfangene Videoframerate.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die gesendete Videoframerate.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Die maximale Videobitrate während der Videositzung.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |Der Prozentsatz der Gesamtzahl der verloren gegangenen Videoframes.  <br/> |
|**VideoFEC** <br/> |Bit  <br/> | <br/> |Nicht verfügbar.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||Der Prozentsatz der Gesamtzahl der verloren gegangenen Videoframes.  <br/> |
|**CIFQualityRatio** <br/> |Tinyint  <br/> ||Der Prozentsatz des Anrufs, der die CIF-Auflösung (Common Interchange Format) aufweist.  <br/> |
|**VGAQualityRatio** <br/> |Tinyint  <br/> ||Der Prozentsatz des Anrufs mit VGA-Auflösung.  <br/> |
|**HD720QualityRatio** <br/> |Tinyint  <br/> ||Der Prozentsatz des Anrufs mit HD720-Auflösung.  <br/> |
|**NoneDropRatio** <br/> |Tinyint  <br/> ||Prozentsatz der Anrufdauer ohne Frame drop.  <br/> |
|**BDropRatio** <br/> |Tinyint  <br/> ||Prozentsatz der Anrufdauer mit B-Frame-Drop.  <br/> |
|**BPDropRatio** <br/> |Tinyint  <br/> ||Prozentsatz der Anrufdauer mit BP-Frame-Drop.  <br/> |
|**BPSPDropRatio** <br/> |Tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSP-Frame drop.  <br/> |
|**BPSPIDropRatio** <br/> |Tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSPI-Frame-Drop.  <br/> |
|**Eingehende** <br/> |Bit  <br/> | <br/> |Streamdaten auf Empfängerseite werden empfangen.  <br/> |
|**Ausgehend** <br/> |Bit  <br/> | <br/> |Streamdaten auf Absenderseite werden empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |Bit  <br/> | <br/> |1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.  <br/> 0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
|**LossCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, in der sich der Anruf in einem Überlastungszustand befand.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz des Anrufs an, bei dem die Überlastung durch die verzögerte Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, in der der Anruf um Netzwerkressourcen konkurrieren konnte.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimale Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBandwidthForMultiview** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung Kein Multiview-Video unterstützt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |Gleitkommazahl  <br/> ||Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Undirektionale Burstvorkommen insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Undirektionale Burstdichte insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdauer insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtzahl der vorkommende unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |Gleitkommazahl  <br/> ||Gesamtdichte der unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |Gleitkommazahl  <br/> ||Gesamtdauer der unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Videpaketverlustrate.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Durchschnittliche für Video reservierte Bandbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendCodecTypes** <br/> |Smallint  <br/> |Ausländisch  <br/> |Typ der vom Absender verwendeten Videocodecs. Weitere Informationen finden Sie in der [CodecDescription-Tabelle.](codecdescription.md) <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Vom Absender verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Vom Absender verwendete Auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Übertragung der Videoframerate, die vom Absender verwendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Absender.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Absender.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl von Videostreams, die vom Absender verwendet werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvCodecTypes** <br/> |Smallint  <br/> |Ausländisch  <br/> |Vom Empfänger verwendete Videocodes. Weitere Informationen finden Sie in der [CodecDescription-Tabelle.](codecdescription.md) <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Vom Empfänger verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Vom Empfänger verwendete Auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche vom Empfänger verwendete Videoframerate.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Maximale Videodatenströme für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Minimale Videodatenströme für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Videomodus (z. B. Katalog oder einzelner Datenstrom) für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPostFECPLR** <br/> |Gleitkommazahl  <br/> ||Paketverlustrate nach Anwendung der Weiterleitungsfehlerkorrektur.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DynamicCapabilityPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz der Zeit, in der das Flag für dynamische Funktionen aktiv war.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Während des Anrufs gemessene Mindestauflösung.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBitRateCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs unterhalb des Schwellenwerts für die niedrige Bitrate (70 Kilobit pro Sekunde).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowFrameRateCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs unterhalb des schwellenwerts für die niedrige Framerate (7,5 Frames pro Sekunde, eingehend).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowResolutionCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DurationSeconds** <br/> |Gleitkommazahl  <br/> ||Dauer des Anrufs in Sekunden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**IsAggregatedData** <br/> |Bit  <br/> ||Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

