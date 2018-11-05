---
title: 'Lync Server 2013: tblPrincipalAffiliations'
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558642(v=OCS.15)
ms:contentKeyID: 49293866
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalAffiliations in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblPrincipalAffiliations enthält die Prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.

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
<td><p>principalID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des zugeordneten Prinzipals.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, die für die Zuordnung steht. Jeder Prinzipal (ausgenommen <strong>system-user-types</strong> ) verfügt auch über eine Selbstzuordnung.</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Index. Der Wert für Selbstzuordnungen ist -1. Für andere Zuordnungen steigt der Wert sequenziell von 1 innerhalb jedes &lt;principalID, affiliationId&gt;-Buckets.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal, der die letzte Aktualisierung durchführte. Der Wert ist in der Regel 1, was der Active Directory-Synchronisierung entspricht.</p></td>
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
<th>Spalten</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>

