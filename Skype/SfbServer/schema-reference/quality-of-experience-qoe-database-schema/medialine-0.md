---
title: MediaLine-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Jeder Datensatz stellt eine Medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Videositzung (A/V) enthält in der Regel eine Audiomedienzeile und eine Videomedienleitung, obwohl die Sitzung möglicherweise zwei Videomedienzeilen enthält, wenn ein Konferenzgerät verwendet wird oder die Galerieansicht verwendet wird.
ms.openlocfilehash: ae2d776b47f7fe0ef172c9904ea77ae6188535fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754284"
---
# <a name="medialine-table"></a>MediaLine-Tabelle
 
Jeder Datensatz stellt eine Medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Videositzung (A/V) enthält in der Regel eine Audiomedienzeile und eine Videomedienleitung, obwohl die Sitzung möglicherweise zwei Videomedienzeilen enthält, wenn ein Konferenzgerät verwendet wird oder die Galerieansicht verwendet wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [Session-Tabelle.](session.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [Session-Tabelle.](session.md)  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |0 is main audio, 1 is main video, and 2 is panorama video, 3 is Application/Desktop Sharing, 16 is Video based Screen Sharing (VbSS). Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.  <br/> |
|**ConnectivityIce** <br/> |Tinyint  <br/> | <br/> |Diese Spalte ist vorhanden, wird jedoch in Microsoft Lync Server 2013 nicht verwendet. Informationen über die für eine Medienleitung verwendete Konnektivität werden in den Spalten "CallerConnectivityICE" und "CalleeConnectivityICE" erfasst.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informationen zum ICE-Prozess (Interactive Connectivity Establishment), der in Bits-Flags beschrieben ist. Ausführliche Informationen finden Sie in der  *Quality of Experience Monitoring Server-Protokollspezifikation,*  die zum Download zur Verfügung steht. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identisch mit CallerIceWarningFlags, aber auf der Seite des Angerufenen. Ausführliche Informationen finden Sie in der  *Quality of Experience Monitoring Server-Protokollspezifikation,*  die zum Download zur Verfügung steht. <br/> |
|**Sicherheit** <br/> |Tinyint  <br/> | <br/> |Das verwendete Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.  <br/> |
|**Transport** <br/> |Tinyint  <br/> | <br/> |0 ist UDP, 1 ist TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des Anrufers. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Vom Anrufer verwendeter Port. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Ausländisch <br/> |Das Subnetz des Anrufers. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CallerInside** <br/> |Bit  <br/> | <br/> |1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Ausländisch  <br/> |Die Mac-Adresse des Anrufers, auf die aus der [MacAddress-Tabelle](macaddress.md)verwiesen wird.  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Aufrufer für den A/V-Edgedienst verwendet wird.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Ausländisch  <br/> |Erfasst das vom Anrufer verwendete Gerät. Referenziert aus der [Device-Tabelle.](device.md)  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Ausländisch  <br/> |Rendern des vom Aufrufer verwendeten Geräts. Referenziert aus der [Device-Tabelle.](device.md)  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das Aufnahmegerät des Anrufers, auf das aus der [DeviceDriver-Tabelle](devicedriver.md)verwiesen wird.  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das Rendergerät des Anrufers, auf das aus der [DeviceDriver-Tabelle](devicedriver.md)verwiesen wird.  <br/> |
|**CallerNetworkConnectionType** <br/> |Tinyint  <br/> |Ausländisch  <br/> |Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist. Werte werden aus der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung" 1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Ausländisch  <br/> |BSSID des Anrufers, wenn drahtlos verwendet wird. Referenziert aus [der MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CallerVPN** <br/> |Bit  <br/> ||Der Link des Anrufers. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Die Netzwerkverbindungsgeschwindigkeit (in Basispunkten) für den Endpunkt des Anrufers.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des Anrufempfängers. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CalleePort** <br/> |Bit  <br/> ||Vom Anrufempfänger verwendeter Port.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Ausländisch  <br/> |Subnetz des Angerufenen. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CalleeInside** <br/> |Bit  <br/> | <br/> |1 bedeutet, dass sich der Anrufempfänger innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufempfänger außerhalb des Netzwerks befindet.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Ausländisch  <br/> |Mac-Adresse des Angerufenen. Referenziert aus der [MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |IP-Adresse des A/V-Edgediensts, der vom Anrufempfänger verwendet wird. Weitere Informationen finden Sie in der [IPAddress-Tabelle.](ipaddress.md) <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Anrufempfänger für den A/V-Edgedienst verwendet wird.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |Ausländisch  <br/> |Erfasst das vom Anrufempfänger verwendete Gerät. Referenziert aus der [Device-Tabelle.](device.md)  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Ausländisch  <br/> |Rendern des vom Anrufempfänger verwendeten Geräts. Referenziert aus der [Device-Tabelle.](device.md)  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Ausländisch  <br/> |Treiber für das Aufnahmegerät des Anrufempfängers. Referenziert aus [der DeviceDriver-Tabelle.](devicedriver.md)  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Ausländisch  <br/> |Treiber für das Rendergerät des Anrufempfängers. Referenziert aus [der DeviceDriver-Tabelle.](devicedriver.md)  <br/> |
|**CalleeNetworkConnectionType** <br/> |Tinyint  <br/> |Ausländisch  <br/> |Gibt an, wie der Angerufene mit dem Netzwerk verbunden ist. Werte werden aus der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung" 1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Ausländisch  <br/> |BSSID des Angerufenen, wenn drahtlos verwendet wird. Referenziert aus [der MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CalleeVPN** <br/> |Bit  <br/> | <br/> |Der Link des Anrufempfängers; 1 ist ein virtuelles privates Netzwerk (VPN), 0 ist kein VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Die Netzwerkverbindungsgeschwindigkeit (in Basispunkten) für den Endpunkt des Anrufempfängers.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Dies ist die tatsächliche Bandbreite, die auf den angegebenen Sendeseitendatenstrom angewendet wird, wenn verschiedene Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) gelten. Dies ist nicht mit der effektiven Bandbreite zu verwechseln, da basierend auf der Bandbreitenvorkalkulation eine niedrigere effektive Bandbreite vorhanden sein kann. Hierbei handelt es sich im Wesentlichen um die maximale Bandbreite, die der Sendedatenstrom durch die Bandbreitenvorkalkulation vorgegebene Grenzwerte belegen kann.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |Smallint  <br/> ||Dies ist die Quelle der Bandbreitenbeschränkung, die angewendet wird. Es beschreibt, woher die Bandbreitenbegrenzung stammt ("Richtlinienserver", "TURN Server", "Modalität" usw.). Referenziert aus der [AppliedBandwidthSource-Tabelle.](appliedbandwidthsource.md)  <br/> |
|**Caller** <br/> |Bit  <br/> | <br/> |Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, ein Nullwert ist nein.  <br/> |
|**Aufgerufenen** <br/> |Bit  <br/> | <br/> |Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein Nullwert ist nein.  <br/> |
|**MidCallReport** <br/> |Bit  <br/> ||Gibt an, ob der Bericht für einen Teil der Sitzung oder für die vollständige Sitzung gilt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClassifiedPoorCall** <br/> |Bit  <br/> ||Gibt an, ob ein Anruf als schlechter Anruf (Wert 1) oder als guter Anruf (0) klassifiziert wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerConnectivityICE** <br/> |Tinyint  <br/> ||Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeConnectivityICE** <br/> |Tinyint  <br/> ||Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |Die ip-Adresse des Benutzers, der den Anruf getätigt hat. In Organisationen, die NAT (Netzwerkadressübersetzung) verwenden, ist die ip-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Ausländisch  <br/> |Gerätebeschreibung für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf getätigt hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Ausländisch  <br/> |Versionsnummer für den WLAN-Treiber, der von dem Benutzer verwendet wird, der den Anruf getätigt hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Ausländisch  <br/> |Die ip-Adresse des Benutzers, der den Anruf empfangen hat. In Organisationen, die NAT (Netzwerkadressübersetzung) verwenden, ist die ip-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Ausländisch  <br/> |Gerätebeschreibung für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf empfangen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Ausländisch  <br/> |Versionsnummer für den WLAN-Treiber, der von dem Benutzer verwendet wird, der den Anruf empfangen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

