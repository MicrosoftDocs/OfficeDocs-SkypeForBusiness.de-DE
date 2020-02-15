---
title: 'Lync Server 2013: UserSite-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d416017afdc36eefaffd3269359bcd0192a0c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="dadf2-102">UserSite-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadf2-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dadf2-103">_**Letztes Änderungsstand des Themas:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="dadf2-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="dadf2-p101">Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.</span><span class="sxs-lookup"><span data-stu-id="dadf2-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dadf2-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dadf2-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dadf2-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dadf2-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dadf2-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dadf2-111">int</span><span class="sxs-lookup"><span data-stu-id="dadf2-111">int</span></span></p></td>
<td><p><span data-ttu-id="dadf2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="dadf2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="dadf2-113">Eindeutige Zahl, die den Benutzerstandort identifiziert.</span><span class="sxs-lookup"><span data-stu-id="dadf2-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dadf2-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="dadf2-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="dadf2-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dadf2-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="dadf2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="dadf2-117">Name des Benutzerstandorts.</span><span class="sxs-lookup"><span data-stu-id="dadf2-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dadf2-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="dadf2-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dadf2-119">int</span><span class="sxs-lookup"><span data-stu-id="dadf2-119">int</span></span></p></td>
<td><p><span data-ttu-id="dadf2-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="dadf2-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dadf2-121">Referenziert aus der <a href="lync-server-2013-region-table.md">Region-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dadf2-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

