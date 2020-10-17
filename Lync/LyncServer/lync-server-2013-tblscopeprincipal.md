---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555611"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="d042b-103">tblScopePrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d042b-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d042b-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d042b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d042b-105">In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d042b-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="d042b-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="d042b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d042b-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="d042b-107">Column</span></span></th>
<th><span data-ttu-id="d042b-108">Typ</span><span class="sxs-lookup"><span data-stu-id="d042b-108">Type</span></span></th>
<th><span data-ttu-id="d042b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d042b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d042b-110">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d042b-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d042b-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d042b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d042b-112">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="d042b-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d042b-113">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d042b-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d042b-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d042b-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d042b-115">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="d042b-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d042b-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d042b-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="d042b-117">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d042b-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d042b-118">True, wenn Bereichstyp "Verweigern" ist; False wenn "Zulassen".</span><span class="sxs-lookup"><span data-stu-id="d042b-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d042b-119">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d042b-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d042b-120">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d042b-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d042b-121">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="d042b-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d042b-122">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d042b-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d042b-123">Spalte</span><span class="sxs-lookup"><span data-stu-id="d042b-123">Column</span></span></th>
<th><span data-ttu-id="d042b-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d042b-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d042b-125">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="d042b-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d042b-126">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="d042b-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d042b-127">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d042b-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d042b-128">Fremdschlüssel mit Abfrage von Tabelle "tblNode.nodeID".</span><span class="sxs-lookup"><span data-stu-id="d042b-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d042b-129">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d042b-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d042b-130">Fremdschlüssel mit Abfrage von Tabelle "tblPrincipal.prinID".</span><span class="sxs-lookup"><span data-stu-id="d042b-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

