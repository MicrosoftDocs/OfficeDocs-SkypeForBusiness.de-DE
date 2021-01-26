---
title: Tabelle "MediaLine"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Jeder Datensatz stellt eine Medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Videositzung (A/V) enthält in der Regel eine Audiomedienzeile und eine Videomedienzeile, obwohl die Sitzung möglicherweise zwei Videomedienzeilen enthält, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802765"
---
# <a name="medialine-table"></a>Tabelle "MediaLine"
 
Jeder Datensatz stellt eine Medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Videositzung (A/V) enthält in der Regel eine Audiomedienzeile und eine Videomedienzeile, obwohl die Sitzung möglicherweise zwei Videomedienzeilen enthält, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [Sitzungstabelle.](session.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [Sitzungstabelle.](session.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 ist Hauptaudio, 1 ist hauptvideo und 2 ist Panoramavideo, 3 ist Anwendungs-/Desktopfreigabe, 16 ist videobasierte Bildschirmfreigabe (VbSS). Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Diese Spalte ist vorhanden, wird jedoch in Microsoft Lync Server 2013 nicht verwendet. Informationen über die für eine Medienleitung verwendete Konnektivität werden in den Spalten "CallerConnectivityICE" und "CalleeConnectivityICE" erfasst.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informationen zum Interactive Connectivity Establishment (ICE)-Prozess, der in Bitflags beschrieben wird. Weitere Informationen finden Sie in der  *Quality of Experience Monitoring Server Protocol Specification*  , die zum Download verfügbar ist. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identisch mit CallerIceWarningFlags, jedoch auf der Anrufeseite. Weitere Informationen finden Sie in der  *Quality of Experience Monitoring Server Protocol Specification*  , die zum Download verfügbar ist. <br/> |
|**Sicherheit** <br/> |tinyint  <br/> | <br/> |Das verwendeten Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 ist UDP, 1 ist TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des Anrufers. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Vom Anrufer verwendeter Port. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Fremd <br/> |Das Subnetz des Anrufers. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Fremd  <br/> |Die Mac-Adresse des Anrufers, auf die in der [Tabelle "MacAddress" verwiesen wird.](macaddress.md)  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Fremd  <br/> |IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Anrufer für den A/V-Edgedienst verwendet wird.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Fremd  <br/> |Vom Anrufer verwendetes Gerät erfassen. Referenziert aus der [Tabelle "Gerät".](device.md)  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Fremd  <br/> |Rendergerät, das vom Anrufer verwendet wird. Referenziert aus der [Tabelle "Gerät".](device.md)  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Aufnahmegerät des Anrufers, auf den in der [#A0 verwiesen wird.](devicedriver.md)  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Rendergerät des Anrufers, auf den in der [#A0 verwiesen wird.](devicedriver.md)  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Fremd  <br/> |Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist. Werte werden aus der [Tabelle "NetworkConnectionDetail" ermittelt.](networkconnectiondetail.md) Typische Werte sind 0 für eine kabelgebundene Verbindung' 1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Fremd  <br/> |BSSID des Anrufers, wenn drahtlos verwendet wird. Referenziert aus [der MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Der Link des Anrufers. 1 ist VPN, 0 ist Nicht-VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Die Geschwindigkeit der Netzwerkverbindung in Bps für den Endpunkt des Anrufers.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des Anrufempfängers. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CalleePort** <br/> |bit  <br/> ||Vom Anrufempfänger verwendeter Port.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Fremd  <br/> |Subnetz des Anrufeten. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 bedeutet, dass sich der Anrufempfänger innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufempfänger außerhalb des Netzwerks befindet.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Fremd  <br/> |Mac-Adresse des Anrufeten. Referenziert aus der [MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des vom Anrufempfänger verwendeten A/V-Edgediensts. Weitere Informationen [finden Sie in der Tabelle "IPAddress".](ipaddress.md) <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Anrufempfänger für den A/V-Edgedienst verwendet wird.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |fremd  <br/> |Vom Anrufempfänger verwendetes Aufnahmegerät. Referenziert aus der [Tabelle "Gerät".](device.md)  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Fremd  <br/> |Rendergerät, das vom Anrufempfänger verwendet wird. Referenziert aus der [Tabelle "Gerät".](device.md)  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Aufnahmegerät des Anrufempfängers. Referenziert aus [der DeviceDriver-Tabelle.](devicedriver.md)  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Fremd  <br/> |Treiber für das Rendergerät des Anrufempfängers. Referenziert aus [der DeviceDriver-Tabelle.](devicedriver.md)  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Fremd  <br/> |Gibt an, wie der Anrufee mit dem Netzwerk verbunden ist. Werte werden aus der [Tabelle "NetworkConnectionDetail" ermittelt.](networkconnectiondetail.md) Typische Werte sind 0 für eine kabelgebundene Verbindung' 1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Fremd  <br/> |BSSID des Anrufers, wenn drahtlos verwendet wird. Referenziert aus [der MacAddress-Tabelle.](macaddress.md)  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Der Link des Anrufempfängers; 1 ist ein virtuelles privates Netzwerk (VPN), 0 ist kein VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Die Geschwindigkeit der Netzwerkverbindung in Bps für den Endpunkt des Anrufempfängers.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Dies ist die tatsächliche Bandbreite, die auf den angegebenen sendeseitigen Datenstrom bei verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Policy Server und so weiter) angewendet wird. Dies ist nicht mit der effektiven Bandbreite zu verwechseln, da es basierend auf der Bandbreitenschätzung eine niedrigere effektive Bandbreite gibt. Dabei handelt es sich im Wesentlichen um die maximale Bandbreite, die der Sendedatenstrom für die Beschränkungen verwenden kann, die von der Bandbreitenschätzung auferlegt werden.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Dies ist die Quelle der Bandbreitengrenze, die auferlegt wird. Es wird beschrieben, woher die Bandbreitenbeschränkung kommt ("Policy Server", "TURN Server", "Modality" und so weiter). Referenziert aus der [Tabelle "AppliedBandwidthSource".](appliedbandwidthsource.md)  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Gibt an, ob Metriken vom Anrufer empfangen wurden; 1 ist ja, ein Nullwert ist nein.  <br/> |
|**Ankrufer** <br/> |bit  <br/> | <br/> |Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein Nullwert ist nein.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Gibt an, ob der Bericht für einen Teil der Sitzung oder für die gesamte Sitzung gilt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Gibt an, ob ein Anruf als Anruf schlechter Qualität (Wert 1) oder als guter Anruf (0) klassifiziert wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerSteigerLocalIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die ip-Adresse des Benutzers, der den Anruf anruft. In Organisationen, die NAT (Netzwerkadressenübersetzung) verwenden, ist dies die ip-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Fremd  <br/> |Gerätebeschreibung für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf tätigt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Fremd  <br/> |Versionsnummer für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf tätigt hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleIziiveLocalIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die ip-Adresse des Benutzers, der den Anruf empfangen hat. In Organisationen, die NAT (Netzwerkadressenübersetzung) verwenden, ist dies die ip-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Fremd  <br/> |Gerätebeschreibung für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf empfangen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Fremd  <br/> |Versionsnummer für den WLAN-Treiber, der vom Benutzer verwendet wird, der den Anruf angenommen hat.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

