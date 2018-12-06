---
title: 'Lync Server 2013: Liste von QoE-Tabellen'
TOCTitle: Liste von QoE-Tabellen
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398236(v=OCS.15)
ms:contentKeyID: 49293303
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste von QoE-Tabellen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Datenbankschema besteht aus den folgenden Tabellen.

**Unterstützungstabellen**


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
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabelle &quot;AppSharingMetricsThreshold&quot;</a></p></td>
<td><p>Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die bei der Anwendungsfreigabe verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">CodecDescription-Tabelle in Lync Server 2013</a></p></td>
<td><p>Ordnet eindeutige Codec-IDs dem entsprechenden Codec zu.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a></p></td>
<td><p>Ordnet IP-Adressen den eindeutigen IP-Adress-IDs zu, die anderswo in der QoE (Quality of Experience)-Datenbank verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail-Tabelle</a></p></td>
<td><p>Ordnet Netzwerkverbindungstypen den Netzwerkverbindungs-IDs zu, die anderswo in der QoE (Quality of Experience)-Datenbank verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings-Tabelle (QoE)</a></p></td>
<td><p>Speichert Informationen, mit denen angegeben wird, ob (und wann) veraltete QoE-(Quality of Experience)-Kommunikationsdatensätze automatisch aus der QoE-Datenbank gelöscht werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">TraceRoute-Tabelle</a></p></td>
<td><p>Speichert Routinginformationen für Anrufe.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE)</a></p></td>
<td><p>Ordnet Benutzeragent-IDs den beschreibenden Namen von Agents zu.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold-Tabelle</a></p></td>
<td><p>Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert in Audio- und Videositzungen verwendete Session Initiation-Protokolle (SIP), Benutzer-Agent-Zeichenfolgen (UA) und UA-Typen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">User-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert in Audio- und Videositzungen verwendete Benutzer-, Konferenz- und Telefon-URIs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Endpoint-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert FQDN-Computernamen von Endpunkten, die an Audio- und Videositzungen teilnehmen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Pool-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Namen von Pools, zu denen metrische Daten gehören.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Device-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert bei Audio-/Videoanrufen verwendete Aufnahme- und Darstellungsgeräte.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">DeviceDriver-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den Treiber für das Aufnahmegerät und das Darstellungsgerät, die bei Audio-/Videoanrufen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Conference-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Konferenz-URIs für Konferenzszenarien oder die Dialog-ID für andere Szenarien.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Korrelations-ID für PSTN-Anrufe.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die bei Audio-/Videoanrufen verwendeten Codecs.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die bei Audio-/Videoanrufen verwendete Bandbreitenquelle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">MacAddress-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die MAC-Adresse der Endpunkte, die an Audio- und Videositzungen teilnehmen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Dialog-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Dialog-ID von Audio- und Videositzungen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Region-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die in der NCS-Einstellung festgelegte Netzwerkregion.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">UserSite-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den in der NCS-Einstellung festgelegten Netzwerkstandort.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Subnet-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert das in der NCS-Einstellung festgelegte Subnetz.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den in der NCS-Einstellung festgelegten Regionslink.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink-Tabelle</a></p></td>
<td><p>Speichert die in der NCS-Einstellung festgelegten Netzwerkstandortverknüpfungen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert das Subnetz des Endpunkts, der an einer Audio- und Videositzung teilnimmt.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Servertabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den FQDN oder die IP-Adresse des Servers, über den der Mediendatenverkehr erfolgt.</p></td>
</tr>
</tbody>
</table>


**Tabellen für metrische Daten**


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
<td><p><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream-Tabelle</a></p></td>
<td><p>Speichert QoE (Quality of Experience)-Metriken für die Netzwerkdatenströme, die bei der Anwendungsfreigabe verwendet werden. QoE (Quality of Experience)-Metriken für die Netzwerkdatenströme, die bei der Anwendungsfreigabe verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Session-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert allgemeine Informationen zu einer Audio- oder Videositzung. Eine Sitzung ist ein Audio- oder Video-SIP-Dialog zwischen zwei Endpunkten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu jeder Medienzeile in einer Sitzung. Eine Medienzeile ist eine Sammlung von mindestens einem Audio- und Videostream. In der Regel enthält eine einzelne Medienzeile zwei Streams, entweder Audio oder Video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">AudioStream-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Audiomedien-Qualitätsmetriken für jeden Audiostream in der Medienzeile.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">AudioSignal-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Audiomedien-Qualitätsmetriken in der Medienzeile, einschließlich Metriken zu Echounterdrückung (AEC) und eingebauten Verstärkern (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">VideoStream-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Videomedien-Qualitätsmetriken für jeden Audiostream in der Medienzeile.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert aus dem Clientereignis empfangene Audiomedien-Qualitätsmetriken.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert aus dem Clientereignis empfangene Videomedien-Qualitätsmetriken.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData-Tabelle</strong></p></td>
<td><p>Speichert Diagnosedaten ausschließlich für die interne Verwendung.</p></td>
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
<td><p>Speichert Zusammenfassungsdaten für die Server. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary-Tabelle</strong></p></td>
<td><p>Speichert Zusammenfassungsdaten für Benutzer. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary-Tabelle</strong></p></td>
<td><p>Speichert Zusammenfassungsdaten für Anruftypen. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.</p></td>
</tr>
</tbody>
</table>


**Tabellen des Monitoring Servers für die interne Verwendung**


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
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aufgabentabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tenant-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
</tbody>
</table>

