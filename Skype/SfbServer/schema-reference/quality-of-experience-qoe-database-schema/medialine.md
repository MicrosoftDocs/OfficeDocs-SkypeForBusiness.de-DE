---
title: MediaLine-Ansicht
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
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 778e322f737a80c71a046073611c234071e3f24b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582569"
---
# <a name="medialine-view"></a>MediaLine-Ansicht
 
Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |Datum/Uhrzeit  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Angerufenen beschrieben. Ausführliche Informationen finden Sie im Artikel "Quality of Experience Monitoring Server Protocol Specification".  <br/> |
|Sicherheit  <br/> |Tinyint  <br/> |Verwendetes Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.  <br/> |
|Transport  <br/> |Tinyint  <br/> |Transporttyp. 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |Bit  <br/> |Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich innerhalb des Unternehmensnetzwerks. 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |MAC-Adresse der von Anrufer verwendeten Netzwerkschnittstelle.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Die VOM A/V-Edgedienst gemeldete IP-Adresse des Anrufers. Diese Adresse kann sich von "CallerIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Der Name des Rendergeräts des Aufrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Der Treibername des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Der Name des Rendergerättreibers des Anrufers.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |Beschreibung des WLAN-Treibers des Anrufers.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Wlan-Treiberversion des Anrufers.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Details zur Netzwerkverbindung des Anrufers. Weitere Informationen finden Sie in der [Tabelle "NetworkConnectionDetail".](networkconnectiondetail.md) <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Von der WLAN-Verbindung des Anrufers verwendete BSSID (Basic Service Set Identifier).  <br/> |
|CallerVPN  <br/> |Bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Angerufenen. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom Angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |Bit  <br/> |Gibt an, ob sich der Angerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb des Netzwerks.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |MAC-Adresse der von Angerufenen verwendeten Netzwerkschnittstelle.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des vom Angerufenen verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Der vom Angerufenen auf dem A/V-Edgedienst verwendete Port.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Die IP-Adresse des Angerufenen, wie vom A/V-Edgedienst gemeldet. Diese Adresse kann sich von "CalleeIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Name des Aufnahmegeräts des Angerufenen.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Der Name des Rendergeräts des Angerufenen.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Der Treibername des Aufnahmegeräts des Angerufenen.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Der Name des Rendergerättreibers des Angerufenen.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Beschreibung des WLAN-Treibers des Angerufenen.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |Wlan-Treiberversion des Angerufenen.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Details zur Netzwerkverbindung des Angerufenen. Weitere Informationen finden Sie in der [Tabelle "NetworkConnectionDetail".](networkconnectiondetail.md) <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Standard-Dienstsatzbezeichner, der von der WLAN-Verbindung des Angerufenen verwendet wird.  <br/> |
|CalleeVPN  <br/> |Bit  <br/> |Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Quelle der Bandbreitenbeschränkung, die auferlegt wird. Es beschreibt, woher die Bandbreiteneinschränkung stammt (z. B. "Richtlinienserver", "TURN Server" oder "Modalität").  <br/> |
|Anrufer  <br/> |Bit  <br/> |Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist nein.  <br/> |
|Aufgerufenen  <br/> |Bit  <br/> |Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, 0 ist nein.  <br/> |
|MidCallReport  <br/> |Bit  <br/> |Gibt an, ob es sich um einen Bericht zu einem Teil des Anrufs oder zum gesamten Anruf handelt.  <br/> |
|ClassifiedPoorCall  <br/> |Bit  <br/> |Gibt an, ob der Anruf als Anruf schlechter Qualität (1) oder als Anruf guter Qualität (0) klassifiziert wurde.  <br/> |
|CallerConnectivityICE  <br/> |Tinyint  <br/> |Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> |
|CalleeConnectivityICE  <br/> |Tinyint  <br/> |Gibt an, ob sich der angerufene Benutzer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> |
   

