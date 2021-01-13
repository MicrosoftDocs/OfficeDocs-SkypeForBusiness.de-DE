---
title: Tabelle "VideoStream"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Jeder Datensatz stellt einen Videostream dar. Eine Videomedienzeile enthält in der Regel zwei Videostreams.
ms.openlocfilehash: e506f022dbfa4ef0a1a8578dc6caf7c0f3984fa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821325"
---
# <a name="videostream-table"></a>Tabelle "VideoStream"
 
Jeder Datensatz stellt einen Videostream dar. Eine Videomedienzeile enthält in der Regel zwei Videostreams.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Fremd, Primär  <br/> |Nutzlastbeschreibung. Weitere Informationen [finden Sie in der Tabelle PayloadDescription.](payloaddescription.md) <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler Netzwerk-Jitter während der Videositzung.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Videostream.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Paketwert für den Videostream (Real Time Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Geschätzte Bandbreite für den Videostream.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die empfangene Videoframerate.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Die gesendete Videoframerate.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Die maximale Videobitrate während der Videositzung.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |Der Prozentsatz der Gesamtvideoframes, die verloren gehen.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Nicht verfügbar.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||Der Prozentsatz der Gesamtvideoframes, die verloren gehen.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs, für den die #A0 (Common Interchange Format) verwendet wurde.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs mit VGA-Auflösung.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Der Prozentsatz des Anrufs mit HD720-Auflösung.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer ohne Frame drop.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit B-Frame-Drop.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit Bp Frame Drop.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSP Frame Drop.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Prozentsatz der Anrufdauer mit BPSPI-Frame-Drop.  <br/> |
|**Eingehende Nachrichten** <br/> |bit  <br/> | <br/> |Daten auf Empfängerseite werden empfangen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Streamdaten auf Absenderseite werden empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.  <br/> 0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
|**LossCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Verlustüberlastungszustand aufting.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verzögerte Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, zu der der Anruf um Netzwerkressourcen konkurriert hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimale Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBandwidthForMultiview** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung Multiviewvideos nicht unterstützen konnte.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |Gleitkommazahl  <br/> ||Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Undirektionale Burstvorkommen insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Undirektionale Burstdichte insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdauer insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtanzahl der vorkommenden one-way-Lücken. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |Gleitkommazahl  <br/> ||Gesamtdichte für die einweg-lücke. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |Gleitkommazahl  <br/> ||Gesamtdauer der ein- und auswegsen Lücken. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Videpaketverlustrate.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Durchschnittliche für Video reservierte Bandbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Fremd  <br/> |Typ der vom Absender verwendeten Videocodecs. Weitere Informationen finden Sie in der [Tabelle "CodecDescription".](codecdescription.md) <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Vom Absender verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Vom Absender verwendete Auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Übertragungsrate von Videoframes, die vom Absender verwendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Absender.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Absender.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl von Videostreams, die vom Absender verwendet werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Fremd  <br/> |Vom Empfänger verwendete Videocodes. Weitere Informationen finden Sie in der [Tabelle "CodecDescription".](codecdescription.md) <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Vom Empfänger verwendete Auflösungsbreite.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Vom Empfänger verwendete Auflösungshöhe.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Videoframerate, die vom Empfänger verwendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Maximale Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Durchschnittliche Bitrate für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Maximale Anzahl von Videostreams für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Minimale Videostreams für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Videomodus (z. B. Katalog oder einzelner Datenstrom) für den Empfänger.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**VideoPostFECPLR** <br/> |Gleitkommazahl  <br/> ||Paketverlustrate, nachdem die Vorwärtsfehlerkorrektur angewendet wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DynamicCapabilityPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz der Zeit, in der das Flag für dynamische Funktionen aktiv war.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Minimale Auflösung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowBitRateCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs unter dem Schwellenwert für die niedrige Bitrate (70 Kilobits pro Sekunde).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowFrameRateCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs unter dem Schwellenwert für die niedrige Framerate (7,5 Frames pro Sekunde, eingehende Daten).  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LowResolutionCallPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der mit der niedrigsten Auflösung erfolgt ist.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DurationSeconds** <br/> |Gleitkommazahl  <br/> ||Die Dauer des Anrufs in Sekunden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

