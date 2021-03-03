---
title: Ansicht "AudioStreamDetail"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: Die AudioStreamDetail-Ansicht speichert Informationen über jeden Audiostream in der Datenbank. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 4a675f2b7a8cf4e0aaa322bb63d804edf27625cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823095"
---
# <a name="audiostreamdetail-view"></a>Ansicht "AudioStreamDetail"
 
Die AudioStreamDetail-Ansicht speichert Informationen über jeden Audiostream in der Datenbank. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|SessionTime  <br/> |Datum/Uhrzeit  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|StreamId  <br/> |int  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|StartTime  <br/> |Datum/Uhrzeit  <br/> |Startzeitpunkt der Sitzung.  <br/> |
|EndTime  <br/> |Datum/Uhrzeit  <br/> |Endzeit der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialogfeldkategorie: 0 ist die Skype for Business Server-zu-Vermittlungsserver-Leg; 1 ist die Vermittlungsserver-zu-PSTN-Gateway-Leg.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Gibt an (falls vorhanden), warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmten. Es ist nur ein Wert definiert:  <br/> 0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des Anruferpools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des Angerufenenpools.  <br/> |
|Anrufer  <br/> |nvarchar(450)  <br/> |URI des Anrufers.  <br/> |
|Ankrufer  <br/> |nvarchar(450)  <br/> |URI des Ankrufers.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Typ des Benutzeragenten des Anrufers. Weitere Informationen finden [Sie in der Tabelle "UserAgent".](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzeragenten des Anrufers. Weitere Informationen [finden Sie in der Tabelle "UserAgentDef" (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Ankrufers.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Typ des Benutzeragenten des Ankrufers. Weitere Informationen finden [Sie in der Tabelle "UserAgent".](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzeragenten des Ankrufers. Weitere Informationen [finden Sie in der Tabelle "UserAgentDef" (QoE).](useragentdef-qoe.md) <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Name des Endpunkts des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Name des Endpunkts des Ankrufers.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Betriebssystem des Endpunkts des Anrufers.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Betriebssystem des Endpunkts des Ankrufers.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Der CPU-Name des Endpunkts des Anrufers.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Der CPU-Name des Endpunkts des Ankrufers.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der CPU-Kerne im Endpunkt des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der CPU-Kerne im Endpunkt des Ankrufers.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit der CPU des Endpunkts des Ankrufers.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Aufrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen [finden Sie in der Endpunkttabelle.](endpoint.md) <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen [finden Sie in der Endpunkttabelle.](endpoint.md) <br/> |
|CorrelationKey  <br/> ||Korrelationsschlüssel. Referenziert aus der [SessionCorrelation-Tabelle.](sessioncorrelation.md)  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zum Medienpfad, z. B. direkt oder Relay. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|Transport  <br/> |tinyint  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob sich der Anrufer innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom Angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob sich der Angerufene innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Angerufene sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Angerufene außerhalb des Netzwerks befindet.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Ankrufers.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region des Standorts des Ankrufers.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Der durch den A/V-Edgedienst des Anrufers verwendete Port.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Der durch den A/V-Edgedienst des Angerufenen verwendete Port.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Name des Rendergeräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Name des Aufnahmegerättreibers des Anrufers.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Name des Rendergerätetreibers des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Ankrufers.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Name des Rendergeräts des Ankrufers.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Name des Aufnahmegerättreibers des Ankrufers.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Name des Rendergerätetreibers des Ankrufers.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 drahtlos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Ankrufers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler Netzwerkjitter während des Anrufs.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketwert für den Audiostream.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Bandbreitenschätzwerte für den Audiostream.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Der für den Anruf verwendete Audiocodec, auf den in der [PayloadDescription -Tabelle verwiesen wird.](payloaddescription.md)  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Samplingrate für den Audiostream.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Stärke des Audiosignals der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Stärke des Audiosignals für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Stärke des Audiogeräusches der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Echodämpfungsverbesserung für den Anrufer. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Störungen pro fünf Minuten für das Lautsprecherrendering des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Störungen pro fünf Minuten für die Mikrofonerfassung des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Driftrate des Mikrofons des Anrufers, relativ zur CPU-Uhr.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Driftrate des Lautsprechergeräts des Anrufers, relativ zur CPU-Uhr.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Durchschnittlicher Zeitstempelfehler des Lautsprechers des Anrufers in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Ursachen von Echoereignissen für den Anrufer. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, in der echo im Aufnahmedatenstrom des Mikrofons des Anrufers erkannt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, in der echo im gesendeten Datenstrom des Anrufers erkannt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway für das Audio des Anrufers; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Signalstufe auf dem Vermittlungsserver vom Gateway für das Audio des Anrufers empfangen. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Die automatische Verstärkungssteuerung (AUTOMATIC Gain Control, AGC) auf der Vermittlungsserverseite wurde auf das Audio des Anrufers angewendet.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |Gleitkommazahl  <br/> |RMS (Effektivwert) des eingehenden Signals an den Anrufer in den ersten 30 Sekunden des Anrufs.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Stellt die Stärke des Audiosignals der postanalogen Verstärkung für das vom Angerufenen gesendete Audio dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Stärke des Audiosignals für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Echodämpfungsverbesserung für den Angerufenen. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Störungen pro fünf Minuten für das Lautsprecherrendering des Ansprechers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Störungen pro fünf Minuten für die Mikrofonaufnahme des Ansprechers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Driftrate des Mikrofons des Ansprechgeräts, relativ zum CPU-Takt.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Driftrate des Lautsprechergeräts des Ansprechers, relativ zur CPU-Uhr.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Durchschnittlicher Zeitstempelfehler des Lautsprechers des Ansprechers in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Ursachen von Echoereignissen für den Angerufenen. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, in der echo im Aufnahmedatenstrom des Mikrofons des Ansprechers erkannt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, in der echo im gesendeten Datenstrom des Ankrufers erkannt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway für das Audio des Ankrufers; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway für das Audio des Ankrufers. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Automatische Verstärkungssteuerung (Automatic Gain Control, AGC) auf der Vermittlungsserverseite, die auf die Audiodaten des Ankrufers angewendet wird.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |Gleitkommazahl  <br/> |RMS (Effektivwert) des eingehenden Signals an den Angerufenen in den ersten 30 Sekunden des Anrufs.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich umfasst [1,0 bis 5,0].  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Minimaler Breitband-Netzwerk-MOS für den Anruf.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendetes Audio, einschließlich Sprachpegel, Rauschen und Aufnahmegerätmerkmale.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |Minimaler SendListenMOS für den Anruf.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Durchschnittlicher vorhergesagter Breitband-Hör-MOS für empfangenes Audio aus dem Netzwerk, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Aufnahmegerätmerkmale.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |Minimaler RecvListenMOS für den Anruf.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Gibt an, ob Audio-FEC für den Anruf verwendet wurde.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Gibt die Richtung der P-Asserted-Identify-Information an; 1 bedeutet, dass die Streamrichtung vom Anrufer zum Angerufenen verläuft; 0 bedeutet, dass die Streamrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
   

