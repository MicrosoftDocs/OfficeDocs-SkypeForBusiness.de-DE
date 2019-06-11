---
title: 'Lync Server 2013: AudioStreamDetail-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>AudioStreamDetail-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

In der AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>datetime</p></td>
<td><p>Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="odd">
<td><p>Datenstrom-Nr</p></td>
<td><p>int</p></td>
<td><p>Eindeutige ID innerhalb einer medienzeile</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Startzeit der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Endzeit der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Dialog Feld Kategorie: 0 ist der lync Server to Mediation Server Leg; 1 ist der Vermittlungs Server für das PSTN-Gateway-Bein.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Wenn vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs zugeordnet wurden. Es wird nur ein Wert definiert:</p>
<p>0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Die Priorität des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des anrufenden Pools.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des aufgerufenen Pools.</p></td>
</tr>
<tr class="even">
<td><p>Anrufer</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Benutzer-Agent-Zeichenfolge des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Der Typ des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Benutzer-Agent-Zeichenfolge des Benutzers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Der Typ des Benutzer-Agents des anrufempfängers. Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie des Benutzer-Agents des berufenen Informationen hierzu finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Endpunktname des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Endpunktname des angerufenen</p></td>
</tr>
<tr class="even">
<td><p>Anrufer</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Betriebssystem (OS) des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Betriebssystem (OS) des Endpunkts des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Der CPU-Name des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Der CPU-Name des Endpunkts des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Die Anzahl der CPU-Kerne im Endpunkt des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Die Anzahl der CPU-Kerne im Endpunkt des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird. Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Korrelationsschlüssel Wird in der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informationen zum Medienpfad, beispielsweise direkt oder weitergeleitet. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird. Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Transporttyp: 0 ist UDP, 1 ist TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Die IP-Adresse des Anrufers. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Der vom Aufrufer verwendete Port.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob sich der Aufrufer innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Die IP-Adresse des aufgerufenen. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Port, der vom aufgerufenen verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob sich der aufgerufene innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Der Name der Website des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name der Website des aufgerufenen.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Name des Landes/der Region der Website des berufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Aufnahmegeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Render-Geräts des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Aufnahmegeräte Treibers des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Render-Gerätetreibers des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Der Name des Erfassungsgeräts des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Name des Render-Geräts.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Der Name des Capture-Gerätetreibers des anrufempfängers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Der Name des Render-Gerätetreibers des Benutzers.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>Decimal (18; 0)</p></td>
<td><p>Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>Decimal (18; 0)</p></td>
<td><p>Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen in BPS.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.). Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann. Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Maximaler Netzwerk Jitter während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>Dezimal (5; 4)</p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>Dezimal (5; 4)</p></td>
<td><p>Maximaler Paketverlust während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>Dezimal (9; 4)</p></td>
<td><p>Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>Dezimal (9; 4)</p></td>
<td><p>Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Die Anzahl der Pakete für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>Bandbreite</p></td>
<td><p>int</p></td>
<td><p>Bandbreiten Schätzungen für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Netzwerk-Mos-Verschlechterung für den gesamten Anruf. Der Bereich ist 0,0 bis 5,0. Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde. Für akzeptable Qualität sollte es weniger als 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Maximaler Netzwerk-Mos-Abbau während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Netzwerk-Mos-Beeinträchtigung durch Jitter.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Netzwerk-Mos-Beeinträchtigung durch Paketverlust.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Der für den Anruf verwendete Audiocodec, auf den von der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Abtastrate für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Analoger Gain-Regler für Audio-Signalpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Audio-Signalpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Verbesserung der Echo-Rückerstattung für den Anrufer. Die Einheit für diese Metrik ist DB. Niedrigere Werte stellen weniger Echo dar. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe des Anrufers. Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers. Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Clock-Drift Rate des Anrufers im Verhältnis zur CPU-Uhr.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Der Durchschnitt des Sprechers des Sprechers Render-Datenstrom Zeitstempel-Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Ursachen für ein Echo Ereignis für den Aufrufer. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des Anrufers erkannt wird. Wenn Headset verwendet wird, sollte der Wert gering sein.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des Anrufers erkannt wird. Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers; Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich-30 bis-18 dBoV sein.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers. Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf das Audiosignal des Anrufers angewendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Stellt die analogen Gain-Regler-Audiosignale für das Audiosignal dar, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Audiosignal Pegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Post-Analog-Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Verbesserung der Echo-Rückerstattung für den aufgerufenen. Die Einheit für diese Metrik ist DB. Niedrigere Werte stellen weniger Echo dar. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Störgeräusche pro fünf Minuten für die Lautsprecher-Darstellung des anrufenden. Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers. Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Abdriftrate des Mikrofon Geräts des Anrufers, relativ zu CPU-Takt.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>Dezimal (9; 2)</p></td>
<td><p>Der Durchschnitt des Sprechers des Speaker-Render-Datenstrom Zeitstempels in Millisekunden in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Ursachen für ein Echo Ereignis für den aufgerufenen. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des berufenen erkannt wird. Wenn Headset verwendet wird, sollte der Wert gering sein.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Der Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des aufgerufenen erkannt wird. Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen; Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen. Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf die Audiofunktion des berufenen angewendet wurde.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p>Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Roundtrip-Zeit von RTCP-Statistiken</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Maximale Roundtrip-Zeit für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Durchschnittliche Breitband-Netzwerk-Mos für den Anruf. Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab. Der Bereich ist 1,0 bis 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Minimale Breitband-Netzwerk-Mos für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Durchschnittliche vorhergesagte Breitband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachniveau, Geräuschpegel und Aufnahmegeräte Eigenschaften.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Minimale SendListenMOS für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Durchschnittlicher prognostizierter breitbandiger Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p>Minimale RecvListenMOS für den Anruf.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob Audio FEC für den Anruf verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Gibt die Richtung der p-Assert-identifizier Informationen an; 1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

