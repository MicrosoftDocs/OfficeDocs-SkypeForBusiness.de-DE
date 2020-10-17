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
ms.openlocfilehash: b8263369e9224c4a3aeb20bbb664392fbe3ba7c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536282"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="acdec-102">tblScopePrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acdec-102">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acdec-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="acdec-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="acdec-104">In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="acdec-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="acdec-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="acdec-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acdec-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="acdec-106">Column</span></span></th>
<th><span data-ttu-id="acdec-107">Typ</span><span class="sxs-lookup"><span data-stu-id="acdec-107">Type</span></span></th>
<th><span data-ttu-id="acdec-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acdec-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acdec-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="acdec-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="acdec-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="acdec-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="acdec-111">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="acdec-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acdec-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="acdec-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="acdec-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="acdec-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="acdec-114">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="acdec-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acdec-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="acdec-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="acdec-116">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="acdec-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="acdec-117">True, wenn Bereichstyp "Verweigern" ist; False wenn "Zulassen".</span><span class="sxs-lookup"><span data-stu-id="acdec-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acdec-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="acdec-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="acdec-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="acdec-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="acdec-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="acdec-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="acdec-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="acdec-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acdec-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="acdec-122">Column</span></span></th>
<th><span data-ttu-id="acdec-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acdec-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acdec-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="acdec-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="acdec-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="acdec-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acdec-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="acdec-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="acdec-127">Fremdschlüssel mit Abfrage von Tabelle "tblNode.nodeID".</span><span class="sxs-lookup"><span data-stu-id="acdec-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acdec-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="acdec-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="acdec-129">Fremdschlüssel mit Abfrage von Tabelle "tblPrincipal.prinID".</span><span class="sxs-lookup"><span data-stu-id="acdec-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

