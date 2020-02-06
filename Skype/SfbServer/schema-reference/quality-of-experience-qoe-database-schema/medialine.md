---
title: Medienansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: In der medialinie-Ansicht werden Informationen zu jeder medienzeile in der Datenbank gespeichert. Eine Audiositzung enthält in der Regel eine Audio-medienzeile. Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808193"
---
# <a name="medialine-view"></a>Medienansicht
 
In der medialinie-Ansicht werden Informationen zu jeder medienzeile in der Datenbank gespeichert. Eine Audiositzung enthält in der Regel eine Audio-medienzeile. Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|SessionSeq  <br/> |int  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |In der [medialinie-Tabelle](medialine-0.md)referenziert.  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.  <br/> |
|Sicherheit  <br/> |tinyint  <br/> |Verwendetes Sicherheitsprofil 0 ist None, 1 ist SRTP, 2 ist v1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Transporttyp. 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des Anrufers. Dies kann eine IPv4-oder IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Der vom Aufrufer verwendete Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, dass sich der Anrufer innerhalb des Unternehmensnetzwerks befindet. 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Mac-Adresse der vom Anrufer verwendeten Netzwerkschnittstelle.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des Anrufers, wie er vom A/V-Edgedienst gemeldet wurde. Diese Adresse kann sich von der CallerIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Name des Aufnahmegeräte Treibers des Anrufers.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Name des Render-Gerätetreibers des Anrufers.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Beschreibung des WLAN-Treibers des Anrufers.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |WLAN-Treiberversion des Anrufers.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Details zur Netzwerkverbindung des Anrufers. Weitere Informationen finden Sie in der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) . <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |Grundlegende Dienst Satzkennung, die von der WLAN-Verbindung der Anrufer verwendet wird.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des aufgerufenen. Dies kann eine IPv4-oder IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Port, der vom aufgerufenen verwendet wird.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob sich der aufgerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Mac-Adresse der vom aufgerufenen verwendeten Netzwerkschnittstelle.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom aufgerufenen verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |Die IP-Adresse des Betreibers, wie vom A/V-Edgedienst gemeldet. Diese Adresse kann sich von der CalleeIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |Der Name des Erfassungsgeräts des Anrufers.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Name des Render-Geräts.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Der Name des Capture-Gerätetreibers des anrufempfängers.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Der Name des Render-Gerätetreibers des Benutzers.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Beschreibung des WLAN-Treibers des Anrufers.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |WLAN-Treiberversion des anrufempfängers.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Details zur Netzwerkverbindung des berufenen. Weitere Informationen finden Sie in der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) . <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Grundlegende Dienst Satz-ID, die von der WLAN-Verbindung des berufenen verwendet wird.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|ConversationalMOS  <br/> |Dezimal (3; 2)  <br/> |Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.). Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Die Quelle des verhängten Bandbreitenlimits. Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").  <br/> |
|Anrufer  <br/> |bit  <br/> |Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist Nein.  <br/> |
|Callee  <br/> |bit  <br/> |Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, 0 ist Nein.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Gibt an, ob es sich bei dem Bericht um einen Teil des Anrufs oder um einen vollständigen Anruf handelt.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Gibt an, ob ein Anruf als schlechter Anruf (1) oder als guter Anruf (0) klassifiziert wurde.  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Gibt an, ob der Benutzer die Verbindung mit dem Netzwerk mit dem ICE-Protokoll (Internet Connectivity Establishment) aufgerufen hat.  <br/> |
   

