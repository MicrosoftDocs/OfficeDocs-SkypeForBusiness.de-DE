---
title: PurgeSettings-Tabelle (QoE)
TOCTitle: PurgeSettings-Tabelle (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204788(v=OCS.15)
ms:contentKeyID: 49293599
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PurgeSettings-Tabelle (QoE)

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle **PurgeSettings** enthält Informationen, aus denen hervorgeht, ob (und wann) veraltete QoS-Datensätze (Quality of Experience) automatisch aus der QoE-Datenbank gelöscht werden. Sie können löschrelevante Informationen auch abrufen, in dem Sie in der Verwaltungsshell für Microsoft Lync Server 2013 den folgenden Befehl ausführen:

    Get-CsQoEConfiguration

Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutiger Bezeichner für die Auflistung der QoS-Löscheinstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Bei Festlegung auf <strong>True</strong> (1) werden veraltete Datensätze von Microsoft Lync Server 2013 regelmäßig aus der QoE-Datenbank gelöscht. Der Löschvorgang findet täglich zu dem in der Einstellung <strong>PurgeHour</strong> angegebenen Zeitpunkt statt. Bei Festlegung auf <strong>False</strong> (0) werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet <strong>True</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Gibt das Alter der QoE-Datensätze (in Tagen) an, die aus der Datenbank gelöscht werden sollen: wenn das Löschen aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank gelöscht. Der Standardwert lautet 60 Tage.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Gibt die lokale Uhrzeit an, zu der der Löschvorgang in der Datenbank stattfindet. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie als Zeitpunkt nur volle Stunden angegeben können: ein Wert von 10 (10:00) ist zulässig, aber ein Wert von 10:30 oder 10,5 (10:30) ist nicht zulässig. Der Standardwert ist 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>

