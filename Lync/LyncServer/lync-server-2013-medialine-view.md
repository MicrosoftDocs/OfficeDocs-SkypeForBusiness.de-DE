---
title: MediaLine-Ansicht
TOCTitle: MediaLine-Ansicht
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49890630
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MediaLine-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Video (A/V)-Sitzung enthält in der Regel eine Audiomedienzeile und eine Videomedienzeile; die Sitzung kann jedoch auch zwei Videomedienzeilen enthalten, wenn ein Konferenzgerät oder die Katalogansicht verwendet werden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>datetime</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Anrufer beschrieben. Ausführliche Informationen finden Sie im Artikel &quot;Quality of Experience Monitoring Server Protocol Specification&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Angerufenen beschrieben. Ausführliche Informationen finden Sie im Artikel &quot;Quality of Experience Monitoring Server Protocol Specification&quot;.</p></td>
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
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Anrufers. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Vom Anrufer verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich innerhalb des Unternehmensnetzwerks. 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>MAC-Adresse der von Anrufer verwendeten Netzwerkschnittstelle.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie unter <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Anrufers, wie vom A/V-Edgedienst berichtet. Diese Adresse kann sich von &quot;CallerIPAddr&quot; unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Treibers des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Treibers des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>Beschreibung des WLAN-Treibers des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>WLAN-Treiberversion des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Details der Netzwerkverbindung des Anrufers. Weitere Informationen finden Sie unter <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Von der WLAN-Verbindung des Anrufers verwendete BSSID (Basic Service Set Identifier).</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Angerufenen. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Vom Angerufenen verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob sich der Angerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>MAC-Adresse der von Angerufenen verwendeten Netzwerkschnittstelle.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des vom Angerufenen verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie unter <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der vom Angerufenen auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Angerufenen, wie vom A/V-Edgedienst berichtet. Diese Adresse kann sich von &quot;CalleeIPAddr&quot; unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var(50)</p></td>
<td><p>Name des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Treibers des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Treibers des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>Beschreibung des WLAN-Treibers des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>WLAN-Treiberversion des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>Details der Netzwerkverbindung des Angerufenen. Weitere Informationen finden Sie unter <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>Von der WLAN-Verbindung des Angerufenen verwendete BSSID (Basic Service Set Identifier).</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar(256)</p></td>
<td><p>Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B.&quot;Policy Server&quot;, &quot;TURN Server&quot; oder &quot;Modality&quot;).</p></td>
</tr>
<tr class="odd">
<td><p>Anrufer</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist nein.</p></td>
</tr>
<tr class="even">
<td><p>Angerufener</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, 0 ist nein.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob es sich um einen Bericht zu einem Teil des Anrufs oder zum gesamten Anruf handelt.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
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

