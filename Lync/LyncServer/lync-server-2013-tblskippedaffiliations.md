---
title: 'Lync Server 2013: tblSkippedAffiliations'
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558611(v=OCS.15)
ms:contentKeyID: 49293131
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSkippedAffiliations in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"SkippedAffiliations" enthält die Zuordnungen, die aus einem beliebigen Grund (in der Regel aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten.

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
<td><p>prinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Zeichenfolge, die die Zuordnung identifiziert.</p>
<p>Das Format lautet: GUID: <em>{0}</em> URI: <em>{1}</em> &gt; ID: <em>{2}</em></p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer <strong>1</strong> (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</p></td>
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
<th>Spalte(n)</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>

