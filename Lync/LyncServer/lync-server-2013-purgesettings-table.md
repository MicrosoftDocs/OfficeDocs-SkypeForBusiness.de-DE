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

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="80c2c-102">PurgeSettings-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80c2c-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80c2c-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="80c2c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="80c2c-104">Die Tabelle PurgeSettings enthält Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="80c2c-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="80c2c-105">Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="80c2c-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="80c2c-106">Administratoren sollten die PurgeSettings-Tabelle schreibgeschützt behandeln: Änderungen an den Einstellungen für das Bereinigen des Anrufdetails sollten nur mithilfe der Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) oder [setCsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="80c2c-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="80c2c-107">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="80c2c-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80c2c-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="80c2c-108">Column</span></span></th>
<th><span data-ttu-id="80c2c-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="80c2c-109">Data Type</span></span></th>
<th><span data-ttu-id="80c2c-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="80c2c-110">Key/Index</span></span></th>
<th><span data-ttu-id="80c2c-111">Details</span><span class="sxs-lookup"><span data-stu-id="80c2c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80c2c-112"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="80c2c-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="80c2c-113">int</span><span class="sxs-lookup"><span data-stu-id="80c2c-113">int</span></span></p></td>
<td><p><span data-ttu-id="80c2c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="80c2c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="80c2c-115">Eindeutiger Bezeichner für die Sammlung von CDR-Bereinigungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="80c2c-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c2c-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="80c2c-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="80c2c-117">bit</span><span class="sxs-lookup"><span data-stu-id="80c2c-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c2c-118">Bei Festlegung auf true (1) bereinigen Microsoft lync Server 2013 in regelmäßigen Abständen veraltete Datensätze aus der CDR-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="80c2c-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="80c2c-119">Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="80c2c-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="80c2c-120">Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt.</span><span class="sxs-lookup"><span data-stu-id="80c2c-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="80c2c-121">Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="80c2c-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c2c-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="80c2c-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="80c2c-123">int</span><span class="sxs-lookup"><span data-stu-id="80c2c-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c2c-124">Gibt das Alter von CDR-Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden CdR-Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="80c2c-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="80c2c-125">Der Standardwert ist 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="80c2c-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c2c-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="80c2c-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="80c2c-127">int</span><span class="sxs-lookup"><span data-stu-id="80c2c-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c2c-128">Gibt das Alter von Fehlerberichts Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden Fehlerberichts Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="80c2c-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="80c2c-129">Der Standardwert ist 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="80c2c-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c2c-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="80c2c-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="80c2c-131">int</span><span class="sxs-lookup"><span data-stu-id="80c2c-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c2c-132">Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="80c2c-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="80c2c-133">Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="80c2c-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="80c2c-134">Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="80c2c-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="80c2c-135">Der Standardwert lautet 2 (2:00 Uhr).</span><span class="sxs-lookup"><span data-stu-id="80c2c-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

