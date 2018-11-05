---
title: 'Lync Server 2013: tblPreference'
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615052(v=OCS.15)
ms:contentKeyID: 49295964
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPreference in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

**tblPreference** enthält die Clientvoreinstellungen der Benutzer. Diese Tabelle wird allgemein von Clients mit einer früheren Version als Lync 2013 verwendet.

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
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Bezeichnung mit einem Format wie z. B. &lt;SIP-URI des Benutzers&gt;|username.&lt;Voreinstellung&gt;.</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Fortlaufende Zahl (pro Bezeichnung) für die Versionsverwaltung.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Verschlüsselter Inhalt.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der die Voreinstellung aktualisiert hat.</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

