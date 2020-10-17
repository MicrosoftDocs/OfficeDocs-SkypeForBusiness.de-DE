---
title: 'Lync Server 2013: medialinie-Tabelle'
description: 'Lync Server 2013: medialinie-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572111"
---
# <a name="medialine-table-in-lync-server-2013"></a>Medientabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-21_

Jeder Datensatz stellt eine Medienleiste dar. (Eine Audiositzung enthält normalerweise eine Audio-Medien-Verbindung. Eine Audio-und Video (A/V)-Sitzung enthält normalerweise eine Audiomedien-und eine Video medienleitung, obwohl die Sitzung zwei Video medienleitungen enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Galerieansicht verwendet wird.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primary</p></td>
<td><p>Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0 ist Haupt-Audio, 1 ist Hauptvideo, 2 ist Panorama Video, 3 ist Application/Desktop Sharing. Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet. Informationen zur für eine Medien Verbindung verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informationen zum unter Bits Flags beschriebenen Ice-Prozess (Interactive Connectivity Establishment). Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Identisch mit CallerIceWarningFlags, jedoch auf der Seite "angerufener". Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicherheit</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Das verwendete Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 ist UDP, 1 ist TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die IP-Adresse des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vom Anrufer verwendeter Port.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> Fremd</p></td>
<td><p>Das Subnetz des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Mac-Adresse des Anrufers, die von der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>referenziert wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die IP-Adresse des vom Anrufer verwendeten lync Server A/V-Edgedienst. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port, der vom Aufrufer auf dem A/V-Edgedienst verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufer verwendete Aufnahmegerät. Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Aufrufer verwendetes Render-Gerät. Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Aufnahmegerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Render-Gerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist. Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>BSSID des Anrufers, wenn Wireless verwendet wird. Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Link des Anrufers. 1 ist VPN, 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>Decimal (18, 0)</p></td>
<td></td>
<td><p>Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>IP-Adresse des anrufempfängers. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Vom Anrufempfänger verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Subnetz des angerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, dass sich der Anrufempfänger innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufempfänger außerhalb des Netzwerks befindet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Mac-Adresse des angerufenen. Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die IP-Adresse des vom Anrufempfänger verwendeten A/V-Edgedienst. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Port, der vom Anrufempfänger im A/V-Edgedienst verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>fremd</p></td>
<td><p>Vom Anrufempfänger verwendetes Aufnahmegerät. Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufempfänger verwendetes Render-Gerät. Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Aufnahmegerät des anrufempfängers. Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Render-Gerät des anrufempfängers. Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt an, wie der angerufene mit dem Netzwerk verbunden ist. Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen. Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>BSSID des angerufenen, wenn Wireless verwendet wird. Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Link des anrufempfängers; 1 ist virtuelles privates Netzwerk (VPN), 0 ist kein VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>Decimal (18, 0)</p></td>
<td><p> </p></td>
<td><p>Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Hierbei handelt es sich um die tatsächliche Bandbreite, die für den angegebenen Sende seitigen Stream mit verschiedenen Richtlinieneinstellungen (Turn, API, SDP, Policy Server usw.) angewendet wird. Dies ist nicht mit der effektiven Bandbreite zu verwechseln, da aufgrund der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Hierbei handelt es sich im Wesentlichen um die maximale Bandbreite, die der sendedatenstrom durch die Schätzung der Bandbreite für die Begrenzung von Beschränkungen ergreifen kann.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Dies ist die Quelle der Bandbreiten Obergrenze, die auferlegt wird. In diesem Artikel wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Turn Server", "Modalität" usw.). Referenziert aus der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob Metriken vom Anrufer empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aufgerufene</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob der Bericht für einen Teil der Sitzung oder für die gesamte Sitzung gilt.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob ein Anruf als schlechter Anruf klassifiziert wurde (Wert 1) oder als guter Aufruf (0).</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat. In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gerätebeschreibung für den von dem Benutzer, der den Anruf getätigt hat, verwendeten WLAN-Treiber.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf getätigt hat, verwendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Reflexive IP-Adresse des Benutzers, der den Anruf empfangen hat. In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gerätebeschreibung für den von dem Benutzer, der den Anruf empfangen hat, verwendeten WLAN-Treiber.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

