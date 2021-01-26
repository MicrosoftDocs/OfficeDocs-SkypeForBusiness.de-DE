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
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: In der VideoStreamDetail-Ansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6341febeb8d43e36975c5b4cc446ac24ff1287c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834345"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail-Ansicht
 
In der VideoStreamDetailansicht werden Informationen zu jedem Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|
|SessionTime  <br/> |Datum/Uhrzeit  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|StreamId  <br/> |int  <br/> |Eindeutige ID innerhalb einer Medienzeile.  <br/> |
|StartTime  <br/> |Datum/Uhrzeit  <br/> |Startzeitpunkt der Sitzung.  <br/> |
|EndTime  <br/> |Datum/Uhrzeit  <br/> |Endzeitpunkt der Sitzung.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des Anruferpools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des Angerufenenpools.  <br/> |
|Anrufer  <br/> |nvarchar(450)  <br/> |URI des Anrufers.  <br/> |
|Ankrufer  <br/> |nvarchar(450)  <br/> |URI des Ankrufers.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agents des Anrufers. Weitere Informationen finden [Sie in der Tabelle "UserAgent".](useragent.md) <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der Prozessorkerne des Endpunkts des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der Prozessorkerne des Endpunkts des Ankrufers.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Prozessorgeschwindigkeit der CPU des Endpunkts des Ankrufers.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Aufrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen [finden Sie in der Endpunkttabelle.](endpoint.md) <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen [finden Sie in der Endpunkttabelle.](endpoint.md) <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zum Medienpfad, z. B. direkt oder Relay. Weitere Informationen [finden Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|Transport  <br/> |int  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom Angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Name der Website des Ankrufers.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Name des Landes/der Region des Standorts des Ankrufers.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port auf dem vom Anrufer verwendeten A/V-Edgedienst.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Name des Rendergeräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Name des Aufnahmegerättreibers des Anrufers.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Name des Rendergerätetreibers des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Ankrufers.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Name des Rendergeräts des Ankrufers.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Name des Aufnahmegerättreibers des Ankrufers.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Name des Rendergerätetreibers des Ankrufers.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 drahtlos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Ankrufers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Ankrufers (in Bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler Netzwerkjitter während des Anrufs.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtripzeit aus RTCP-Statistik.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtripzeit für den Audiostream.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Maximale Paketverlustrate während des Anrufs.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketwert für den Videostream (Real Time Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Bandbreitenschätzungen für den Audiostream.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Für den Anruf verwendeter Audiocodec, auf den in der [PayloadDescription -Tabelle verwiesen wird.](payloaddescription.md)  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Durchschnittliche Bitrate des Videostreams.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Empfangene Framerate des Videostreams.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Gesendete Framerate des Videostreams.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Maximale Videobitrate während der Videositzung.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Videpaketverlustrate.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Nicht verwendet.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Durchschnittliche für Video reservierte Bandbreite.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.  <br/> |
   

