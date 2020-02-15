---
title: 'Lync Server 2013: users-Tabelle'
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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="9991e-102">Tabelle "Users" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9991e-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9991e-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9991e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9991e-104">Die Tabelle users ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9991e-104">The Users table is a supporting table.</span></span> <span data-ttu-id="9991e-105">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an anrufen oder Sitzungen beteiligt ist, die Datensätze in der Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="9991e-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9991e-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="9991e-106">Column</span></span></th>
<th><span data-ttu-id="9991e-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9991e-107">Data Type</span></span></th>
<th><span data-ttu-id="9991e-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="9991e-108">Key/Index</span></span></th>
<th><span data-ttu-id="9991e-109">Details</span><span class="sxs-lookup"><span data-stu-id="9991e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9991e-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="9991e-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="9991e-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="9991e-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9991e-112">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="9991e-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9991e-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9991e-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9991e-114">int</span><span class="sxs-lookup"><span data-stu-id="9991e-114">int</span></span></p></td>
<td><p><span data-ttu-id="9991e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="9991e-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="9991e-116">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9991e-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9991e-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9991e-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9991e-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9991e-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9991e-119">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="9991e-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9991e-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="9991e-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="9991e-121">int</span><span class="sxs-lookup"><span data-stu-id="9991e-121">int</span></span></p></td>
<td><p><span data-ttu-id="9991e-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="9991e-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9991e-123">Die Mandanten-ID dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9991e-123">This user’s Tenant ID.</span></span> <span data-ttu-id="9991e-124">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9991e-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9991e-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9991e-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9991e-126">int</span><span class="sxs-lookup"><span data-stu-id="9991e-126">int</span></span></p></td>
<td><p><span data-ttu-id="9991e-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="9991e-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9991e-128">URI-Typ dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9991e-128">This user’s URI type.</span></span> <span data-ttu-id="9991e-129">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9991e-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

