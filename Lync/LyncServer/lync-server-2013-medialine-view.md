---
title: 'Lync Server 2013: medialinie-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1b8cac172b4973f86916269585d2d9b02cdc728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505732"
---
# <a name="medialine-view-in-lync-server-2013"></a>Medienansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Angerufenen beschrieben. Ausführliche Informationen finden Sie im Artikel "Quality of Experience Monitoring Server Protocol Specification".</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>tinyint</p></td>
<td><p>Verwendetes Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Transporttyp. 0 ist UDP, 1 ist TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Anrufers. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Vom Anrufer verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich innerhalb des Unternehmensnetzwerks. 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>MAC-Adresse der von Anrufer verwendeten Netzwerkschnittstelle.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Anrufers, wie vom A/V-Edgedienst berichtet. Diese Adresse kann sich von "CallerIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Treibers des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>Beschreibung des WLAN-Treibers des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>WLAN-Treiberversion des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Details der Netzwerkverbindung des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>Von der WLAN-Verbindung des Anrufers verwendete BSSID (Basic Service Set Identifier).</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Angerufenen. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Vom Angerufenen verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob sich der Angerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>MAC-Adresse der von Angerufenen verwendeten Netzwerkschnittstelle.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des vom Angerufenen verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der vom Angerufenen auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Angerufenen, wie vom A/V-Edgedienst berichtet. Diese Adresse kann sich von "CalleeIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
<td><p>Name des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Treibers des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>Beschreibung des WLAN-Treibers des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>WLAN-Treiberversion des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>Details der Netzwerkverbindung des Angerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>Von der WLAN-Verbindung des Angerufenen verwendete BSSID (Basic Service Set Identifier).</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B."Policy Server", "TURN Server" oder "Modality").</p></td>
</tr>
<tr class="odd">
<td><p>Anrufer</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist nein.</p></td>
</tr>
<tr class="even">
<td><p>Aufgerufene</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, 0 ist nein.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob es sich um einen Bericht zu einem Teil des Anrufs oder zum gesamten Anruf handelt.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Anruf als Anruf schlechter Qualität (1) oder als Anruf guter Qualität (0) klassifiziert wurde.</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob sich der angerufene Benutzer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

