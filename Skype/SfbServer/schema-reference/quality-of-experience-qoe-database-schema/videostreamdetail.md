---
title: VideoStreamDetail-Ansicht
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
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: In der VideoStreamDetail-Ansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 465684ed4cfc857ede340d960f82d8be13031808
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609092"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail-Ansicht
 
In der VideoStreamDetail-Ansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|
|SessionTime  <br/> |Datum/Uhrzeit  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|StreamId  <br/> |int  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|StartTime  <br/> |Datum/Uhrzeit  <br/> |Startzeitpunkt der Sitzung.  <br/> |
|EndTime  <br/> |Datum/Uhrzeit  <br/> |Endzeitpunkt der Sitzung.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des Anruferpools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des Angerufenenpools.  <br/> |
|Anrufer  <br/> |nvarchar(450)  <br/> |Der URI des Aufrufers.  <br/> |
|Aufgerufenen  <br/> |nvarchar(450)  <br/> |Der URI des Angerufenen.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Aufrufers.  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |Typ des Benutzer-Agenten des Anrufers. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzer-Agenten des Anrufers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Angerufenen.  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |Typ des Benutzer-Agenten des Angerufenen. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Kategorie des Benutzer-Agenten des Angerufenen. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE).](useragentdef-qoe.md) <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des Angerufenen.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Betriebssystem des Endpunkts des Aufrufers.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Betriebssystem des Endpunkts des Angerufenen.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |CPU-Name des Endpunkts des Anrufers.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |CPU-Name des Endpunkts des Angerufenen.  <br/> |
|CallerCPUNumberOfCores  <br/> |Smallint  <br/> |Anzahl der CPU-Kerne des Endpunkts des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |Smallint  <br/> |Anzahl der CPU-Kerne des Endpunkts des Angerufenen.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des Angerufenen.  <br/> |
|CallerVirtualizationFlag  <br/> |Tinyint  <br/> |Gibt an, ob das System des Aufrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkttabelle.](endpoint.md) <br/> |
|CalleeVirtualizationFlag  <br/> |Tinyint  <br/> |Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkttabelle.](endpoint.md) <br/> |
|ConnectivityIce  <br/> |Tinyint  <br/> |Informationen zum Medienpfad, z. B. direkt oder Relay. Weitere Informationen finden Sie in der [MediaLine-Tabelle.](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|Transport  <br/> |int  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |Bit  <br/> |Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom Angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |Bit  <br/> |Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Angerufenen.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region der Website des Angerufenen.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port auf dem vom Anrufer verwendeten A/V-Edgedienst.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Der Name des Rendergeräts des Aufrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Der Treibername des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Der Name des Rendergerättreibers des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Angerufenen.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Der Name des Rendergeräts des Angerufenen.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Der Treibername des Aufnahmegeräts des Angerufenen.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Der Name des Rendergerättreibers des Angerufenen.  <br/> |
|CallerNetworkConnectionType  <br/> |Tinyint  <br/> |Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 drahtlos.  <br/> |
|CallerVPN  <br/> |Bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |Tinyint  <br/> |Netzwerkverbindungstyp des Angerufenen: 0 ist verkabelt, 1 drahtlos.  <br/> |
|CalleeVPN  <br/> |Bit  <br/> |Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Angerufenen (in Basispunkten).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler Netzwerkjitter während des Anrufs.  <br/> |
|Roundtrip  <br/> |int  <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketwert für den Videostream (Real Time Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Bandbreitenschätzungen für den Audiostream.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Für den Anruf verwendeter Audiocodec, auf den in der [PayloadDescription-Tabelle](payloaddescription.md)verwiesen wird.  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Empfangene Framerate des Videostreams.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Gesendete Framerate des Videostreams.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Maximale Videobitrate während der Videositzung.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Videpaketverlustrate.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.  <br/> |
|VideoFEC  <br/> |Bit  <br/> |Nicht verwendet.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Durchschnittliche für Video reservierte Bandbreite.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.  <br/> |
|SenderIsCallerPAI  <br/> |Bit  <br/> |Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.  <br/> |
   

