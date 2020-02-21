---
title: 'Lync Server 2013: tblADUpdates'
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
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="fe27d-102">tblADUpdates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe27d-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe27d-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fe27d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fe27d-104">tblADUpdates enthält Active Directory-Domänendienste Änderungen, die von den späteren Active Directory Synchronisierungs Schritten noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="fe27d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="fe27d-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="fe27d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe27d-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="fe27d-106">Column</span></span></th>
<th><span data-ttu-id="fe27d-107">Typ</span><span class="sxs-lookup"><span data-stu-id="fe27d-107">Type</span></span></th>
<th><span data-ttu-id="fe27d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe27d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe27d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fe27d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fe27d-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-111">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="fe27d-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe27d-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="fe27d-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="fe27d-113">nvarchar (384), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-114">Distinguished Name (DN) des Objekts.</span><span class="sxs-lookup"><span data-stu-id="fe27d-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe27d-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="fe27d-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="fe27d-116">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-117">TRUE, wenn sich mindestens ein Attribut des Objekts geändert hat.</span><span class="sxs-lookup"><span data-stu-id="fe27d-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe27d-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="fe27d-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="fe27d-119">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-120">TRUE, wenn sich die Mitgliedschaft geändert hat.</span><span class="sxs-lookup"><span data-stu-id="fe27d-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe27d-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="fe27d-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="fe27d-122">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-123">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe27d-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe27d-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="fe27d-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="fe27d-125">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-126">TRUE, wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="fe27d-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe27d-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="fe27d-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="fe27d-128">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fe27d-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fe27d-129">Zeitstempel für den Zeitpunkt, an dem die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe27d-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

