---
title: MediaLine-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Jeder Datensatz stellt eine medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audio-medienzeile. Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-Medien Linie und eine Video Medien Linie, obwohl die Sitzung zwei Video Medien Linien enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.
ms.openlocfilehash: f9ededade35e5654a89b68343f44094f4319ae70
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294894"
---
# <a name="medialine-table"></a>MediaLine-Tabelle
 
Jeder Datensatz stellt eine medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audio-medienzeile. Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-Medien Linie und eine Video Medien Linie, obwohl die Sitzung zwei Video Medien Linien enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Wird aus der [Sitzungstabelle](session.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Wird aus der [Sitzungstabelle](session.md)referenziert.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 ist Haupt-Audio, 1 ist das Hauptvideo, und 2 ist ein Panorama Video, 3 ist die Anwendung/Desktop-Freigabe, 16 ist videobasierter Bildschirmübertragung (schlechte VBSS). Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet. Informationen zur für eine medienzeile verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informationen über das in Bits-Flags beschriebene Verfahren zum interaktiven Verbindungsaufbau (ICE). Ausführliche Informationen finden Sie in der *Spezifikation für Quality of Experience Monitoring Server Protocol* , die zum Download zur Verfügung steht. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identisch mit CallerIceWarningFlags, aber auf der aufgerufenen Seite. Ausführliche Informationen finden Sie in der *Spezifikation für Quality of Experience Monitoring Server Protocol* , die zum Download zur Verfügung steht. <br/> |
|**Sicherheit** <br/> |tinyint  <br/> | <br/> |Das verwendete Sicherheitsprofil. 0 ist None, 1 ist SRTP, 2 ist v1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 ist UDP, 1 ist TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des Anrufers. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Der vom Aufrufer verwendete Port. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Fremd <br/> |Das Subnetz des Anrufers. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Fremd  <br/> |Die Mac-Adresse des Anrufers, auf die von der [macaddress-Tabelle](macaddress.md)verwiesen wird.  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Anrufer für den A/V-Edgedienst verwendet wird.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Fremd  <br/> |Das vom Anrufer verwendete Aufnahmegerät. Wird in der [Gerätetabelle](device.md)referenziert.  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Fremd  <br/> |Vom Aufrufer verwendetes Render-Gerät. Wird in der [Gerätetabelle](device.md)referenziert.  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Aufnahmegerät des Anrufers, auf das aus der [ACPITreiber-Tabelle](devicedriver.md)verwiesen wird.  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Render-Gerät des Anrufers, auf das aus der [ACPITreiber-Tabelle](devicedriver.md)verwiesen wird.  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Fremd  <br/> |Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist. Werte werden aus der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Fremd  <br/> |BSSID des Anrufers, wenn Wireless verwendet wird. Referenziert aus der [macaddress-Tabelle](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Der Link des Anrufers. 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|**CallerLinkSpeed** <br/> |Decimal (18; 0)  <br/> ||Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des anrufempfängers. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CalleePort** <br/> |bit  <br/> ||Der vom Anrufempfänger verwendete Port.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Fremd  <br/> |Subnetz der aufgerufenen. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 bedeutet, dass der Anrufempfänger sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufempfänger sich außerhalb des Netzwerks befindet.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Fremd  <br/> |Mac-Adresse des angerufenen Wird in der [macaddress-Tabelle](macaddress.md)referenziert.  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Fremd  <br/> |Die IP-Adresse des A/V-Edgedienst, der vom Empfänger des Anrufs verwendet wird. Weitere Informationen finden Sie in der [Tabelle IPAddress](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port, der vom Anrufempfänger für den A/V-Edgedienst verwendet wird.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |fremd  <br/> |Das vom Anrufempfänger verwendete Aufnahmegerät. Wird in der [Gerätetabelle](device.md)referenziert.  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Fremd  <br/> |Render-Gerät, das vom Empfänger des Anrufs verwendet wird. Wird in der [Gerätetabelle](device.md)referenziert.  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Fremd  <br/> |Treiber für das Aufnahmegerät des anrufempfängers. Referenziert aus der [ACPITreiber-Tabelle](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Fremd  <br/> |Treiber für das Render-Gerät des anrufempfängers. Referenziert aus der [ACPITreiber-Tabelle](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Fremd  <br/> |Gibt an, wie der aufgerufene mit dem Netzwerk verbunden ist. Werte werden aus der [NetworkConnectionDetail-Tabelle](networkconnectiondetail.md)abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Fremd  <br/> |BSSID des anrufempfängers, wenn Wireless verwendet wird. Referenziert aus der [macaddress-Tabelle](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Link des anrufempfängers; 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |Decimal (18; 0)  <br/> | <br/> |Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.  <br/> |
|**ConversationalMOS** <br/> |Dezimal (3; 2)  <br/> | <br/> |Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.). Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits. Es wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Server umwandeln", "Modalität" usw.). Wird in der [AppliedBandwidthSource-Tabelle](appliedbandwidthsource.md)referenziert.  <br/> |
|**Anrufer** <br/> |bit  <br/> | <br/> |Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".  <br/> |
|**Callee** <br/> |bit  <br/> | <br/> |Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Gibt an, ob der Bericht für einen Teil der Sitzung oder für die vollständige Sitzung gilt.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Gibt an, ob ein Anruf als schlechter Anruf (Wert 1) oder als guter Anruf (0) klassifiziert wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Fremd  <br/> |Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat. In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Fremd  <br/> |Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf getätigt hat.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Fremd  <br/> |Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf getätigt hat, verwendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Fremd  <br/> |Reflexive IP-Adresse des Benutzers, der den Anruf erhalten hat. In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Fremd  <br/> |Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf erhalten hat.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Fremd  <br/> |Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf erhalten hat, verwendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

