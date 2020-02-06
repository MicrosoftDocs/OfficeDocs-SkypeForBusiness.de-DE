---
title: AudioStreamDetail-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: In der AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 14815a107654fc83fc2b71c5070b82617154677c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810873"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail-Ansicht
 
In der AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|SessionSeq  <br/> |int  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|Datenstrom-Nr  <br/> |int  <br/> |Eindeutige ID innerhalb einer medienzeile  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit der Sitzung.  <br/> |
|EndTime  <br/> |datetime  <br/> |Endzeit der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialog Feld Kategorie: 0 ist der Skype for Business Server für Mediation Server Leg; 1 ist der Vermittlungs Server für das PSTN-Gateway-Bein.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Wenn vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs zugeordnet wurden. Es wird nur ein Wert definiert:  <br/> 0x0001-unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.  <br/> |
|CallPriority  <br/> |int  <br/> |Die Priorität des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des anrufenden Pools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des aufgerufenen Pools.  <br/> |
|Anrufer  <br/> |nvarchar (450)  <br/> |URI des Anrufers.  <br/> |
|Callee  <br/> |nvarchar (450)  <br/> |URI des aufgerufenen.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Kategorie des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Benutzers.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents des anrufempfängers. Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Kategorie des Benutzer-Agents des berufenen Informationen finden Sie in der [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) . <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Der Endpunktname des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des angerufenen  <br/> |
|Anrufer  <br/> |nvarchar (128)  <br/> |Betriebssystem (OS) des Endpunkts des Anrufers.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Betriebssystem (OS) des Endpunkts des aufgerufenen.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Der CPU-Name des Endpunkts des Anrufers.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Der CPU-Name des Endpunkts des aufgerufenen.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der CPU-Kerne im Endpunkt des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der CPU-Kerne im Endpunkt des aufgerufenen.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkt Tabelle](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkt Tabelle](endpoint.md) . <br/> |
|CorrelationKey  <br/> ||Korrelationsschlüssel Wird in der [SessionCorrelation-Tabelle](sessioncorrelation.md)referenziert.  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zum Medienpfad, beispielsweise direkt oder weitergeleitet. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|Transport  <br/> |tinyint  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des Anrufers. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.  <br/> |
|CallerPort  <br/> |int  <br/> |Der vom Aufrufer verwendete Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob sich der Aufrufer innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des aufgerufenen. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.  <br/> |
|CalleePort  <br/> |int  <br/> |Port, der vom aufgerufenen verwendet wird.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob sich der aufgerufene innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Der Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Name des Landes/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Name der Website des aufgerufenen.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Name des Landes/der Region der Website des berufenen.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräte Treibers des Anrufers.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |Name des Render-Gerätetreibers des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Der Name des Erfassungsgeräts des Anrufers.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Der Name des Capture-Gerätetreibers des anrufempfängers.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Der Name des Render-Gerätetreibers des Benutzers.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal (18; 0)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal (18; 0)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen in BPS.  <br/> |
|ConversationalMOS  <br/> |Dezimal (3; 2)  <br/> |Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.). Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler Netzwerk Jitter während des Anrufs.  <br/> |
|PacketLossRate  <br/> |Dezimal (5; 4)  <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |Dezimal (5; 4)  <br/> |Maximaler Paketverlust während des Anrufs.  <br/> |
|BurstDensity  <br/> |Dezimal (9; 4)  <br/> |Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.  <br/> |
|BurstGapDensity  <br/> |Dezimal (9; 4)  <br/> |Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Die Anzahl der Pakete für den Audiostream.  <br/> |
|Bandbreite  <br/> |int  <br/> |Bandbreiten Schätzungen für den Audiostream.  <br/> |
|DegradationAvg  <br/> |Dezimal (3; 2)  <br/> |Netzwerk-Mos-Verschlechterung für den gesamten Anruf. Der Bereich ist 0,0 bis 5,0. Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde. Für akzeptable Qualität sollte es weniger als 0,5.  <br/> |
|DegradationMax  <br/> |Dezimal (3; 2)  <br/> |Maximaler Netzwerk-Mos-Abbau während des Anrufs.  <br/> |
|DegradationJitterAvg  <br/> |Dezimal (3; 2)  <br/> |Netzwerk-Mos-Beeinträchtigung durch Jitter.  <br/> |
|DegradationPacketLossAvg  <br/> |Dezimal (3; 2)  <br/> |Netzwerk-Mos-Beeinträchtigung durch Paketverlust.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Der für den Anruf verwendete Audiocodec, auf den in der [PayloadDescription-Tabelle](payloaddescription.md)verwiesen wird.  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Abtastrate für den Audiostream.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Analoger Gain-Regler für Audio-Signalpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Audio-Signalpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Verbesserung der Echo-Rückerstattung für den Anrufer. Die Einheit für diese Metrik ist DB. Niedrigere Werte stellen weniger Echo dar. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe des Anrufers. Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers. Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|CallerTimestampDriftRateMic  <br/> |Dezimal (9; 2)  <br/> |Clock-Drift Rate des Anrufers im Verhältnis zur CPU-Uhr.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |Dezimal (9; 2)  <br/> |Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.  <br/> |
|CallerTimestampErrorMicMs  <br/> |Dezimal (9; 2)  <br/> |Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |Dezimal (9; 2)  <br/> |Der Durchschnitt des Sprechers des Sprechers Render-Datenstrom Zeitstempel-Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Ursachen für ein Echo Ereignis für den Aufrufer. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CallerEchoPercentMicIn  <br/> |Dezimal (5; 2)  <br/> |Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des Anrufers erkannt wird. Wenn Headset verwendet wird, sollte der Wert gering sein.  <br/> |
|CallerEchoPercentSend  <br/> |Dezimal (5; 2)  <br/> |Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des Anrufers erkannt wird. Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers; Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich-30 bis-18 dBoV sein.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers. Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf das Audiosignal des Anrufers angewendet wurde.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Stellt die analogen Gain-Regler-Audiosignale für das Audiosignal dar, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Audiosignal Pegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Post-Analog-Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Verbesserung der Echo-Rückerstattung für den aufgerufenen. Die Einheit für diese Metrik ist DB. Niedrigere Werte stellen weniger Echo dar. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Störgeräusche pro fünf Minuten für die Lautsprecher-Darstellung des anrufenden. Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers. Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |Dezimal (9; 2)  <br/> |Abdriftrate des Mikrofon Geräts des Anrufers, relativ zu CPU-Takt.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |Dezimal (9; 2)  <br/> |Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |Dezimal (9; 2)  <br/> |Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |Dezimal (9; 2)  <br/> |Der Durchschnitt des Sprechers des Speaker-Render-Datenstrom Zeitstempels in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Ursachen für ein Echo Ereignis für den aufgerufenen. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CalleeEchoPercentMicIn  <br/> |Dezimal (5; 2)  <br/> |Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des berufenen erkannt wird. Wenn Headset verwendet wird, sollte der Wert gering sein.  <br/> |
|CalleeEchoPercentSend  <br/> |Dezimal (5; 2)  <br/> |Der Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des aufgerufenen erkannt wird. Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen; Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen. Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf die Audiofunktion des berufenen angewendet wurde.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|RatioConcealedSamplesAvg  <br/> |Dezimal (5; 2)  <br/> |Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.  <br/> |
|RatioStretchedSamplesAvg  <br/> |Dezimal (5; 2)  <br/> |Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.  <br/> |
|RatioCompressedSamplesAvg  <br/> |Dezimal (5; 2)  <br/> |Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtrip-Zeit von RTCP-Statistiken  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtrip-Zeit für den Audiostream.  <br/> |
|OverallAvgNetworkMOS  <br/> |Dezimal (3; 2)  <br/> |Durchschnittliche Breitband-Netzwerk-Mos für den Anruf. Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab. Der Bereich ist 1,0 bis 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |Dezimal (3; 2)  <br/> |Minimale Breitband-Netzwerk-Mos für den Anruf.  <br/> |
|SendListenMOS  <br/> |Dezimal (3; 2)  <br/> |Durchschnittliche vorhergesagte Breitband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachniveau, Geräuschpegel und Aufnahmegeräte Eigenschaften.  <br/> |
|SendListenMOSMin  <br/> |Dezimal (3; 2)  <br/> |Minimale SendListenMOS für den Anruf.  <br/> |
|RecvListenMOS  <br/> |Dezimal (3; 2)  <br/> |Durchschnittlicher prognostizierter breitbandiger Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.  <br/> |
|RecvListenMOSMin  <br/> |Dezimal (3; 2)  <br/> |Minimale RecvListenMOS für den Anruf.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Gibt an, ob Audio FEC für den Anruf verwendet wurde.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Gibt die Richtung der p-Assert-identifizier Informationen an; 1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.  <br/> |
   

