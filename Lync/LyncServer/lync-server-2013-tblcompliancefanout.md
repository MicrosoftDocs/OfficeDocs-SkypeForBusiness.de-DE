---
title: 'Lync Server 2013: tblComplianceFanout'
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615050(v=OCS.15)
ms:contentKeyID: 49295917
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceFanout in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblComplianceFanout enthält alle Server, die ein Kompatibilitätsereignis verarbeitet haben.

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>int</p></td>
<td><p>Ereignis-ID</p></td>
</tr>
<tr class="even">
<td><p>fanoutServerID</p></td>
<td><p>int</p></td>
<td><p>Serveridentität (entsprechend zur tblServerIdentity.serverID-Tabelle).</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblComplianceData.cmplEventID-Tabelle.</p></td>
</tr>
</tbody>
</table>

