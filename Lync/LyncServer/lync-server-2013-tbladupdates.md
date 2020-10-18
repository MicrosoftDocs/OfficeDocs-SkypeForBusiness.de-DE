---
title: 'Lync Server 2013: tblADUpdates'
description: 'Lync Server 2013: tblADUpdates.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573681"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="bb1f6-103">tblADUpdates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1f6-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb1f6-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bb1f6-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bb1f6-105">tblADUpdates enthält Active Directory-Domänendienste Änderungen, die von den späteren Active Directory Synchronisierungs Schritten noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="bb1f6-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="bb1f6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb1f6-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="bb1f6-107">Column</span></span></th>
<th><span data-ttu-id="bb1f6-108">Typ</span><span class="sxs-lookup"><span data-stu-id="bb1f6-108">Type</span></span></th>
<th><span data-ttu-id="bb1f6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb1f6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb1f6-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bb1f6-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-111">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-112">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb1f6-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="bb1f6-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-114">nvarchar (384), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-115">Distinguished Name (DN) des Objekts.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb1f6-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="bb1f6-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-117">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-118">TRUE, wenn sich mindestens ein Attribut des Objekts geändert hat.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb1f6-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="bb1f6-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-120">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-121">TRUE, wenn sich die Mitgliedschaft geändert hat.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb1f6-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="bb1f6-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-123">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-124">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb1f6-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="bb1f6-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-126">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-127">TRUE, wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb1f6-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="bb1f6-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-129">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb1f6-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bb1f6-130">Zeitstempel für den Zeitpunkt, an dem die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

