---
title: 'Lync Server 2013: PurgeSettings-Tabelle (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>PurgeSettings-Tabelle (QoE) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:

    Get-CsQoEConfiguration

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
<td><p>Primary</p></td>
<td><p>Eindeutiger Bezeichner für die Sammlung von QoE-Bereinigungseinstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Bei Festlegung auf true (1) bereinigen Microsoft lync Server 2013 in regelmäßigen Abständen veraltete Datensätze aus der QoE-Datenbank. Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird. Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt. Der Standardwert lautet „True“.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt das Alter von QoE-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 am). Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 am).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

