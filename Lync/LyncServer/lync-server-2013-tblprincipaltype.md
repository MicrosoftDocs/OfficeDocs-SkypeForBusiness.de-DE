---
title: 'Lync Server 2013: tblPrincipalType'
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558633(v=OCS.15)
ms:contentKeyID: 49293613
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalType in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

**tblPrincipalType** enthält Prinzipaltypen zur Kategorisierung des Inhalts der **tblPrincipal** -Tabelle.

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
<td><p>ptypeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Prinzipaltyp-ID</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Beschreibung des Typs.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn es sich beim Typ um einen Benutzertyp handelt.</p></td>
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
<td><p>ptypeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


### Prinzipalwerte

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Rolle</th>
<th>Beschreibung</th>
<th>User</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Beliebig</p></td>
<td><p>Allgemeiner Prinzipal ohne bekannten Typ. Keine Verwendung in <strong>tblPrincipal</strong> -Tabelle.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Allgemeiner Prinzipal vom Typ Benutzer. Keine Verwendung in <strong>tblPrincipal</strong> -Tabelle.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Allgemeiner Prinzipal mit Gruppensemantik. Keine Verwendung in <strong>tblPrincipal</strong> -Tabelle.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Intern von Server für beständigen Chat verwendeter Prinzipal.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>User</p></td>
<td><p>Regelmäßiger Benutzer.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Active Directory-Domänendienste-Domänencontroller</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Gruppe</p></td>
<td><p>Active Directory-Sicherheitsgruppe</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Folder</p></td>
<td><p>Active Directory-Container oder Organisationseinheit</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[tblPrincipal in Lync Server 2013](lync-server-2013-tblprincipal.md)

