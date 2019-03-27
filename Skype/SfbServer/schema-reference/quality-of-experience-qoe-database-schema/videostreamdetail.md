---
title: VideoStreamDetail-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail-Ansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6bafdbed3152bc73b2988e31877d8b7203557d46
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884435"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail-Ansicht
 
VideoStreamDetail-Ansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Eindeutige ID innerhalb einer medienzeile.  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit der Sitzung.  <br/> |
|EndTime  <br/> |datetime  <br/> |Die Endzeit der Sitzung.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Anzahl der CPU-Kerne des Endpunkts des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Anzahl der CPU-Kerne des Endpunkts des angerufenen.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit des Endpunkts des angerufenen.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob der Anrufer System in einer virtualisierten Umgebung ausgeführt wird. Finden Sie weitere Informationen der [Endpoint-Tabelle](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob des angerufenen System in einer virtualisierten Umgebung ausgeführt wird. Finden Sie weitere Informationen der [Endpoint-Tabelle](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zu Medienpfad, wie direkte oder weitergeleitet. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für den Anrufer. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für des angerufenen. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|Transport  <br/> |int  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob der Anrufer innerhalb des Netzwerks der Organisation ist. 1 bedeutet, dass Anrufer innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob der Anrufer innerhalb ist der Organisation network.1 bedeutet, dass angerufenen innerhalb des Unternehmensnetzwerks, 0 bedeutet, dass der aufgerufene außerhalb des Netzwerks ist.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Name des Lands/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des angerufenen.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Name des Lands/der Region der Website des angerufenen.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des A / V-edgedienst vom Anrufer verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port auf dem A / V-edgedienst vom Anrufer verwendeten.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Key der IP-Adresse des A / V-edgedienst vom angerufenen verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port auf dem A / V-edgedienst vom angerufenen verwendeten.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)-Wert  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des Anrufers Gerät Treiber.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)-Wert  <br/> |Name des Aufnahmegeräts des angerufenen.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des angerufenen.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des angerufenen Gerät Treiber.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des angerufenen.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Typ der Netzwerkverbindung des angerufenen: 0 ist verkabelt, 1 ist kabellos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkübertragungsrate für den Endpunkt des angerufenen (in Bit/s).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite in den angegebenen senden Seite Stream angegebenen verschiedene Einstellungen für die Informationsverwaltungsrichtlinie (aktivieren, API, SDP, Policy Server usw.) angewendet. Dies ist nicht für die effektive Bandbreite verwechselt werden, da ein niedriger Bandbreite basierend auf die Schätzung für das Bandbreite kann. Dies ist im Wesentlichen die maximale Bandbreite, die der Stream senden läuft Grenzwerte, die auf die Schätzung für das Bandbreite durchführen kann.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher netzwerkjitter aus Statistik (Real Time Control Protocol, RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler netzwerkjitter während des Anrufs.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Durchschnittliche paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Maximale paketverlustrate während des Anrufs.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketwert für den Videostream (Real-Time Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Bandbreitenschätzwerte für den Audiostream.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Audiocodec für den Anruf wird aus der [PayloadDescription-Tabelle](payloaddescription.md)verwendet.  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Auflösung des Videos in Pixel Breite, Höhe multipliziert. Gemeldet als Zeichenfolge.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Der Framerate des Videostreams empfangen.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Der Framerate des Videostreams gesendet.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Maximale Videobitrate während der videositzung.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Rate, bei der Videopakete verlorengingen.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Prozentsatz der gesamten Videoframes, die verloren gegangen sind.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Nicht verwendet.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Durchschnittliche reservierte Bandbreite für Video.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Prozentsatz der gesamten Videoframes, die verloren gingen.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Streamrichtung p-asserted-Identity-Informationen. 1 bedeutet, dass die streamrichtung vom Anrufer zum angerufenen verläuft; 0 bedeutet, dass die streamrichtung vom angerufenen zum Anrufer verläuft.  <br/> |
   

