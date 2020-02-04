---
title: 'Lync Server 2013: Liste von QoE-Tabellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Liste von QoE-Tabellen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Das Datenbankschema besteht aus den folgenden Tabellen.

**Unterstützende Tabellen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabelle</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">CodecDescription-Tabelle in lync Server 2013</a></p></td>
<td><p>Ordnet eindeutige Codec-IDs dem zugehörigen Codec zu.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle in lync Server 2013</a></p></td>
<td><p>Ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle in lync Server 2013</a></p></td>
<td><p>Ordnet Netzwerkverbindungstypen den Netzwerk Verbindungs Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings-Tabelle (QoE) in lync Server 2013</a></p></td>
<td><p>Speichert Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">TraceRoute-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Routinginformationen für Anrufe.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE) in lync Server 2013</a></p></td>
<td><p>Ordnet die Bezeichner des Benutzer-Agents den beschreibenden Namen des Agents zu.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert optimale und akzeptable Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert SIP-Benutzer-Agent (Session Initiation Protocol)-Zeichenfolgen und UA-Typen, die in Audio-und Videositzungen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">User-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Benutzer-, Konferenz-und Telefon-URIs, die in Audio-und Videositzungen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Endpoint-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert FQDN-Computernamen von Endpunkten, die an Audio-und Videositzungen teilnehmen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Pool-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Namen der Pools, zu denen Metrikdaten gehören.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Aufnahmegeräte und rendergeräte, die in Audio-und Videogesprächen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den Treiber für das Aufnahmegerät und das Render-Gerät, die in Audio-und Videoanrufen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Conference-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Konferenz-URIs für Konferenzszenarien oder Dialogfelder für andere Szenarien.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert CorrelationId für PSTN-Anrufe.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den in Audio-und Videoanrufen verwendeten Codec.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die in Audio-und Videoanrufen verwendete Bandbreiten Quelle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Mac-Adresse der Endpunkte, die an Audio-und Videositzungen teilnehmen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Dialog-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Dialog-ID für Audio-und Videositzungen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Region-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die in der NCS-Einstellung definierte netzwerkregion.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">UserSite-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die in der NCS-Einstellung definierte Netzwerk Website.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Subnet-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert das in der NCS-Einstellung definierte Subnetz.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den in der NCS-Einstellung definierten Link "Region".</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink-Tabelle</a></p></td>
<td><p>Speichert die in der NCS-Einstellung definierten Netzwerkstandort Links.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert das Subnetz des Endpunkts, der an einer Audio-und Videositzung teilnimmt.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Servertabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den FQDN oder die IP-Adresse des Servers, den das Medium durchläuft.</p></td>
</tr>
</tbody>
</table>


**Tabellen für Metrikdaten**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabelle</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Qualität der Erfahrungswerte für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Metrik für die Qualität der Erfahrung für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Session-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert allgemeine Informationen zu einer Audio-oder Audio/Video-Sitzung. Eine Sitzung ist als Audio-oder Video-SIP-Dialogfeld zwischen zwei Endpunkten definiert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu jeder medienzeile in einer Sitzung. Eine medienzeile ist eine Sammlung von einem oder mehreren Audio-und Videodatenströmen. In der Regel besitzt eine einzelne medienzeile zwei Streams, entweder Audio oder Video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">AudioStream-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Qualitäts Metriken für Audio-Medien für jeden Audiostream in der Medien Linie.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">AudioSignal-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Qualitäts Metriken für Audiomedien in der medienzeile. Dazu gehören akustische Echo Unterdrückungs-und AGC-Metriken (Automatic Gain Control).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">VideoStream-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Qualitäts Metriken für Video Medien für jeden Audiostream in der Medien Linie.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die von der Client Veranstaltung gesammelten Qualitäts Metriken für Audio-Medien.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Qualitäts Metriken für Video Medien, die vom Clientereignis gesammelt wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData-Tabelle</strong></p></td>
<td><p>Speichert Diagnosedaten, die nur für die interne Verwendung vorgesehen sind.</p></td>
</tr>
</tbody>
</table>


**Tabellen für Zusammenfassungsdaten**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabelle</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary-Tabelle</strong></p></td>
<td><p>Speichert Zusammenfassungsdaten für die Server, diese Daten werden nur für QoE-Berichte (Quality of Experience) verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary-Tabelle</strong></p></td>
<td><p>Speichert Zusammenfassungsdaten für Benutzer, diese Daten werden nur für QoE-Berichte verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary-Tabelle</strong></p></td>
<td><p>Speichern von Zusammenfassungsdaten für Anruftypen werden diese Daten nur für QoE-Berichte verwendet.</p></td>
</tr>
</tbody>
</table>


**Tabellen für die interne Verwendung durch Monitoring Server**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabelle</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frontend-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aufgaben Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dberrormessage</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitzonen</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mandantentabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

