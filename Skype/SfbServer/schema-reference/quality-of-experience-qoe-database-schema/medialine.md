---
title: MediaLine-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine-Ansicht speichert Informationen zu jeder medienzeile in der Datenbank. Eine audiositzung enthält in der Regel eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält eine Audiomedien Zeile und eine Videomedien Zeile; die Sitzung kann jedoch zwei Videomedien Zeilen enthalten, wenn ein Konferenzgerät verwendet wird oder Katalogansicht verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 04037bae4b2f04058667d42205a2e0b33abacb4f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212200"
---
# <a name="medialine-view"></a>MediaLine-Ansicht
 
MediaLine-Ansicht speichert Informationen zu jeder medienzeile in der Datenbank. Eine audiositzung enthält in der Regel eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält eine Audiomedien Zeile und eine Videomedien Zeile; die Sitzung kann jedoch zwei Videomedien Zeilen enthalten, wenn ein Konferenzgerät verwendet wird oder Katalogansicht verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für den Anrufer. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informationen zum Vorgang, Interactive Connectivity Establishment (ICE) beschriebenen in Bits Flags für des angerufenen. Weitere Informationen hierzu finden Sie in der Qualität der Experience Monitoring Server-Protokoll-Spezifikation.  <br/> |
|Sicherheit  <br/> |tinyint  <br/> |Security-Profil verwendet. "0" ist keine, 1 ist SRTP, 2 V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Transporttyp. 0 ist UDP, 1 ist TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers. Dies kann eine IPv4 oder IPv6-Adresse sein.  <br/> |
|CallerPort  <br/> |int  <br/> |Vom Anrufer verwendeter Port.  <br/> |
|CallerInside  <br/> |bit  <br/> |Gibt an, ob der Anrufer innerhalb des Netzwerks der Organisation ist. 1 bedeutet, dass der Anrufer innerhalb des Unternehmensnetzwerks ist. 0 bedeutet, dass der Anrufer außerhalb des Netzwerks ist.  <br/> |
|CallerMacAddress  <br/> |varchar(256)-Wert  <br/> |MAC-Adresse des vom Anrufer verwendeten Netzwerkschnittstelle.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des A / V-edgedienst vom Anrufer verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port verwendet, auf dem A / V-edgedienst vom Anrufer verwendeten.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |IP-Adresse des Anrufers gemeldete vom A / V-edgedienst. Diese Adresse kann unterschiedlich sein, die die CallerIPAddr, wenn der Client hinter NAT beispielsweise befindet.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)-Wert  <br/> |Name des Aufnahmegeräts des Anrufers.  <br/> |
|CallerRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des Anrufers.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des Anrufers Gerät Treiber.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des Anrufers.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |Varchar (256  <br/> |Beschreibung des Anrufers-WLAN-Treibers.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)-Wert  <br/> |Treiberversion des Anrufers.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)-Wert  <br/> |Details der Netzwerkverbindung des Anrufers. Finden Sie weitere Informationen der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) . <br/> |
|CallerBssid  <br/> |varchar(256)-Wert  <br/> |Basic Service Set Identifier verwendete BSSID WLAN-Verbindung.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |IP-Adresse des angerufenen. Dies kann eine IPv4 oder IPv6-Adresse sein.  <br/> |
|CalleePort  <br/> |int  <br/> |Vom angerufenen verwendeter Port.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Gibt an, ob die aufgerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, dass aufgerufene innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass die aufgerufene außerhalb des Netzwerks befindet.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)-Wert  <br/> |MAC-Adresse der von angerufenen verwendeten Netzwerkschnittstelle.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP-Adresse des A / V-edgedienst vom angerufenen verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port verwendet, auf dem A / V-edgedienst vom angerufenen verwendeten.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |IP-Adresse des angerufenen gemeldete vom A / V-edgedienst. Diese Adresse kann unterschiedlich sein, die die CalleeIPAddr, wenn der Client hinter NAT beispielsweise befindet.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Name des Aufnahmegeräts des angerufenen.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)-Wert  <br/> |Name des darstellungsgeräts des angerufenen.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)-Wert  <br/> |Name des angerufenen Gerät Treiber.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)-Wert  <br/> |Treibername des darstellungsgeräts des angerufenen.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)-Wert  <br/> |Beschreibung des angerufenen-WLAN-Treibers.  <br/> |
|CalleeWifiDriverVersion  <br/> |Varchar (256  <br/> |Treiberversion des angerufenen.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)-Wert  <br/> |Details der Netzwerkverbindung des angerufenen. Finden Sie weitere Informationen der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) . <br/> |
|CalleeBssid  <br/> |varchar(256)-Wert  <br/> |Basic Service Set Identifier von angerufenen WLAN-Verbindung verwendet.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Schmalband-Gesprächs-MOS der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Dies ist die tatsächliche Bandbreite in den angegebenen senden Seite Stream angegebenen verschiedene Einstellungen für die Informationsverwaltungsrichtlinie (aktivieren, API, SDP, Policy Server.) angewendet. Es sollte sich nicht um mit der effektiven Bandbreite verwechselt werden, da möglicherweise ein niedriger Bandbreite basierend auf die Schätzung für das Bandbreite. Dies ist im Wesentlichen die maximale Bandbreite, die der Stream senden läuft Grenzwerte, die auf die Schätzung für das Bandbreite durchführen kann.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)-Wert  <br/> |Die Quelle des Endes Bandbreite eingeführt wird. Beschrieben werden, in dem der Grenzwert für Bandbreite (beispielsweise "Richtlinienserver", "Server aktivieren" oder "Modalität") stammt.  <br/> |
|Anrufer  <br/> |bit  <br/> |Gibt an, ob die Metriken des Anrufers empfangen wurden. 1 = Ja, 0 = keine.  <br/> |
|Callee  <br/> |bit  <br/> |Gibt an, ob die Metriken des angerufenen empfangen wurden. 1 = Ja, 0 = keine.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Gibt an, ob der Bericht für einen Teil des Anrufs oder zum gesamten Anruf handelt.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Gibt an, ob ein Anruf als Anruf schlechter Qualität (1) oder als Anruf guter (0) klassifiziert wurde.  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Gibt an, ob der Anrufer über das ICE-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden.  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Gibt an, ob der Benutzer mit dem Netzwerk mithilfe des ICE (Internet Connectivity Establishment) verbunden bezeichnet.  <br/> |
   

