---
title: 'Lync Server 2013: Session-Tabelle'
TOCTitle: Session-Tabelle
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398635(v=OCS.15)
ms:contentKeyID: 49294545
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Session-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz stellt eine Sitzung mit Audio oder mit Audio und Video dar. Er enthält allgemeine Informationen zu einer Sitzung. Eine Sitzung ist als ein SIP-Dialog (Session Initiation Protocol) mit Audio oder Video zwischen zwei Endpunkten definiert.


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
<td><p>Verwiesen von der <a href="lync-server-2013-dialog-table.md">Dialog-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-dialog-table.md">Dialog-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenzschlüssel. In der <a href="lync-server-2013-conference-table.md">Conference-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Korrelationsschlüssel. In der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Dialogkategorie. 0 = Abschnitt von Lync Server zum Vermittlungsserver, 1 = Abschnitt vom Vermittlungsserver zum PSTN-Gateway.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Dieses Feld gibt an (falls es vorhanden ist), warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmten. Für Lync Server ist nur ein Wert definiert.</p>
<p>0x0001 - Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Startzeitpunkt des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Endzeitpunkt des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des Anrufers. In der <a href="lync-server-2013-pool-table.md">Pool-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des Angerufenen. In der <a href="lync-server-2013-pool-table.md">Pool-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die SIP-URI in der SIP-PAI (P-Asserted-Identity) des empfangenden Endpunkts. In der <a href="lync-server-2013-user-table.md">User-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die URI des Anrufers. In der <a href="lync-server-2013-user-table.md">User-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Endpunkt des Anrufers. In der <a href="lync-server-2013-endpoint-table.md">Endpoint-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Fremd</p></td>
<td><p>Dr Benutzer-Agent des Anrufers. In der <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a> referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Priorität dieses Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Dies Spalte wird nicht mehr unterstützt und wird in Microsoft Lync Server 2013 nicht verwendet. Stattdessen werden diese Informationen pro Medienzeile angegeben. Weitere Informationen finden Sie unter <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (PAI) dient zur Übermittlung der wahren Identität des Benutzers, der den Anruf getätigt hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Endpunkt, der den Anruf empfangen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Benutzer-Agent des Benutzers, der den Anruf empfangen hat. Benutzer-Agents repräsentieren das Endpunktgerät des Clients.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>SIP-URI des Benutzers, der den Anruf empfangen hat.</p></td>
</tr>
</tbody>
</table>

