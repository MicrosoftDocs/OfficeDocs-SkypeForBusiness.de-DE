---
title: 'Lync Server 2013: PurgeSettings-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>PurgeSettings-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Die Tabelle PurgeSettings enthält Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:

    Get-CsCdrConfiguration

Administratoren sollten die PurgeSettings-Tabelle schreibgeschützt behandeln: Änderungen an den Einstellungen für das Bereinigen des Anrufdetails sollten nur mithilfe der Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) oder [setCsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) erfolgen.

Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>Primary</p></td>
<td><p>Eindeutiger Bezeichner für die Sammlung von CDR-Bereinigungseinstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Bei Festlegung auf true (1) bereinigen Microsoft lync Server 2013 in regelmäßigen Abständen veraltete Datensätze aus der CDR-Datenbank. Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird. Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt. Der Standardwert lautet „True“.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt das Alter von CDR-Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden CdR-Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt das Alter von Fehlerberichts Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden Fehlerberichts Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert lautet 2 (2:00 Uhr).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

