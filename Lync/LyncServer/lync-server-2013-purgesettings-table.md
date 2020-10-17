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
ms.openlocfilehash: 84c75e96c9a1541a8bd56f68d5fcf9d1a8655204
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512212"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="5974b-102">PurgeSettings-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5974b-102">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5974b-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5974b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5974b-104">Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5974b-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="5974b-105">Beachten Sie, dass Bereinigungs bezogene Informationen auch in der Microsoft lync Server 2013 Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="5974b-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="5974b-106">Administratoren sollten die PurgeSettings-Tabelle als schreibgeschützt behandeln: Änderungen an den Aufräum Einstellungen für das Anruf Detail sollten nur mit den Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) oder [Satz-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="5974b-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="5974b-107">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5974b-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5974b-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="5974b-108">Column</span></span></th>
<th><span data-ttu-id="5974b-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5974b-109">Data Type</span></span></th>
<th><span data-ttu-id="5974b-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="5974b-110">Key/Index</span></span></th>
<th><span data-ttu-id="5974b-111">Details</span><span class="sxs-lookup"><span data-stu-id="5974b-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5974b-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="5974b-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="5974b-113">int</span><span class="sxs-lookup"><span data-stu-id="5974b-113">int</span></span></p></td>
<td><p><span data-ttu-id="5974b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="5974b-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="5974b-115">Eindeutige Bezeichnung für die Sammlung der KDS-Löscheinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5974b-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5974b-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="5974b-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="5974b-117">Bit</span><span class="sxs-lookup"><span data-stu-id="5974b-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5974b-118">Bei Festlegung auf "true" (1) löscht Microsoft lync Server 2013 regelmäßig veraltete Datensätze aus der KDS-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5974b-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="5974b-119">Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit.</span><span class="sxs-lookup"><span data-stu-id="5974b-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="5974b-120">Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5974b-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="5974b-121">Der Standardwert lautet "True".</span><span class="sxs-lookup"><span data-stu-id="5974b-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5974b-122"><strong>"Keepcalldetailfordays"</strong></span><span class="sxs-lookup"><span data-stu-id="5974b-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="5974b-123">int</span><span class="sxs-lookup"><span data-stu-id="5974b-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5974b-p103">Gibt das Alter von KDS-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden KDS-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="5974b-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5974b-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="5974b-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="5974b-127">int</span><span class="sxs-lookup"><span data-stu-id="5974b-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5974b-p104">Gibt das Alter von Fehlerberichtsdatensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden Fehlerberichtsdatensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="5974b-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5974b-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="5974b-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="5974b-131">int</span><span class="sxs-lookup"><span data-stu-id="5974b-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5974b-p105">Gibt die lokale Tageszeit an, zu der die Datenbanklöschung erfolgt. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Tagesstunden angeben können: der Wert 10 (für 10:00 Uhr) ist zwar zulässig, aber der Wert 10:30 oder 10.5 (für 10:30 Uhr) ist unzulässig. Der Standardwert lautet 2 (2:00 Uhr).</span><span class="sxs-lookup"><span data-stu-id="5974b-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

