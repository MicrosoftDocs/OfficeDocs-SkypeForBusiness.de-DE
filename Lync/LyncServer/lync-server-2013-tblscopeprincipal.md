---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: ab3faccea0ba914ca17c9aefcd0ea112e5b58a96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="ef432-102">tblScopePrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef432-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef432-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ef432-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ef432-104">In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ef432-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="ef432-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="ef432-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef432-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="ef432-106">Column</span></span></th>
<th><span data-ttu-id="ef432-107">Typ</span><span class="sxs-lookup"><span data-stu-id="ef432-107">Type</span></span></th>
<th><span data-ttu-id="ef432-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef432-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef432-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="ef432-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="ef432-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ef432-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef432-111">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="ef432-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef432-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="ef432-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="ef432-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="ef432-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef432-114">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="ef432-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef432-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="ef432-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="ef432-116">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ef432-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ef432-117">True, wenn Bereichstyp "Verweigern" ist; False wenn "Zulassen".</span><span class="sxs-lookup"><span data-stu-id="ef432-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef432-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="ef432-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="ef432-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ef432-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef432-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ef432-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ef432-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ef432-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef432-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="ef432-122">Column</span></span></th>
<th><span data-ttu-id="ef432-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef432-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef432-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="ef432-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="ef432-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="ef432-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef432-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="ef432-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="ef432-127">Fremdschlüssel mit Abfrage von Tabelle "tblNode.nodeID".</span><span class="sxs-lookup"><span data-stu-id="ef432-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef432-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="ef432-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="ef432-129">Fremdschlüssel mit Abfrage von Tabelle "tblPrincipal.prinID".</span><span class="sxs-lookup"><span data-stu-id="ef432-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

