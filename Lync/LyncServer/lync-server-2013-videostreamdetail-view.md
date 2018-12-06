---
title: VideoStreamDetail-Ansicht
TOCTitle: VideoStreamDetail-Ansicht
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49890998
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoStreamDetail-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Ansicht **VideoStreamDetail** werden Informationen über jeden Videostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>Wird aus der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Wird aus der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Wird aus der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>Eindeutige ID innerhalb einer Medienzeile.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Startzeitpunkt der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Endzeitpunkt der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Priorität des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN des Anruferpools.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN des Angerufenenpools.</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Zeichenfolge für den Benutzer-Agent des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Typ des Benutzer-Agent des Anrufers. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie des Benutzer-Agent des Anrufers. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE)</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Zeichenfolge für den Benutzer-Agent des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Typ des Benutzer-Agent des Angerufenen. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie des Benutzer-Agent des Angerufenen. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE)</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name des Endpunkts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Betriebssystem des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Betriebssystem des Endpunkts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der CPU des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der CPU des Endpunkts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Anzahl der CPU-Kerne des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Anzahl der CPU-Kerne des Endpunkts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der <a href="lync-server-2013-endpoint-table.md">Endpoint-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie in der <a href="lync-server-2013-endpoint-table.md">Endpoint-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informationen zum Medienpfad, z. B. direkt oder Relay. Weitere Informationen finden Sie in der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel &quot;[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll&quot;.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel &quot;[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>Transporttyp: 0 ist UDP, 1 ist TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Vom Anrufer verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des Angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Vom Angerufenen verwendeter Port.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der Website des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der Website des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port auf dem vom Anrufer verwendeten A/V-Edgedienst.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p>
<p></p></td>
<td><p>IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,)</p></td>
<td><p>Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Maximaler Netzwerkjitter während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Roundtripzeit aus RTCP-Statistik.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Maximale Roundtripzeit für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Maximale Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Paketwert für den Videostream (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>Bandbreitenschätzungen für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Für den Anruf verwendeter Audiocodec; wird aus der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char(9)</p></td>
<td><p>Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Bitrate des Videostreams.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Empfangene Framerate des Videostreams.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Gesendete Framerate des Videostreams.</p></td>
</tr>
<tr class="odd">
<td><p>VideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>Maximale Videobitrate während der Videositzung.</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Videpaketverlustrate.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>Nicht verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche für Video reservierte Bandbreite.</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.</p></td>
</tr>
</tbody>
</table>

