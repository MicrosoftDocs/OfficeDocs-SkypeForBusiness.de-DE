---
title: 'Lync Server 2013: tblLastInviteId'
description: 'Lync Server 2013: tblLastInviteId.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5a13cfc7edc29ea20c95f7f4d587b0cfb84eb73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547541"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="04b9a-103">tblLastInviteId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04b9a-103">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04b9a-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="04b9a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="04b9a-105">"tblLastInviteId" enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="04b9a-105">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="04b9a-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="04b9a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04b9a-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="04b9a-107">Column</span></span></th>
<th><span data-ttu-id="04b9a-108">Typ</span><span class="sxs-lookup"><span data-stu-id="04b9a-108">Type</span></span></th>
<th><span data-ttu-id="04b9a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04b9a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04b9a-110">prinID</span><span class="sxs-lookup"><span data-stu-id="04b9a-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="04b9a-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="04b9a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04b9a-112">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="04b9a-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04b9a-113">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="04b9a-113">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="04b9a-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="04b9a-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04b9a-115">Zuletzt verwendete INVITE-ID.</span><span class="sxs-lookup"><span data-stu-id="04b9a-115">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="04b9a-116">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="04b9a-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04b9a-117">Spalte</span><span class="sxs-lookup"><span data-stu-id="04b9a-117">Column</span></span></th>
<th><span data-ttu-id="04b9a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04b9a-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04b9a-119">prinID</span><span class="sxs-lookup"><span data-stu-id="04b9a-119">prinID</span></span></p></td>
<td><p><span data-ttu-id="04b9a-120">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="04b9a-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04b9a-121">prinID</span><span class="sxs-lookup"><span data-stu-id="04b9a-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="04b9a-122">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04b9a-122">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="04b9a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04b9a-123">See Also</span></span>


[<span data-ttu-id="04b9a-124">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04b9a-124">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

