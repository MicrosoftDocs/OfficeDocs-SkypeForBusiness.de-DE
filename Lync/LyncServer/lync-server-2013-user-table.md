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
ms.openlocfilehash: ed3f2372621b2b098a6b235d1bdc151ddac054bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530162"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="545f7-102">Benutzertabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="545f7-102">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="545f7-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="545f7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="545f7-p101">Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="545f7-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="545f7-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="545f7-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="545f7-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="545f7-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="545f7-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-111">int</span><span class="sxs-lookup"><span data-stu-id="545f7-111">int</span></span></p></td>
<td><p><span data-ttu-id="545f7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="545f7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="545f7-113">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="545f7-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="545f7-114"><strong>uri</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="545f7-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="545f7-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="545f7-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="545f7-117">URI-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="545f7-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="545f7-118"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-119">int</span><span class="sxs-lookup"><span data-stu-id="545f7-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="545f7-120">1 ist ein unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="545f7-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="545f7-121">2 ist ein Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="545f7-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="545f7-122">4 ist ein Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="545f7-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="545f7-123">8 ist ein Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="545f7-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="545f7-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-125">int</span><span class="sxs-lookup"><span data-stu-id="545f7-125">int</span></span></p></td>
<td><p><span data-ttu-id="545f7-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="545f7-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="545f7-127">Mandant des Benutzers. Verweis von der tenant-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="545f7-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="545f7-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-129">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="545f7-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="545f7-130">Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.</span><span class="sxs-lookup"><span data-stu-id="545f7-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="545f7-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="545f7-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="545f7-132">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="545f7-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="545f7-133">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="545f7-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

