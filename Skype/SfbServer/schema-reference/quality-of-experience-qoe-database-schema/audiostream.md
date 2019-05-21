---
title: AudioStream-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Jeder Datensatz steht für einen Audiostream. Eine Audio-Media-Zeile enthält in der Regel zwei Audiostreams.
ms.openlocfilehash: eae96b08f3a365288f48b7a68c75d3fd9114107d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295048"
---
# <a name="audiostream-table"></a>AudioStream-Tabelle
 
Jeder Datensatz steht für einen Audiostream. Eine Audio-Media-Zeile enthält in der Regel zwei Audiostreams.
  
|Spalte|Datentyp|Schlüssel/Index|Details|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**Datenstrom-Nr** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer medienzeile  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler Netzwerk Jitter während des Anrufs.  <br/> |
|**PacketLossRate** <br/> |Dezimal (5; 4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |Dezimal (5; 4)  <br/> | <br/> |Maximaler Paketverlust während des Anrufs.  <br/> |
|**BurstDensity** <br/> |Dezimal (9; 4)  <br/> | <br/> |Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.  <br/> |
|**BurstGapDensity** <br/> |Dezimal (9; 4)  <br/> | <br/> |Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Die Anzahl der Pakete für den Audiostream.  <br/> |
|**Bandbreite** <br/> |Int  <br/> | <br/> |Bandbreiten Schätzungen für den Audiostream.  <br/> |
|**DegradationAvg** <br/> |Dezimal (3; 2)  <br/> | <br/> |Netzwerk-Mos-Verschlechterung für den gesamten Anruf. Der Bereich ist 0,0 bis 5,0. Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde. Für akzeptable Qualität sollte es weniger als 0,5.  <br/> |
|**DegradationMax** <br/> |Dezimal (3; 2)  <br/> | <br/> |Maximaler Netzwerk-Mos-Abbau während des Anrufs.  <br/> |
|**DegradationJitterAvg** <br/> |Dezimal (3; 2)  <br/> | <br/> |Netzwerk-Mos-Beeinträchtigung durch Jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |Dezimal (3; 2)  <br/> | <br/> |Netzwerk-Mos-Beeinträchtigung durch Paketverlust.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Fremd  <br/> |Der für den Anruf verwendete Audiocodec, auf den von der PayloadDescription-Tabelle verwiesen wird.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Abtastrate für den Audiostream.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtrip-Zeit von RTCP-Statistiken Bei akzeptabler Qualität sollte dies weniger als 100M betragen.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtrip-Zeit für den Audiostream.  <br/> |
|**OverallAvgNetworkMOS** <br/> |Dezimal (3; 2)  <br/> | <br/> |Durchschnittliche Breitband-Netzwerk-Mos für den Anruf. Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab. Bereich ist [1,0 bis 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |Dezimal (3; 2)  <br/> | <br/> |Das Mindest-Breitband-Netzwerk Mos für den Anruf.  <br/> |
|**SendListenMOS** <br/> |Dezimal (3; 2)  <br/> | <br/> |Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für gesendete Audiodaten, einschließlich der Eigenschaften für Sprachpegel, Geräuschpegel und Aufnahmegeräte.  <br/> |
|**SendListenMOSMin** <br/> |Dezimal (3; 2)  <br/> | <br/> |Die Mindest-SendListenMOS für den Anruf.  <br/> |
|**RecvListenMOS** <br/> |Dezimal (3; 2)  <br/> | <br/> |Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.  <br/> |
|**RecvListenMOSMin** <br/> |Dezimal (3; 2)  <br/> | <br/> |Die Mindest-RecvListenMOS für den Anruf.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |Dezimal (5; 2)  <br/> ||Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |Dezimal (5; 2)  <br/> ||Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |Dezimal (5; 2)  <br/> ||Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.  <br/> |
|**Inbound** <br/> |bit  <br/> | <br/> |Datenstrom auf Empfängerseite wird empfangen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Datenstrom auf Absenderseite wird empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die Datenstrom Richtung vom Aufrufer an den aufgerufenen gesendet wird.  <br/> 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Standard Abweichung für Jitter-Ankunftszeiten.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Das Verhältnis der vom Heiler abgegebenen Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Die maximale Anzahl von Audiopaketen, die vom Heiler komprimiert wurden.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Engpass Zustand befand.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verspätete Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Gibt den Prozentsatz der Zeit an, zu der der Anruf im Wettbewerb um Netzwerkressourcen erfolgte.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimaler Grad der Bandbreitenschätzung, gemessen während des Anrufs.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Gesamtzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Anzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Anzahl von unidirektionalen Latenzzeiten. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Gesamtzahl der einseitigen Burst-Ereignisse. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Totale unidirektionale Burst Dichte. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Gesamtdauer des einseitigen Bursts. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtanzahl der einseitigen Lücken. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Gesamtdichte für einseitigen Abstand. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Gesamtdauer der einseitigen Lücke Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der als Stereo decodiert wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Die Paketverlustrate, nachdem die weiter Leitungsfehler Korrektur angewendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Prozentsatz des als Stereo codierten Anrufs.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo aufgenommen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
