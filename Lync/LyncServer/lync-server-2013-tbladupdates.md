---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="faf35-102">tblADUpdates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf35-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faf35-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="faf35-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="faf35-104">tblADUpdates enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="faf35-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="faf35-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="faf35-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faf35-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="faf35-106">Column</span></span></th>
<th><span data-ttu-id="faf35-107">Typ</span><span class="sxs-lookup"><span data-stu-id="faf35-107">Type</span></span></th>
<th><span data-ttu-id="faf35-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf35-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faf35-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="faf35-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="faf35-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-111">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="faf35-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf35-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="faf35-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="faf35-113">nvarchar (384); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-114">Distinguished Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="faf35-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf35-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="faf35-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="faf35-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-117">"True", wenn mindestens ein Attribut des Objekts geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="faf35-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf35-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="faf35-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="faf35-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-120">"True", wenn die Mitgliedschaft geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="faf35-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf35-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="faf35-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="faf35-122">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-123">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="faf35-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faf35-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="faf35-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="faf35-125">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-126">"True", wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="faf35-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faf35-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="faf35-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="faf35-128">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="faf35-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="faf35-129">Zeitstempel, wann die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="faf35-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

