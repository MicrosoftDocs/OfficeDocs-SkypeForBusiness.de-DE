---
title: AudioStream-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Jeder Datensatz stellt einen Audiodatenstrom dar. Eine Audiomedienzeile enthält in der Regel zwei Audiodatenströme.
ms.openlocfilehash: 0ca913e042b988d20aad644af65fed7970d2afa8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763253"
---
# <a name="audiostream-table"></a>AudioStream-Tabelle
 
Jeder Datensatz stellt einen Audiodatenstrom dar. Eine Audiomedienzeile enthält in der Regel zwei Audiodatenströme.
  
|Spalte|Datentyp|Schlüssel/Index|Details|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler Netzwerkjitter während des Anrufs.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte von Paketverlusten bei Verlusten während des Anrufs.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Paketwert für den Audiostream.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Bandbreitenschätzungen für den Audiostream.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Ausländisch  <br/> |Der für den Anruf verwendete Audiocodec, auf den in "PayloadDescription Table" verwiesen wird.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Samplingrate für den Audiostream.  <br/> |
|**Roundtrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik. Für eine akzeptable Qualität sollte dies weniger als 100 ms sein.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich ist [1,0 bis 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Der minimale Wideband-Netzwerk-MOS für den Anruf.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die durchschnittliche prognostizierte WIDEBAND-MOS-Bewertung für gesendete Audiodaten, einschließlich Sprachniveau, Rauschniveau und Aufnahmegeräteeigenschaften.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Die minimale SendListenMOS für den Anruf.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die durchschnittliche prognostizierte WIDEBAND-MOS-Bewertung für vom Netzwerk empfangene Audiodaten, einschließlich Sprachniveau, Rauschniveau, Codec, Netzwerkbedingungen und Aufnahmegeräteeigenschaften.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Der mindeste RecvListenMOS für den Anruf.  <br/> |
|**AudioFECUsed** <br/> |Bit  <br/> ||Flag, das angibt, ob audio FEC für den Anruf verwendet wurde.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**Eingehende** <br/> |Bit  <br/> | <br/> |Streamdaten auf Empfängerseite werden empfangen.  <br/> |
|**Ausgehend** <br/> |Bit  <br/> | <br/> |Streamdaten auf Absenderseite werden empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |Bit  <br/> | <br/> |1 bedeutet, dass die Datenstromrichtung vom Aufrufer zum Angerufenen erfolgt.  <br/> 0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
|**JitterInterArrivalsd** <br/> |Gleitkommazahl  <br/> ||Standardabweichung für jitter-Ankunftszeiten.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioMax** <br/> |Gleitkommazahl  <br/> ||Maximales Verhältnis von Paketen, die von der Reparatur verdeckt werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioSD** <br/> |Gleitkommazahl  <br/> ||Standardabweichung für das Verhältnis von Paketen, die durch die Reparatur verdeckt werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerPacketDropRatio** <br/> |Gleitkommazahl  <br/> ||Das Verhältnis von Paketen, die von der Reparatur verworfen wurden, im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |Gleitkommazahl  <br/> ||Verhältnis der verwendeten Weiterleitungsfehlerkorrekturpakete im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MaxCompressedSamples** <br/> |Gleitkommazahl  <br/> ||Maximale Anzahl von Audiopaketen, die von der Wiege komprimiert wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LossCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, in der sich der Anruf in einem Überlastungszustand befand.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz des Anrufs an, bei dem die Überlastung durch die verzögerte Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, in der der Anruf um Netzwerkressourcen konkurrieren konnte.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimale Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Bandbreitenberechnung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |Gleitkommazahl  <br/> ||Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Undirektionale Burstvorkommen insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdichte insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdauer insgesamt. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen und nicht in einem beständigen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtzahl der vorkommende unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |Gleitkommazahl  <br/> ||Gesamtdichte der unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |Gleitkommazahl  <br/> ||Gesamtdauer der unidirektionale Lücke. Eine "stürmige" Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Brüchen im Gegensatz zu einem beständigen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Datenspitzen hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DecodeStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der als Stereo decodiert wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecRenderStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der vom akustischen Echounterdräger als Stereo gerendert wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AudioPostFECPLR** <br/> |Gleitkommazahl  <br/> ||Paketverlustrate nach Anwendung der Weiterleitungsfehlerkorrektur.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**EncodeStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der als Stereo codiert ist.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecCaptureStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der vom akustischen Echounterdräger als Stereo erfasst wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
