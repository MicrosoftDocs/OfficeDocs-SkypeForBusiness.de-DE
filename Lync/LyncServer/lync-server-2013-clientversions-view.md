---
title: ClientVersions-Ansicht
TOCTitle: ClientVersions-Ansicht
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49890938
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ClientVersions-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der **ClientVersions**-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert werden, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Eintrag in dieser Ansicht steht für eine Clientversion. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Für bestimmte Spalten können mehrere Einträge vorhanden sein.




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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Stellt den Benutzer-Agent dar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Clienttyp.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Die Kategorie, der der Client angehört. Beispielsweise weist der Client Conferencing_Attendant_1.0 eine ClientCategory von CAA auf.</p></td>
</tr>
</tbody>
</table>

