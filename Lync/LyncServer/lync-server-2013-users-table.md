---
title: 'Lync Server 2013: users-Tabelle'
description: 'Lync Server 2013: users-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548631"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="d433e-103">Tabelle "Users" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d433e-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d433e-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d433e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d433e-105">Die Tabelle users ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d433e-105">The Users table is a supporting table.</span></span> <span data-ttu-id="d433e-106">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an anrufen oder Sitzungen beteiligt ist, die Datensätze in der Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="d433e-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d433e-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="d433e-107">Column</span></span></th>
<th><span data-ttu-id="d433e-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d433e-108">Data Type</span></span></th>
<th><span data-ttu-id="d433e-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="d433e-109">Key/Index</span></span></th>
<th><span data-ttu-id="d433e-110">Details</span><span class="sxs-lookup"><span data-stu-id="d433e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d433e-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d433e-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d433e-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d433e-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d433e-113">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d433e-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d433e-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d433e-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d433e-115">int</span><span class="sxs-lookup"><span data-stu-id="d433e-115">int</span></span></p></td>
<td><p><span data-ttu-id="d433e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d433e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d433e-117">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d433e-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d433e-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="d433e-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d433e-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d433e-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d433e-120">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="d433e-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d433e-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="d433e-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="d433e-122">int</span><span class="sxs-lookup"><span data-stu-id="d433e-122">int</span></span></p></td>
<td><p><span data-ttu-id="d433e-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="d433e-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d433e-124">Die Mandanten-ID dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d433e-124">This user’s Tenant ID.</span></span> <span data-ttu-id="d433e-125">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d433e-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d433e-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d433e-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d433e-127">int</span><span class="sxs-lookup"><span data-stu-id="d433e-127">int</span></span></p></td>
<td><p><span data-ttu-id="d433e-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="d433e-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d433e-129">URI-Typ dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d433e-129">This user’s URI type.</span></span> <span data-ttu-id="d433e-130">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d433e-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

