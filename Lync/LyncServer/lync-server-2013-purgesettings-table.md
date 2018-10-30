---
title: PurgeSettings-Tabelle
TOCTitle: PurgeSettings-Tabelle
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205121(v=OCS.15)
ms:contentKeyID: 49294926
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PurgeSettings-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass löschunsbezogene Informationen auch aus Verwaltungsshell für Microsoft Lync Server 2013 abgerufen werden können, indem Sie den folgenden Befehl ausführen:

    Get-CsCdrConfiguration

Administratoren sollten die Tabelle "PurgeSettings" schreibgeschützt behandeln: Änderungen an den Löscheinstellungen für Anrufdetails sollten nur mithilfe der Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) oder [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) vorgenommen werden.

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
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige Bezeichnung für die Sammlung der KDS-Löscheinstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Wenn diese Einstellung auf &quot;True&quot; (1) festgelegt ist, löscht Microsoft Lync Server 2013 regelmäßig veraltete Datensätze aus der KDS-Datenbank. Die Löschung erfolgt täglich zu der durch die Einstellung &quot;PurgeHour&quot; festgelegten Zeit. Wenn die Einstellung auf &quot;False&quot; (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet &quot;True&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Gibt das Alter von KDS-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden KDS-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Gibt das Alter von Fehlerberichtsdatensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden Fehlerberichtsdatensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Gibt die lokale Tageszeit an, zu der die Datenbanklöschung erfolgt. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Tagesstunden angeben können: der Wert 10 (für 10:00 Uhr) ist zwar zulässig, aber der Wert 10:30 oder 10.5 (für 10:30 Uhr) ist unzulässig. Der Standardwert lautet 2 (2:00 Uhr).</p></td>
</tr>
</tbody>
</table>

