---
title: AudioStreamDetail-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 770ccad50a6f48aa41e4ba2f105d1fc0d4879d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920054"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail-Ansicht
 
AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Eindeutige ID innerhalb einer medienzeile.  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit der Sitzung.  <br/> |
|EndTime  <br/> |datetime  <br/> |Die Endzeit der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialogfeld Kategorie: 0 ist die Skype für Business Server Mediation Server Abschnitts; 1 wird vom Vermittlungsserver zum PSTN-Gateway-Abschnitt.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Flag gibt an, ob der Anruf oder nicht umgangen wurde.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehung IDs übereinstimmen. Es wird nur ein Wert definiert:  <br/> 0 x 0001 – unbekannte umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Anrufer-Pool FQDN.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des angerufenenpools.  <br/> |
|Anrufer  <br/> |nvarchar(450)  <br/> |URI des Anrufers.  <br/> |
|Callee  <br/> |nvarchar(450)  <br/> |URI des angerufenen.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragentzeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agent des Anrufers. [UserAgent-Tabelle](useragent.md) Details finden Sie. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzer-Agent des Anrufers. [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) ausführliche Informationen finden Sie. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragentzeichenfolge des angerufenen.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agent des angerufenen. Siehe [UserAgent-Tabelle](useragent.md) Informationen. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzer-Agent des angerufenen. Siehe die [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) Informationen. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des angerufenen.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des angerufenen.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Betriebssystem (OS) des Endpunkts des Anrufers.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Betriebssystem (OS) des Endpunkts des angerufenen.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Prozessorname des Endpunkts des Anrufers.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Prozessorname des Endpunkts des angerufenen.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Anzahl der Prozessorkerne des Endpunkts des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Anzahl der Prozessorkerne des Endpunkts des angerufenen.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit des Endpunkts des angerufenen.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob der Anrufer System in einer virtualisierten Umgebung ausgeführt wird. Finden Sie weitere Informationen der [Endpoint-Tabelle](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob des angerufenen System in einer virtualisierten Umgebung ausgeführt wird. Finden Sie weitere Informationen der [Endpoint-Tabelle](endpoint.md) . <br/> |
|CorrelationKey  <br/> ||Korrelations-Taste. Verweis von der [SessionCorrelation-Tabelle](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zu den Medienpfad wie direkte oder weitergeleitet. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für den Anrufer. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für des angerufenen. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|Transport  <br/> |tinyint  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob der Anrufer innerhalb des intervallnetzwerks befindet: 1 bedeutet, dass Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer außerhalb des Netzwerks.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob die aufgerufene innerhalb des intervallnetzwerks befindet: 1 bedeutet, dass angerufenen ist innerhalb des Unternehmensnetzwerks, 0 bedeutet, dass der aufgerufene außerhalb des Netzwerks.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Name des Lands/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des angerufenen.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Name des Lands/der Region der Website des angerufenen.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des A / V-edgedienst vom Anrufer verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port verwendet, auf dem A / V-edgedienst vom Anrufer verwendeten.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Key der IP-Adresse des A / V-edgedienst vom angerufenen verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port verwendet, auf dem A / V-edgedienst vom angerufenen verwendeten.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)-Wert  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des Anrufers Gerät Treiber.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)-Wert  <br/> |Name des Aufnahmegeräts des angerufenen.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des angerufenen.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des angerufenen Gerät Treiber.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des angerufenen.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden: 1 = virtuelles privates Netzwerk (VPN), 0 = nicht-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Typ der Netzwerkverbindung des angerufenen: 0 ist verkabelt, 1 ist kabellos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden: 1 = virtuelles privates Netzwerk (VPN), 0 = nicht-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkübertragungsrate für den Endpunkt des angerufenen in Bit/s.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite in den angegebenen senden Seite Stream angegebenen verschiedene Einstellungen für die Informationsverwaltungsrichtlinie (aktivieren, API, SDP, Policy Server usw.) angewendet. Dies ist nicht für die effektive Bandbreite verwechselt werden, da ein niedriger Bandbreite basierend auf die Schätzung für das Bandbreite kann. Dies ist im Wesentlichen die maximale Bandbreite, die der Stream senden läuft Grenzwerte, die auf die Schätzung für das Bandbreite durchführen können  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher netzwerkjitter aus Statistik (Real Time Control Protocol, RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler netzwerkjitter während des Anrufs.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Durchschnittliche paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Maximale paketverlustrate während des Anrufs.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketwert für den Audiostream.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Bandbreitenschätzwerte für den Audiostream.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Werte sind 0,0, 5.0 ist. Diese Metrik zeigt die Dauer, dass die Netzwerk-MOS aufgrund von Jitter und Paketverlust reduziert wurde. Für eine akzeptable Qualität sollte es weniger als 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Für den Anruf wird aus der [PayloadDescription-Tabelle](payloaddescription.md)verwendete Audiocodec.  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Samplingrate für den Audiostream.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Nach dem analoge erhalten Sie die Kontrolle Audiosignal-Ebene für die Audiodaten gesendet, der Anrufer. Die Einheit dieser Metrik ist dBmo. Für eine akzeptable Qualität sollte mindestens 30 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Audiosignal-Ebene für die Audiodaten der Anrufer empfangen. Die Einheit dieser Metrik ist dBmo. Für eine akzeptable Qualität sollte mindestens 30 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nach dem analoge erhalten Sie die Kontrolle audio Rauschen für Audio den Anrufer gesendet. Die Einheit dieser Metrik ist dBmo. Akzeptable Qualität sollten sie weniger als 35 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nach dem analoge erhalten Sie die Kontrolle audio Rauschen für Audio der Anrufer empfangen. Die Einheit dieser Metrik ist dBmo. Akzeptable Qualität sollten sie weniger als 35 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Echo zurückgeben Verlust Erweiterung für Anrufer. Die Einheit dieser Metrik ist dB. Niedrigere Werte darstellen weniger Echo. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Probleme pro fünf Minuten des Anrufers Audiosignalen rendern. Für die Qualität sollte dies weniger als eine pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Probleme pro fünf Minuten für Mikrofon des Anrufers erfassen. Für guter Qualität sollte dies weniger als einer pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Des Anrufers Uhr driftrate Mikrofons, relativ zum CPU-Takt.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Des Anrufers Uhr driftrate Lautsprechers, relativ zum CPU-Takt.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durchschnittliche Mikrofon Capture Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Mittelwert der Lautsprecher des Anrufers Rendern Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |VoIP-Switch ist eine Halbduplexmodus reduzierte Unterbrechung Möglichkeit. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Ursachen für echoereignis für den Anrufer. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, wenn in der Aufrufer Mikrofon Capture Stream Echo erkannt wird. Wenn Kopfhörer verwendet wird, sollte der Wert niedriger sein.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, wenn Echo, in dem Anrufer erkannt wird, des Stream-Objekt gesendet. Hohe Echo Prozentsatz im senden Datenströme Angabe des Echo Speicherverlusten.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Audiosignals auf dem Vermittlungsserver vom Gateway für das Audio des Anrufers; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität sollte des Gültigkeitsbereichs-18 dBoV -30 sein.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Empfangene Audiosignals auf dem Vermittlungsserver vom Gateway für den Anrufer Audiosignal des. Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität sollte der zulässigen Bereich weniger als-50 dBoV sein.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Eingebauter Verstärker (AGC) auf der vermittlungsserverseite angewendet auf das Audio des Anrufers.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Quadratischer Mittelwert (RMS) des eingehenden Signals an den Anrufer in den ersten 30 Sekunden des Anrufs.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Stellt die nach der Analog zu erhalten Audiosignal Steuerungsebene für das Audio des angerufenen gesendet. Die Einheit dieser Metrik ist dBmo. Für eine akzeptable Qualität sollte mindestens 30 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Audiosignal-Ebene für Audio des angerufenen empfangen. Die Einheit dieser Metrik ist dBmo. Für eine akzeptable Qualität sollte mindestens 30 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nach dem analoge erhalten Sie die Kontrolle audio Rauschen für Audio des angerufenen gesendet. Die Einheit dieser Metrik ist dBmo. Akzeptable Qualität sollten sie weniger als 35 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nach dem analoge erhalten Sie die Kontrolle audio Rauschen für Audio des angerufenen empfangen. Die Einheit dieser Metrik ist dBmo. Akzeptable Qualität sollten sie weniger als 35 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Echo zurückgeben Verlust für Verbesserung des angerufenen. Die Einheit dieser Metrik ist dB. Niedrigere Werte darstellen weniger Echo. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Durchschnittliche Probleme pro fünf Minuten des angerufenen Audiosignalen rendern. Für die Qualität sollte dies weniger als eine pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Durchschnittliche Probleme pro fünf Minuten für Mikrofon des angerufenen erfassen. Für guter Qualität sollte dies weniger als einer pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Angerufenen Uhr driftrate Mikrofons, relativ zum CPU-Takt.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Angerufenen Uhr driftrate Lautsprechers, relativ zum CPU-Takt.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durchschnittliche Mikrofon Capture Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Mittelwert der Lautsprecher des angerufenen Rendern Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |VoIP-Switch ist eine Halbduplexmodus reduzierte Unterbrechung Möglichkeit. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Ursachen für echoereignis für des angerufenen. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, wenn Echo in des angerufenen Mikrofon Capture Stream erkannt wird. Wenn Kopfhörer verwendet wird, sollte der Wert niedriger sein.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Prozentsatz der Zeit, wenn Echo in angerufenen erkannt wird, der Stream gesendet. Hohe Echo Prozentsatz im senden Datenströme Angabe des Echo Speicherverlusten.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Empfangene Audiosignals auf dem Vermittlungsserver vom Gateway für das Audio des angerufenen; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität des Gültigkeitsbereichs [-30,-18] werden sollte dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Empfangene Audiosignals auf dem Vermittlungsserver vom Gateway für die aufgerufenen Audiosignal des. Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität sollte der zulässigen Bereich weniger als-50 dBoV sein.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Eingebauter Verstärker (AGC) auf der vermittlungsserverseite angewendet auf das Audio des angerufenen.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Quadratischer Mittelwert (RMS) des eingehenden Signals an den angerufenen in den ersten 30 Sekunden des Anrufs.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch audioreparatur, und standardsamples.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Durchschnittliche Breitband-Netzwerk-MOS für den Anruf. Dieser Metrik hängt davon ab, die Paketverluste, Jitter und verwendeten Codecs. Werte sind 1.0 auf 5.0 ist.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Minimaler Breitband-Netzwerk-MOS für den Anruf.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendete Audios, einschließlich sprachpegel, Rauschen und aufnahmegerätmerkmale.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |Minimaler SendListenMOS für den Anruf.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Durchschnittlicher vorhergesagter Breitband-Hör-MOS für Audio empfangen aus dem Netzwerk, einschließlich sprachpegel, Rauschen, Codec, netzwerkbedingungen und aufnahmegerätmerkmale.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |Minimaler RecvListenMOS für den Anruf.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Gibt an, ob audio-FEC für den Anruf verwendet wurde.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Gibt die Richtung der p-asserted-identify-Information; 1 bedeutet, dass die streamrichtung vom Anrufer zum angerufenen verläuft; 0 bedeutet, dass die streamrichtung vom angerufenen zum Anrufer verläuft.  <br/> |
   

