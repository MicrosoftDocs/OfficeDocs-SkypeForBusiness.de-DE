---
title: 'Lync Server 2013: AudioStreamDetail-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>AudioStreamDetail-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Die AudioStreamDetail-Ansicht speichert Informationen über jeden Audiostream in der Datenbank. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>SessionTime</p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="odd">
<td><p>Datenstrom-Nr</p></td>
<td><p>int</p></td>
<td><p>Eindeutige ID innerhalb einer Medienzeile.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Startzeitpunkt der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Endzeit der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>Bit</p></td>
<td><p>Dialog Feld Kategorie: 0 ist die lync Server Vermittlungsserver Bein; 1 ist die Vermittlungsserver zu PSTN-Gateway-Bein.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>Bit</p></td>
<td><p>Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Gibt an (falls vorhanden), warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmten. Es ist nur ein Wert definiert:</p>
<p>0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</p></td>
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
<td><p>Anrufer</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>Aufgerufene</p></td>
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
<td><p>Benutzeragentenart des Anrufers. Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Benutzeragentenkategorie des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Zeichenfolge für den Benutzer-Agent des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Typ des Benutzer-Agent des Angerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie des Benutzer-Agent des Angerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</p></td>
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
<td><p>Anrufer</p></td>
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
<td><p>Anzahl der Prozessorkerne des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Anzahl der Prozessorkerne des Endpunkts des Angerufenen.</p></td>
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
<td><p>Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Korrelationsschlüssel. Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informationen zum Medienpfad, z. B. direkt oder Relay. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Transporttyp: 0 ist UDP, 1 ist TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Anrufers. Dies kann eine IPv4- oder eine IPv6-Adresse sein.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Vom Anrufer verwendeter Port.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob sich der Anrufer innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des Angerufenen. Dies kann eine IPv4- oder eine IPv6-Adresse sein.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Vom Angerufenen verwendeter Port.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob sich der Angerufene innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Angerufene sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Angerufene außerhalb des Netzwerks befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der Website des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der Website des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der durch den A/V-Edgedienst des Anrufers verwendete Port.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der durch den A/V-Edgedienst des Angerufenen verwendete Port.</p></td>
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
<td><p>Name des Treibers für das Aufnahmegerät des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
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
<td><p>Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>Decimal (18, 0)</p></td>
<td><p>Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>Decimal (18, 0)</p></td>
<td><p>Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Maximaler Netzwerkjitter während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p>Maximale Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p>Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p>Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Paketwert für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>Bandbreite</p></td>
<td><p>int</p></td>
<td><p>Bandbreitenschätzwerte für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Der für den Aufruf verwendete Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013</a>von der PayloadDescription-Tabelle referenziert wird.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Samplingrate für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiosignals der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiosignals für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiogeräusches der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Echodämpfungsverbesserung für den Anrufer. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Driftrate der Uhr des Mikrofons des Anrufers, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Driftrate der Uhr des Lautsprechers des Anrufers, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Anrufers in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Ursachen von Echoereignissen für den Anrufer. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Anrufers Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Prozentsatz der Zeit, in der im gesendeten Datenstrom des Anrufers Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>Gleitkommazahl</p></td>
<td><p>RMS (Effektivwert) des eingehenden Signals an den Anrufer in den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stellt die Stärke des Audiosignals der postanalogen Verstärkung für das vom Angerufenen gesendete Audio dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiosignals für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Echodämpfungsverbesserung für den Angerufenen. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Driftrate der Uhr des Mikrofons des Angerufenen, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Driftrate der Uhr des Lautsprechers des Angerufenen, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p>Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Angerufenen in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Ursachen von Echoereignissen für den Angerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Angerufenen Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Prozentsatz der Zeit, in der im gesendeten Datenstrom des Angerufenen Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Angerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>Gleitkommazahl</p></td>
<td><p>RMS (Effektivwert) des eingehenden Signals an den Angerufenen in den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="even">
<td><p>Roundtrip</p></td>
<td><p>int</p></td>
<td><p>Roundtripzeit aus RTCP-Statistik.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Maximale Roundtripzeit für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich umfasst [1,0 bis 5,0].</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Minimaler Breitband-Netzwerk-MOS für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendetes Audio, einschließlich Sprachpegel, Rauschen und Aufnahmegerätmerkmale.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Minimaler SendListenMOS für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Durchschnittlicher vorhergesagter Breitband-Hör-MOS für empfangenes Audio aus dem Netzwerk, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Aufnahmegerätmerkmale.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p>Minimaler RecvListenMOS für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob Audio-FEC für den Anruf verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>Bit</p></td>
<td><p>Gibt die Richtung der P-Asserted-Identify-Information an; 1 bedeutet, dass die Streamrichtung vom Anrufer zum Angerufenen verläuft; 0 bedeutet, dass die Streamrichtung vom Angerufenen zum Anrufer verläuft.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

