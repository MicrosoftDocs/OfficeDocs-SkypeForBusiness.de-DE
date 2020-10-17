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
ms.openlocfilehash: 5ebf521b1cf215e2a7d5bdd30e5fa4be92334a79
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530032"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="a76f0-102">Tabelle "Users" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76f0-102">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a76f0-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a76f0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a76f0-104">Die Tabelle users ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a76f0-104">The Users table is a supporting table.</span></span> <span data-ttu-id="a76f0-105">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an anrufen oder Sitzungen beteiligt ist, die Datensätze in der Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="a76f0-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a76f0-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="a76f0-106">Column</span></span></th>
<th><span data-ttu-id="a76f0-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a76f0-107">Data Type</span></span></th>
<th><span data-ttu-id="a76f0-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="a76f0-108">Key/Index</span></span></th>
<th><span data-ttu-id="a76f0-109">Details</span><span class="sxs-lookup"><span data-stu-id="a76f0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a76f0-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a76f0-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a76f0-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a76f0-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a76f0-112">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a76f0-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a76f0-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a76f0-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a76f0-114">int</span><span class="sxs-lookup"><span data-stu-id="a76f0-114">int</span></span></p></td>
<td><p><span data-ttu-id="a76f0-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a76f0-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="a76f0-116">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a76f0-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a76f0-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a76f0-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a76f0-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a76f0-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a76f0-119">Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="a76f0-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a76f0-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="a76f0-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a76f0-121">int</span><span class="sxs-lookup"><span data-stu-id="a76f0-121">int</span></span></p></td>
<td><p><span data-ttu-id="a76f0-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="a76f0-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a76f0-123">Die Mandanten-ID dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a76f0-123">This user’s Tenant ID.</span></span> <span data-ttu-id="a76f0-124">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a76f0-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a76f0-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a76f0-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a76f0-126">int</span><span class="sxs-lookup"><span data-stu-id="a76f0-126">int</span></span></p></td>
<td><p><span data-ttu-id="a76f0-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="a76f0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a76f0-128">URI-Typ dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a76f0-128">This user’s URI type.</span></span> <span data-ttu-id="a76f0-129">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a76f0-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

