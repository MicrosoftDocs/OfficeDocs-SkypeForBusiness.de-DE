---
title: UserStatistics-Tabelle
TOCTitle: UserStatistics-Tabelle
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49890950
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserStatistics-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der UserStatistics-Tabelle handelt es sich um eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über die Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt, zu dem der Benutzer zuletzt eine Konferenz organisiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt, zu dem der Benutzer zuletzt einen Anruffehler registriert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt, zu dem der Benutzer als Konferenzorganisator zuletzt einen Anruffehler registriert hat.</p></td>
</tr>
</tbody>
</table>

