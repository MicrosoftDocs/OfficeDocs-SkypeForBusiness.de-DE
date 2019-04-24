---
title: MediaLine-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Jeder Datensatz steht für eine medienzeile. (In der Regel eine audiositzung enthält eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält zeilenweise Audiomedien und Videomedien zeilenweise, obwohl die Sitzung zwei Videomedien Zeilen enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn Katalogansicht verwendet wird.
ms.openlocfilehash: 11c309091211ce0bc480fa032e0f1dbbbbf533cd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212544"
---
# <a name="medialine-table"></a>MediaLine-Tabelle
 
Jeder Datensatz steht für eine medienzeile. (In der Regel eine audiositzung enthält eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält zeilenweise Audiomedien und Videomedien zeilenweise, obwohl die Sitzung zwei Videomedien Zeilen enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn Katalogansicht verwendet wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verwiesen von [Session Table](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Verwiesen von [Session Table](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Haupt-Audiodateien "0" ist, 1 Hauptvideo, und 2 ist panoramavideo, 3 ist Anwendung/Desktopfreigabe, 16 Video Bildschirmfreigabe (VbSS) basiert. Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Diese Spalte ist vorhanden, aber nicht in Microsoft Lync Server 2013 verwendet wird. Informationen über die Konnektivität Media-Zeile wird in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informationen zu den in Bits Flags beschriebenen Prozess der Interactive Connectivity Establishment (ICE). Weitere Informationen hierzu finden Sie in der *Qualität der Experience Monitoring Server Protocol-Spezifikation* , zum Download zur Verfügung. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identisch mit CallerIceWarningFlags, aber auf der Seite des angerufenen. Weitere Informationen hierzu finden Sie in der *Qualität der Experience Monitoring Server Protocol-Spezifikation* , zum Download zur Verfügung. <br/> |
|**Sicherheit** <br/> |tinyint  <br/> | <br/> |Das Sicherheitsprofil verwendet. "0" ist keine, 1 ist SRTP, 2 V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 ist UDP, 1 ist TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des Anrufers. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Vom Anrufer verwendeter Port. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Ausländisch <br/> |Das Subnetz des Anrufers. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 bedeutet, dass Anrufer innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Ausländisch  <br/> |Des Anrufers Mac-Adresse von der [MacAddress Table](macaddress.md)referenziert.  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des A / V-edgedienst vom Anrufer verwendeten. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port verwendet, auf dem A / V-edgedienst vom Anrufer.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Ausländisch  <br/> |Aufnahmegerät des Anrufers. Verweis von der [Device-Tabelle](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Ausländisch  <br/> |Rendern von Anrufer verwendeten Gerät. Verweis von der [Device-Tabelle](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das Aufnahmegerät des Anrufers, verwiesen von [DeviceDriver Table](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das darstellungsgerät des Anrufers, verwiesen von [DeviceDriver Table](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Ausländisch  <br/> |Gibt an, wie der Aufrufer mit dem Netzwerk verbunden. Werte werden von der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine drahtgebundene Verbindung ' 1 für ein WLAN-Verbindung und 3 für eine Ethernet-Verbindung.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Ausländisch  <br/> |BSSID des Anrufers, wenn Wireless verwendet wird. Verwiesen von der [MacAddress Table](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Link des Anrufers. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Die Netzwerkübertragungsrate in Bit/s für den Endpunkt des Anrufers.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des anrufempfängers. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Vom anrufempfänger verwendete Port.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Ausländisch  <br/> |Subnetz des angerufenen. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 bedeutet Empfänger des Anrufs innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Empfänger des Anrufs außerhalb des Netzwerks ist.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Ausländisch  <br/> |Mac-Adresse des angerufenen. Verweis von der [MacAddress-Tabelle](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des A / V-edgedienst verwendete durch den Empfänger des Anrufs. [IPAddress-Tabelle](ipaddress.md) Weitere Informationen finden Sie. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port verwendet, auf dem A / V-Edgedienst durch den Empfänger des Anrufs.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |Ausländisch  <br/> |Aufnahmegerät verwendet, die für den Empfänger des Anrufs. Verweis von der [Device-Tabelle](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Ausländisch  <br/> |Das Gerät, durch den Empfänger des Anrufs zu rendern. Verweis von der [Device-Tabelle](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das Aufnahmegerät des anrufempfängers. Verwiesen von [DeviceDriver Table](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)-Wert  <br/> |Ausländisch  <br/> |Treiber für das darstellungsgerät des anrufempfängers. Verwiesen von [DeviceDriver Table](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Ausländisch  <br/> |Gibt an, wie der aufgerufene mit dem Netzwerk verbunden. Werte werden von der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine drahtgebundene Verbindung ' 1 für ein WLAN-Verbindung und 3 für eine Ethernet-Verbindung.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Ausländisch  <br/> |BSSID des angerufenen, wenn Wireless verwendet wird. Verwiesen von der [MacAddress Table](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Der anrufempfänger in Verbindung. 1 virtuelles privates Netzwerk (VPN), 0 nicht-VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Die Netzwerkübertragungsrate in Bit/s für den Endpunkt des anrufempfängers.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |Schmalband-Gesprächs-MOS der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Dies ist die tatsächliche Bandbreite in den angegebenen senden Seite Stream angegebenen verschiedene Einstellungen für die Informationsverwaltungsrichtlinie (aktivieren, API, SDP, Policy Server usw.) angewendet. Dies ist nicht für die effektive Bandbreite verwechselt werden, da ein niedriger Bandbreite basierend auf die Schätzung für das Bandbreite kann. Dies ist im Wesentlichen die maximale Bandbreite, die der Stream senden läuft Grenzwerte, die auf die Schätzung für das Bandbreite durchführen kann.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Dies ist die Quelle des Endes Bandbreite eingeführt wird. Es wird beschrieben, in dem der Grenzwert für Bandbreite ("Policy Server", "TURN-Servers", "Modalität" usw.) stammt. Verweis von der [AppliedBandwidthSource-Tabelle](appliedbandwidthsource.md).  <br/> |
|**Anrufer** <br/> |bit  <br/> | <br/> |Gibt an, ob die Metriken des Anrufers empfangen wurden. 1 ist Ja, ein null-Wert ist keine.  <br/> |
|**Callee** <br/> |bit  <br/> | <br/> |Gibt an, ob die Metriken des angerufenen empfangen wurden. 1 ist Ja, ein null-Wert ist keine.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Gibt an, ob der Bericht für einen Teil der Sitzung oder für die gesamte Sitzung ist.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Gibt an, ob ein Anruf als Anruf schlechter (Wert 1) oder als Anruf guter (0) klassifiziert wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Gibt an, ob der Anrufer über das ICE-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Gibt an, ob der Anrufer über das ICE-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |Reflexive IP-Adresse des Benutzers, der den Anruf ausgeführt hat. In Organisationen, die NAT (Network Address Translation) verwenden, ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Ausländisch  <br/> |Beschreibung des WLAN-Treibers des Benutzers, der den Anruf ausgeführt hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Ausländisch  <br/> |Versionsnummer des WLAN-Treibers des Benutzers, der den Anruf ausgeführt hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |Reflexive IP-Adresse des Benutzers, der den Anruf empfangen hat. In Organisationen, die NAT (Network Address Translation) verwenden, ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Ausländisch  <br/> |Beschreibung des WLAN-Treibers des Benutzers, der den Anruf empfangen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Ausländisch  <br/> |Versionsnummer des WLAN-Treibers des Benutzers, der den Anruf empfangen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

