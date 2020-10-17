---
title: 'Lync Server 2013: PurgeSettings-Tabelle (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac236e08f79adbe1ec7cbe92ea04405de46d0055
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512222"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>PurgeSettings-Tabelle (QoE) in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013 Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:

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
<td><p>Eindeutiger Bezeichner für die Auflistung der QoS-Löscheinstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Bei Festlegung auf "true" (1) löscht Microsoft lync Server 2013 regelmäßig veraltete Datensätze aus der QoE-Datenbank. Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit. Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet "True".</p></td>
</tr>
<tr class="odd">
<td><p><strong>"Keepqoedatafordays"</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt das Alter der QoE-Datensätze (in Tagen) an, die aus der Datenbank gelöscht werden sollen: wenn das Löschen aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank gelöscht. Der Standardwert lautet 60 Tage.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gibt die lokale Uhrzeit an, zu der der Löschvorgang in der Datenbank stattfindet. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie als Zeitpunkt nur volle Stunden angegeben können: ein Wert von 10 (10:00) ist zulässig, aber ein Wert von 10:30 oder 10,5 (10:30) ist nicht zulässig. Der Standardwert ist 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

