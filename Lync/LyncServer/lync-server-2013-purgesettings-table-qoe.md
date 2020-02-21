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
ms.openlocfilehash: 5cb0a0770136fa5b9d61f80825e49d319f872f32
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="471ef-102">PurgeSettings-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="471ef-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="471ef-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="471ef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="471ef-104">Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="471ef-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="471ef-105">Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013 Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="471ef-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="471ef-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="471ef-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="471ef-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="471ef-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="471ef-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="471ef-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="471ef-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="471ef-112">int</span><span class="sxs-lookup"><span data-stu-id="471ef-112">int</span></span></p></td>
<td><p><span data-ttu-id="471ef-113">Primary</span><span class="sxs-lookup"><span data-stu-id="471ef-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="471ef-114">Eindeutiger Bezeichner für die Auflistung der QoS-Löscheinstellungen.</span><span class="sxs-lookup"><span data-stu-id="471ef-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471ef-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="471ef-116">Bit</span><span class="sxs-lookup"><span data-stu-id="471ef-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="471ef-117">Bei Festlegung auf "true" (1) löscht Microsoft lync Server 2013 regelmäßig veraltete Datensätze aus der QoE-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="471ef-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="471ef-118">Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit.</span><span class="sxs-lookup"><span data-stu-id="471ef-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="471ef-119">Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="471ef-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="471ef-120">Der Standardwert lautet "True".</span><span class="sxs-lookup"><span data-stu-id="471ef-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471ef-121"><strong>"Keepqoedatafordays"</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="471ef-122">int</span><span class="sxs-lookup"><span data-stu-id="471ef-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="471ef-p103">Gibt das Alter der QoE-Datensätze (in Tagen) an, die aus der Datenbank gelöscht werden sollen: wenn das Löschen aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank gelöscht. Der Standardwert lautet 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="471ef-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471ef-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="471ef-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="471ef-126">int</span><span class="sxs-lookup"><span data-stu-id="471ef-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="471ef-p104">Gibt die lokale Uhrzeit an, zu der der Löschvorgang in der Datenbank stattfindet. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie als Zeitpunkt nur volle Stunden angegeben können: ein Wert von 10 (10:00) ist zulässig, aber ein Wert von 10:30 oder 10,5 (10:30) ist nicht zulässig. Der Standardwert ist 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="471ef-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

