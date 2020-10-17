---
title: 'Lync Server 2013: Benutzeransicht'
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
ms.openlocfilehash: f978b6acaa1cdfdf6abf2d768c1fb679af260a63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530152"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="8bb22-102">Benutzeransicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb22-102">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb22-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8bb22-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8bb22-104">In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="8bb22-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="8bb22-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8bb22-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb22-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="8bb22-106">Column</span></span></th>
<th><span data-ttu-id="8bb22-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8bb22-107">Data Type</span></span></th>
<th><span data-ttu-id="8bb22-108">Details</span><span class="sxs-lookup"><span data-stu-id="8bb22-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb22-109">UserId</span><span class="sxs-lookup"><span data-stu-id="8bb22-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="8bb22-110">int</span><span class="sxs-lookup"><span data-stu-id="8bb22-110">int</span></span></p></td>
<td><p><span data-ttu-id="8bb22-111">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8bb22-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb22-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="8bb22-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="8bb22-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8bb22-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8bb22-114">URI des Benutzers</span><span class="sxs-lookup"><span data-stu-id="8bb22-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb22-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="8bb22-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="8bb22-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="8bb22-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8bb22-117">Mandant des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8bb22-117">Tenant of user.</span></span> <span data-ttu-id="8bb22-118">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8bb22-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb22-119">URI</span><span class="sxs-lookup"><span data-stu-id="8bb22-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="8bb22-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8bb22-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8bb22-121">Benutzer-URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="8bb22-121">Type of user URI.</span></span> <span data-ttu-id="8bb22-122">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8bb22-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

