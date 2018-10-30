---
title: 'Lync Server 2013: MediaLine-Tabelle'
TOCTitle: MediaLine-Tabelle
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425920(v=OCS.15)
ms:contentKeyID: 49293803
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MediaLine-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz stellt eine Medienzeile dar. (Eine Audiositzung enthält in der Regel eine Audiomedienzeile. Eine Audio- und Videositzung (A/V) enthält in der Regel eine Audiomedienzeile und eine Videomedienzeile. Bei Verwendung eines Konferenzgeräts oder der Katalogansicht kann die Sitzung jedoch auch zwei Videomedienzeilen enthalten.)


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
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-session-table.md">Session-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-session-table.md">Session-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0 ist Hauptaudio, 1 ist Hauptvideo, 2 ist Panoramavideo und 3 ist Anwendungs-/Desktopfreigabe. Diese Bezeichnung muss in einer einzelnen Sitzung eindeutig sein.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Diese Spalte ist in Microsoft Lync Server 2013 vorhanden, wird jedoch nicht verwendet. Informationen zur für eine Medienzeile verwendeten Konnektivität werden in den Spalten &quot;CallerConnectivityICE&quot; und &quot;CalleeConnectivityICE&quot; erfasst.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel <em>Quality of Experience Monitoring Server Protocol Specification</em> , der zum Download zur Verfügung steht (möglicherweise in englischer Sprache).</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Genau wie &quot;CallerIceWarningFlags&quot;, aber auf der Seite des Angerufenen. Ausführliche Informationen finden Sie im Artikel <em>Quality of Experience Monitoring Server Protocol Specification</em> , der zum Download zur Verfügung steht (möglicherweise in englischer Sprache).</p></td>
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
<td><p>IP-Adresse des Anrufers. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
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
<td><p>Fremd</p></td>
<td><p>Das Subnetz des Anrufers. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>MAC-Adresse des Anrufers, verwiesen von der <a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>IP-Adresse des vom Anrufer verwendeten Lync Server-A/V-Edgediensts. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufer verwendetes Aufnahmegerät. Verwiesen von <a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufer verwendetes Darstellungsgerät. Verwiesen von <a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Aufnahmegerät des Anrufers, verwiesen von <a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Darstellungsgerät des Anrufers, verwiesen von <a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt an, wie der Anrufer die Verbindung zum Netzwerk hergestellt hat. Die Werte werden aus der <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle</a> bezogen. Typische Werte sind 0 für eine drahtgebundene Verbindung, 1 für eine WiFi-Verbindung und 3 für eine Ethernet-Verbindung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>BSSID des Anrufers bei kabelloser Verbindung. Verwiesen von der <a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Link des Anrufers. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p></p></td>
<td><p>Netzwerkübertragungsrate in Bit/s für den Endpunkt des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>IP-Adresse des Anrufempfängers. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Vom Anrufempfänger verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Subnetz des Anrufempfängers. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, der Anrufempfänger befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufempfänger befindet sich außerhalb des Netzwerks.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>MAC-Adresse des Angerufenen. Verwiesen von der <a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>IP-Adresse des vom Anrufempfänger verwendeten A/V-Edgediensts. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Der vom Anrufempfänger auf dem A/V-Edgedienst verwendete Port.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>foreign</p></td>
<td><p>Vom Anrufempfänger verwendetes Aufnahmegerät. Verwiesen von <a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufempfänger verwendetes Darstellungsgerät. Verwiesen von <a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Aufnahmegerät des Anrufempfängers. Verwiesen von <a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Fremd</p></td>
<td><p>Treiber für das Darstellungsgerät des Anrufempfängers. Verwiesen von <a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt an, wie der Angerufene die Verbindung zum Netzwerk hergestellt hat. Die Werte werden aus der <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle</a> bezogen. Typische Werte sind 0 für eine drahtgebundene Verbindung, 1 für eine WiFi-Verbindung und 3 für eine Ethernet-Verbindung.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>BSSID des Anrufempfängers bei kabelloser Verbindung. Verwiesen von der <a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Link des Anrufempfängers. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p> </p></td>
<td><p>Netzwerkübertragungsrate in Bit/s für den Endpunkt des Anrufempfängers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Dies ist die Quelle der auferlegten Bandbreitenbeschränkung. Sie beschreibt, wodurch die Bandbreite beschränkt wird (”Richtlinienserver”, ”TURN-Server”, ”Modalität” usw.). Verwiesen von der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, ein Nullwert ist nein.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Callee</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, ein Nullwert ist nein.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob der Bericht für die gesamte Sitzung oder nur einen Teil davon gilt.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob ein Anruf als Anruf schlechter (Wert gleich 1) oder guter (0) Qualität klassifiziert wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Gibt an, ob der Anrufer sich über das ICE-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden hat.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Gibt an, ob der Anrufer sich über das ICE-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden hat.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die reflexive IP-Adresse des Benutzers, der den Anruf ausgeführt hat. In Organisationen, die NAT (Network Address Translation, Netzwerkadressenübersetzung) verwenden, ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gerätebeschreibung für den von dem Benutzer, der den Anruf ausgeführt hat, verwendeten WLAN-Treiber.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Versionsnummer des von dem Benutzer, der den Anruf ausgeführt hat, verwendeten WLAN-Treibers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die reflexive IP-Adresse des Benutzers, der den Anruf empfangen hat. In Organisationen, die NAT (Network Address Translation, Netzwerkadressenübersetzung) verwenden, ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gerätebeschreibung für den von dem Benutzer, der den Anruf empfangen hat, verwendeten WLAN-Treiber.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Versionsnummer des von dem Benutzer, der den Anruf empfangen hat, verwendeten WLAN-Treibers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

