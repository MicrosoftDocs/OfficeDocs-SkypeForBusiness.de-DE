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
ms.openlocfilehash: 46516be447fa3099afe492e5edc4f4008ea5a079
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="c97ae-102">PurgeSettings-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c97ae-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c97ae-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c97ae-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c97ae-104">Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c97ae-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="c97ae-105">Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="c97ae-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="c97ae-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c97ae-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97ae-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c97ae-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c97ae-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c97ae-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97ae-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c97ae-112">int</span><span class="sxs-lookup"><span data-stu-id="c97ae-112">int</span></span></p></td>
<td><p><span data-ttu-id="c97ae-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c97ae-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c97ae-114">Eindeutiger Bezeichner für die Sammlung von QoE-Bereinigungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c97ae-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97ae-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="c97ae-116">bit</span><span class="sxs-lookup"><span data-stu-id="c97ae-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c97ae-117">Bei Festlegung auf true (1) bereinigen Microsoft lync Server 2013 in regelmäßigen Abständen veraltete Datensätze aus der QoE-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c97ae-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="c97ae-118">Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c97ae-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="c97ae-119">Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt.</span><span class="sxs-lookup"><span data-stu-id="c97ae-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="c97ae-120">Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="c97ae-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97ae-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="c97ae-122">int</span><span class="sxs-lookup"><span data-stu-id="c97ae-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c97ae-123">Gibt das Alter von QoE-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="c97ae-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="c97ae-124">Der Standardwert ist 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="c97ae-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97ae-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="c97ae-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="c97ae-126">int</span><span class="sxs-lookup"><span data-stu-id="c97ae-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c97ae-127">Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c97ae-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="c97ae-128">Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c97ae-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="c97ae-129">Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c97ae-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="c97ae-130">Der Standardwert ist 1 (1:00 am).</span><span class="sxs-lookup"><span data-stu-id="c97ae-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="c97ae-131">Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c97ae-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="c97ae-132">Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c97ae-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="c97ae-133">Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c97ae-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="c97ae-134">Der Standardwert ist 1 (1:00 am).</span><span class="sxs-lookup"><span data-stu-id="c97ae-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

