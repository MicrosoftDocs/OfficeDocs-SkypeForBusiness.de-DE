---
title: 'Lync Server 2013: user-Tabelle'
description: 'Lync Server 2013: user-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558901"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="84ec2-103">Benutzertabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ec2-103">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ec2-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="84ec2-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="84ec2-p101">Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="84ec2-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84ec2-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="84ec2-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="84ec2-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="84ec2-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84ec2-111"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-111"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-112">int</span><span class="sxs-lookup"><span data-stu-id="84ec2-112">int</span></span></p></td>
<td><p><span data-ttu-id="84ec2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="84ec2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="84ec2-114">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="84ec2-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ec2-115"><strong>uri</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-115"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="84ec2-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="84ec2-117">Eigen</span><span class="sxs-lookup"><span data-stu-id="84ec2-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="84ec2-118">URI-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="84ec2-118">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ec2-119"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-119"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-120">int</span><span class="sxs-lookup"><span data-stu-id="84ec2-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ec2-121">1 ist ein unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="84ec2-121">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="84ec2-122">2 ist ein Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="84ec2-122">2 is user URI.</span></span></p>
<p><span data-ttu-id="84ec2-123">4 ist ein Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="84ec2-123">4 is conference URI.</span></span></p>
<p><span data-ttu-id="84ec2-124">8 ist ein Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="84ec2-124">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ec2-125"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-125"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-126">int</span><span class="sxs-lookup"><span data-stu-id="84ec2-126">int</span></span></p></td>
<td><p><span data-ttu-id="84ec2-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="84ec2-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ec2-128">Mandant des Benutzers. Verweis von der tenant-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="84ec2-128">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ec2-129"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-129"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="84ec2-130">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ec2-131">Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.</span><span class="sxs-lookup"><span data-stu-id="84ec2-131">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ec2-132"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="84ec2-132"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="84ec2-133">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="84ec2-133">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ec2-134">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="84ec2-134">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

