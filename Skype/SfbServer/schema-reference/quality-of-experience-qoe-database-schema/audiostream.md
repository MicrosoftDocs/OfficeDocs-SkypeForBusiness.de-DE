---
title: AudioStream-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Jeder Datensatz steht für einen Audiodatenstrom. Eine Audiomedien Zeile enthält in der Regel zwei Audiostreams.
ms.openlocfilehash: 7c1e7ae70a04aabc7db704aaaad873bc5b2100c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894135"
---
# <a name="audiostream-table"></a>AudioStream-Tabelle
 
Jeder Datensatz steht für einen Audiodatenstrom. Eine Audiomedien Zeile enthält in der Regel zwei Audiostreams.
  
|Spalte|Datentyp|Schlüssel/Index|Details|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer medienzeile.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher netzwerkjitter aus Statistik (Real Time Control Protocol, RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler netzwerkjitter während des Anrufs.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale paketverlustrate während des Anrufs.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Paketwert für den Audiostream.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Bandbreitenschätzwerte für den Audiostream.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Werte sind 0,0, 5.0 ist. Diese Metrik zeigt die Dauer, dass die Netzwerk-MOS aufgrund von Jitter und Paketverlust reduziert wurde. Für eine akzeptable Qualität sollte es weniger als 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Ausländisch  <br/> |Verwendete Audiocodec für den Anruf, verwiesen von der PayloadDescription-Tabelle.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Samplingrate für den Audiostream.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik. Für eine akzeptable Qualität sollte dies weniger als 100 ms sein.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Durchschnittliche Breitband-Netzwerk-MOS für den Anruf. Dieser Metrik hängt davon ab, die Paketverluste, Jitter und verwendeten Codecs. Bereich ist [1.0-5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die minimaler Breitband-Netzwerk-MOS für den Anruf.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendete Audios, einschließlich sprachpegel, Rauschen und aufnahmegerätmerkmale.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Für gesendete Audios für den Anruf.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die durchschnittliche vorhergesagter Breitband-Hör-MOS für Audio empfangen aus dem Netzwerk, einschließlich sprachpegel, Rauschen, Codec, netzwerkbedingungen und aufnahmegerätmerkmale.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Minimaler RecvListenMOS für den Anruf.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Flag gibt an, ob audio-FEC für den Anruf verwendet wurde.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|**Eingehend** <br/> |bit  <br/> | <br/> |Streamdaten empfangen auf Empfängerseite empfangen werden.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Streamdaten empfangen auf der Seite Absender empfangen werden.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die streamrichtung vom Anrufer zum angerufenen verläuft.  <br/> 0 bedeutet, dass die streamrichtung vom angerufenen zum Anrufer verläuft.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Standardabweichung für Jitter-Ankunftszeiten.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Maximales Verhältnis der Pakete, die von der Reparatur ausgeblendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Standardabweichung für das Verhältnis der Pakete, die von der Reparatur ausgeblendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Verhältnis der Pakete, die von der Reparatur zur Gesamtanzahl der empfangenen Pakete gelöscht.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Verhältnis der verwendeten vorwärtsfehler-korrekturpakete zur Gesamtanzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Maximale Anzahl der audiopakete, die von der Reparatur komprimiert wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, wenn der Aufruf in einem Verlust Überlastung Zustand war.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz des Anrufs, in dem eine Überlastung aufgrund der verzögerten Ankunft von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit wenn der Anruf im Wettbewerb Netzwerkressourcen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Mindest-bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Größe des bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der bandbreitenschätzung, die während des Anrufs gemessen werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche bandbreitenschätzung während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Die Gesamtmenge des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Dauer der unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Größe des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Insgesamt unidirektionale Bursts vorkommen. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Insgesamt unidirektionale Bursts Dichte. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Insgesamt unidirektionale Bursts Dauer. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Unidirektionale lückenvorkommen insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Unidirektionale lückendichte insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Unidirektionale lückendauer insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs Stereo dekodiert.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der von der echounterdrückung Stereo dekodiert gerendert.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Paketverlustrate nach dem Anwenden der vorwärtsfehlerkorrektur.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs in Stereo kodiert wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs in Stereo kodiert wurde von der echounterdrückung Stereo erfasst.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
