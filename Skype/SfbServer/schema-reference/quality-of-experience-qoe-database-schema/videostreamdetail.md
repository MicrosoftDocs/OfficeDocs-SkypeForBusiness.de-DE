---
title: VideoStreamDetail-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videodatenströmen in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: ee342de919ffca8b62c60f8c7b724f3dc7be0205
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294530"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail-Ansicht
 
In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videodatenströmen in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|SessionSeq  <br/> |int  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|Datenstrom-Nr  <br/> |int  <br/> |Eindeutige ID innerhalb einer medienzeile  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit der Sitzung.  <br/> |
|EndTime  <br/> |datetime  <br/> |Endzeit der Sitzung.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl der CPU-Kerne des Endpunkts des Anrufers.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Die Anzahl von CPU-Kernen des Endpunkts des aufgerufenen.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkt Tabelle](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der [Endpunkt Tabelle](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informationen zu Medien Pfaden, beispielsweise direkt oder weitergeleitet. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|Transport  <br/> |int  <br/> |Transporttyp: 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des Anrufers. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.  <br/> |
|CallerPort  <br/> |int  <br/> |Der vom Aufrufer verwendete Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des aufgerufenen. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.  <br/> |
|CalleePort  <br/> |int  <br/> |Port, der vom aufgerufenen verwendet wird.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob sich der Aufrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Der Name der Website des Anrufers.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Name des Landes/der Region der Website des Anrufers.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Name der Website des aufgerufenen.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Name des Landes/der Region der Website des berufenen.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port des A/V-Edgedienst, der vom Anrufer verwendet wird.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port auf dem A/V-Edgedienst, der vom aufgerufenen verwendet wird.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräte Treibers des Anrufers.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Name des Render-Gerätetreibers des Anrufers.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Der Name des Erfassungsgeräts des Anrufers.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Der Name des Capture-Gerätetreibers des anrufempfängers.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Der Name des Render-Gerätetreibers des Benutzers.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal (18;)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal (18; 0)  <br/> |Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen (in BPS).  <br/> |
|ConversationalMOS  <br/> |Dezimal (3; 2)  <br/> |Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.). Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maximaler Netzwerk Jitter während des Anrufs.  <br/> |
|RoundTrip  <br/> |int  <br/> |Roundtrip-Zeit von RTCP-Statistiken  <br/> |
|RoundTripMax  <br/> |int  <br/> |Maximale Roundtrip-Zeit für den Audiostream.  <br/> |
|PacketLossRate  <br/> |Dezimal (5; 4)  <br/> |Durchschnittliche Paketverlustrate während des Anrufs.  <br/> |
|PacketLossRateMax  <br/> |Dezimal (5; 4)  <br/> |Maximaler Paketverlust während des Anrufs.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Paketanzahl für den Videostream (Echt Zeit Transport Protokoll, RTP).  <br/> |
|Bandbreite  <br/> |int  <br/> |Bandbreiten Schätzungen für den Audiostream.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Für den Anruf verwendeter Audiocodec, auf den in der [PayloadDescription-Tabelle](payloaddescription.md)verwiesen wird.  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |Auflösung des Videos in Pixel Breite multipliziert mit Höhe des Pixels. Als Zeichenfolge gemeldet.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Durchschnittliche Bitrate des Videodatenstroms.  <br/> |
|InboundVideoFrameRateAvg  <br/> |Dezimal (9; 4)  <br/> |Bildrate des empfangenen Videos.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |Dezimal (9; 4)  <br/> |Bildrate des gesendeten Videos.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Maximale Video Bitrate während der Videositzung.  <br/> |
|VideoPacketLossRate  <br/> |Dezimal (9; 4)  <br/> |Die Rate, mit der Videopakete verloren gegangen sind.  <br/> |
|VideoFrameLossRate  <br/> |Decimal (9.4)  <br/> |Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Nicht verwendet.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Der durchschnittliche Umfang der für Video zugewiesenen Bandbreite.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |Decimal (9.4)  <br/> |Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gegangen sind.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Datenstrom Richtung für p-asserted Identity-Informationen. 1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.  <br/> |
   

