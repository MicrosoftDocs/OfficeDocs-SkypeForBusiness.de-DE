---
title: Session-Ansicht
TOCTitle: Session-Ansicht
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49890735
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Session-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>Datetime</p></td>
<td><p>Verweis von der MediaLine-Tabelle.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p>Korrelation</p></td>
<td><p>Varchar(max)</p></td>
<td><p>Korrelations-ID der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>Bit</p></td>
<td><p>Dialogkategorie. 0 = Abschnitt von Lync Server zum Vermittlungsserver, 1 = Abschnitt vom Vermittlungsserver zum PSTN-Gateway.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Anruf umgangen wurde.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>Int</p></td>
<td><p>Dieses Feld gibt ggf. an, warum ein Anruf nicht umgangen wurde, obwohl eine Überstimmung der Umgehungs-IDs vorlag. Für Lync Server wurde nur ein Wert definiert:</p>
<p>0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>Datetime</p></td>
<td><p>Die Startzeit des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Die Endzeit des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Anruferpools.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Angerufenen-Pools.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>P-Asserted-Identity-URI des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>P-Asserted-Identity-URI des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Endpunktname des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Endpunktname des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Benutzeragentzeichenfolge des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Benutzeragenttyp des Anrufers. Nähere Informationen finden Sie unter <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Benutzeragentkategorie des Anrufers. Nähere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE)</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Benutzeragentzeichenfolge des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Benutzeragenttyp des Angerufenen. Nähere Informationen finden Sie unter <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Benutzeragentkategorie des Angerufenen. Nähere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef-Tabelle (QoE)</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI des Angerufenen.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Priorität des Anrufs.</p></td>
</tr>
</tbody>
</table>

