---
title: 'Lync Server 2013: tblNode'
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615024(v=OCS.15)
ms:contentKeyID: 49294959
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblNode in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblNode" enthält die Objektstruktur (mit Kategorie oder Chatroom-Knoten) gemäß Verwaltung in der Systemsteuerung für Lync Server 2013 und den Verwaltungs-Cmdlets.

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
<td><p>nodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID (eindeutige Nummer).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Knoten-GUID.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) gilt selbst als übergeordnetes Element.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>&quot;True&quot; wenn der Knoten eine Kategorie ist.</p>
<p>&quot;False&quot; wenn der Knoten ein Chatroom ist.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Knotenname</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Knotenbeschreibung.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>&quot;True&quot; wenn Einladungen aktiviert sind.</p></li>
<li><p>&quot;False&quot; wenn Einladungen deaktiviert sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>&quot;False&quot;, wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</p></li>
<li><p>&quot;Null&quot; wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>&quot;True&quot; wenn der Chatverlauf aktiviert ist.</p></li>
<li><p>&quot;False&quot; wenn der Chatverlauf deaktiviert ist.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>&quot;Null&quot;.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>&quot;True&quot; wenn Dateiuploads zugelassen sind.</p></li>
<li><p>&quot;False&quot; wenn Dateiuploads nicht zugelassen sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>&quot;Null&quot;.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>deaktiviert</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>&quot;True&quot; wenn der Chatroom deaktiviert ist. Trifft nur auf Chatrooms zu. (&quot;False&quot; für Kategorien.)</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Verhalten (in der Tabelle &quot;EnumValue&quot; ermittelt):</p>
<ul>
<li><p>4: Normal (normale Chatrooms)</p></li>
<li><p>5: Auditorium (Auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen).</p></li>
</ul>
<p>Trifft nur auf Chatrooms zu.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Sichtbarkeit (in der Tabelle &quot;EnumValue&quot; ermittelt):</p>
<ul>
<li><p>2: Privat</p></li>
<li><p>3: Bereich</p></li>
<li><p>6: Offen</p></li>
</ul>
<p>Trifft nur auf Chatrooms zu.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>Add-In-GUID, falls diesem Chatroom ein Add-In zugeordnet ist. (Kategorien sind keine Add-Ins zugeordnet.)</p>
<p>Die Add-In-Informationen werden in der Tabelle &quot;SiopWhiteList&quot; gesucht.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der diesen Knoten erstellt hat.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel der Knotenerstellung.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der die letzte Aktualisierung dieses Knotens vorgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel der letzten Aktualisierung dieses Knotens.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt des letzten Löschvorgangs (Entfernung von Bereichen aus der Tabelle &quot;tblScopedPrincipal&quot; und Rollen aus der Tabelle &quot;tblPrincipalRole&quot;), der Auswirkungen auf diesen Knoten hatte. Wird von der internen Cache-Aktualisierung des Chatdiensts verwendet.</p></td>
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
<td><p>nodeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle &quot;tblEnumValue.valueID&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle &quot;tblEnumValue.valueID&quot;.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblNode.nodeID</strong> -Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle &quot;tblSiopWhiteList.siopId&quot;.</p></td>
</tr>
</tbody>
</table>

