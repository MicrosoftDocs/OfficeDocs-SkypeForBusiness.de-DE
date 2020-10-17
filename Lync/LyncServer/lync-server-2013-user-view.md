---
title: 'Lync Server 2013: Benutzeransicht'
description: 'Lync Server 2013: Benutzeransicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558911"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="c9f94-103">Benutzeransicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9f94-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9f94-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c9f94-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c9f94-105">In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9f94-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c9f94-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c9f94-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9f94-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="c9f94-107">Column</span></span></th>
<th><span data-ttu-id="c9f94-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c9f94-108">Data Type</span></span></th>
<th><span data-ttu-id="c9f94-109">Details</span><span class="sxs-lookup"><span data-stu-id="c9f94-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9f94-110">UserId</span><span class="sxs-lookup"><span data-stu-id="c9f94-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="c9f94-111">int</span><span class="sxs-lookup"><span data-stu-id="c9f94-111">int</span></span></p></td>
<td><p><span data-ttu-id="c9f94-112">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c9f94-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9f94-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="c9f94-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="c9f94-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9f94-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9f94-115">URI des Benutzers</span><span class="sxs-lookup"><span data-stu-id="c9f94-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9f94-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c9f94-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="c9f94-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c9f94-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c9f94-118">Mandant des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c9f94-118">Tenant of user.</span></span> <span data-ttu-id="c9f94-119">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9f94-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9f94-120">URI</span><span class="sxs-lookup"><span data-stu-id="c9f94-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="c9f94-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9f94-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9f94-122">Benutzer-URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="c9f94-122">Type of user URI.</span></span> <span data-ttu-id="c9f94-123">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9f94-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

