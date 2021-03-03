---
title: Tabelle "AudioStream"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Jeder Datensatz stellt einen Audiodatenstrom dar. Eine Audiomedienzeile enthält in der Regel zwei Audiostreams.
ms.openlocfilehash: e24a5c8611c3f6bf7b56edf342aa2595f6794a90
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831365"
---
# <a name="audiostream-table"></a>Tabelle "AudioStream"
 
Jeder Datensatz stellt einen Audiodatenstrom dar. Eine Audiomedienzeile enthält in der Regel zwei Audiostreams.
  
|Spalte|Datentyp|Schlüssel/Index|Details|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maximaler Netzwerkjitter während des Anrufs.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte des Paketverlusts während Verlust bursts während des Anrufs.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Paketwert für den Audiostream.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Bandbreitenschätzungen für den Audiostream.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Fremd  <br/> |Der für den Anruf verwendete Audiocodec, auf den in der PayloadDescription Table verwiesen wird.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Samplingrate für den Audiostream.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Roundtripzeit aus RTCP-Statistik. Für eine akzeptable Qualität sollte dies weniger als 100 ms sein.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich ist [1,0 bis 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Der Minimale Breitband-Netzwerk-MOS für den Anruf.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die durchschnittliche vorhergesagte Wideband-Listening-MOS-Bewertung für gesendete Audiodaten, einschließlich Sprachstufe, Rauschstufe und Aufnahmegeräteigenschaften.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Der Mindestwert von SendListenMOS für den Anruf.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Die durchschnittliche vorhergesagte Wideband-Listening-MOS-Bewertung für aus dem Netzwerk empfangene Audiodaten, einschließlich Sprach-, Rausch-, Codec-, Netzwerkbedingungen und Aufnahmegerätemerkmale.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Der minimale RecvListenMOS für den Anruf.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Flag, das angibt, ob der Audio-FEC für den Anruf verwendet wurde.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|**Eingehende Nachrichten** <br/> |bit  <br/> | <br/> |Daten auf Empfängerseite werden empfangen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> | <br/> |Streamdaten auf Absenderseite werden empfangen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 bedeutet, dass die Datenstromrichtung vom Anrufer zum Ankrufe liegt.  <br/> 0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
|**JitterInterArrivalSD** <br/> |Gleitkommazahl  <br/> ||Standardabweichung für jitterantreffende Zeiten.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioMax** <br/> |Gleitkommazahl  <br/> ||Maximales Verhältnis von Paketen, die von der Healer ausgeblendet werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ConcealRatioSD** <br/> |Gleitkommazahl  <br/> ||Standardabweichung für das Verhältnis von Paketen, die von der Wieer ausgeblendet werden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerPacketDropRatio** <br/> |Gleitkommazahl  <br/> ||Das Verhältnis der pakete, die von der Healer abgelegt wurden, im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |Gleitkommazahl  <br/> ||Das Verhältnis der verwendeten Pakete zur Vorwärtsfehlerkorrektur im Vergleich zur Gesamtzahl der empfangenen Pakete.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MaxCompressedSamples** <br/> |Gleitkommazahl  <br/> ||Maximale Anzahl von Audiopaketen, die von der Wiege komprimiert wurden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LossCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Verlustüberlastungszustand aufting.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DelayCongestionPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verzögerte Eintreffen von Netzwerkpaketen verursacht wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ContentionDetectedPercent** <br/> |Gleitkommazahl  <br/> ||Gibt den Prozentsatz der Zeit an, zu der der Anruf um Netzwerkressourcen konkurriert hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Minimale Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Maximale Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Standardabweichung der Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Durchschnittliche Bandbreitenschätzung, die während des Anrufs gemessen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayTotal** <br/> |Gleitkommazahl  <br/> ||Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Undirektionale Burstvorkommen insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdichte insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdauer insgesamt. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamtanzahl der vorkommenden one-way-Lücken. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDensity** <br/> |Gleitkommazahl  <br/> ||Gesamtdichte für die einweg-lücke. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayGapDuration** <br/> |Gleitkommazahl  <br/> ||Gesamtdauer der ein- und auswegsen Lücken. Bei einer Übertragung mit Bursts handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Datenströmen und nicht in einem stabilen Datenstrom übertragen werden. Lücken weisen auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DecodeStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des als Stereo decodierten Anrufs.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecRenderStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der vom Echounterdungssignal als Stereo wiedergegeben wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AudioPostFECPLR** <br/> |Gleitkommazahl  <br/> ||Paketverlustrate nach Anwendung der Vorwärtsfehlerkorrektur.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**EncodeStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des als Stereo codierten Anrufs.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**AecCaptureStereoPercent** <br/> |Gleitkommazahl  <br/> ||Prozentsatz des Anrufs, der vom Echounterdungssignal als Stereo aufgezeichnet wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
