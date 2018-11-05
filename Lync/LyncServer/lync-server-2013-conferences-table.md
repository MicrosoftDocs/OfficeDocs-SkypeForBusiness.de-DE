---
title: 'Lync Server 2013: Conferences-Tabelle'
TOCTitle: Conferences-Tabelle
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412964(v=OCS.15)
ms:contentKeyID: 49295325
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conferences-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Der Zeitpunkt, zu dem die Konferenzanforderung vom KDS-Agent erfasst wurde. Dient nur als Primärschlüssel zur eindeutigen Identifizierung einer Konferenzinstanz.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Die ID zur Kennzeichnung der Sitzung. Gibt in Verbindung mit <strong>SessionIdTime</strong> eine Konferenzinstanz eindeutig an.*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Konferenz-URI. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Nützlich für wiederkehrende Konferenzen. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche <strong>ConferenceUri</strong> , aber eine andere <strong>ConfInstance</strong> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Der Endzeitpunkt der Konferenz.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Der Endzeitpunkt der Konferenz.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID zur Identifizierung des Pools, in dem die Konferenz aufgezeichnet wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-pools-table.md">Pools-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID zur Identifizierung des URI des Organisators dieser Konferenz. Weitere Informationen finden Sie in der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Eine Bitmaske, die Konferenzattribute enthält. Mögliche Werte sind:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetic</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Processed</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Ein internes Feld, das vom Überwachungsdienst verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


\* Für die meisten Sitzungen hat **SessionIdSeq** den Wert 1. Wenn zwei Sitzungen exakt zum gleichen Zeitpunkt beginnen, ist die **SessionIdSeq** für die eine Sitzung 1 und für die andere Sitzung 2 (usw.).

