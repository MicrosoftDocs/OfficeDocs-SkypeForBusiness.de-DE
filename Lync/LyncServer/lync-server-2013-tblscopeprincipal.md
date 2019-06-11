---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="1ccba-102">tblScopePrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ccba-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ccba-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1ccba-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1ccba-104">tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1ccba-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="1ccba-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="1ccba-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ccba-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="1ccba-106">Column</span></span></th>
<th><span data-ttu-id="1ccba-107">Typ</span><span class="sxs-lookup"><span data-stu-id="1ccba-107">Type</span></span></th>
<th><span data-ttu-id="1ccba-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ccba-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ccba-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="1ccba-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="1ccba-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1ccba-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ccba-111">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="1ccba-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ccba-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="1ccba-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="1ccba-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1ccba-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ccba-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="1ccba-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ccba-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="1ccba-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="1ccba-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1ccba-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ccba-117">"True", wenn der Typ des Bereichs "verweigern" lautet. False, wenn allow.</span><span class="sxs-lookup"><span data-stu-id="1ccba-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ccba-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1ccba-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="1ccba-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1ccba-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ccba-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="1ccba-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1ccba-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1ccba-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ccba-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="1ccba-122">Column</span></span></th>
<th><span data-ttu-id="1ccba-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ccba-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ccba-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="1ccba-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1ccba-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="1ccba-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ccba-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="1ccba-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="1ccba-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="1ccba-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ccba-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="1ccba-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="1ccba-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1ccba-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

