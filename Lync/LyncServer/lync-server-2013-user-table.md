---
title: 'Lync Server 2013: user-Tabelle'
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
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="b2af2-102">Benutzertabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2af2-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2af2-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b2af2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b2af2-p101">Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b2af2-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2af2-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b2af2-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b2af2-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b2af2-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2af2-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-111">int</span><span class="sxs-lookup"><span data-stu-id="b2af2-111">int</span></span></p></td>
<td><p><span data-ttu-id="b2af2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b2af2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2af2-113">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b2af2-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2af2-114"><strong>uri</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b2af2-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b2af2-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="b2af2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="b2af2-117">URI-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b2af2-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2af2-118"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-119">int</span><span class="sxs-lookup"><span data-stu-id="b2af2-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2af2-120">1 ist ein unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="b2af2-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="b2af2-121">2 ist ein Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="b2af2-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="b2af2-122">4 ist ein Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="b2af2-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="b2af2-123">8 ist ein Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="b2af2-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2af2-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-125">int</span><span class="sxs-lookup"><span data-stu-id="b2af2-125">int</span></span></p></td>
<td><p><span data-ttu-id="b2af2-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="b2af2-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2af2-127">Mandant des Benutzers. Verweis von der tenant-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b2af2-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2af2-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-129">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b2af2-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2af2-130">Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.</span><span class="sxs-lookup"><span data-stu-id="b2af2-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2af2-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b2af2-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b2af2-132">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b2af2-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2af2-133">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="b2af2-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

