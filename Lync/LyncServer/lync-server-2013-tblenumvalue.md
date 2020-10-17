---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571371"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="7e2c1-103">tblEnumValue in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e2c1-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e2c1-104">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="7e2c1-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="7e2c1-105">"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e2c1-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="7e2c1-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="7e2c1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e2c1-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="7e2c1-107">Column</span></span></th>
<th><span data-ttu-id="7e2c1-108">Typ</span><span class="sxs-lookup"><span data-stu-id="7e2c1-108">Type</span></span></th>
<th><span data-ttu-id="7e2c1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e2c1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-110">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="7e2c1-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-111">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7e2c1-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-112">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="7e2c1-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e2c1-113">AttributeID</span><span class="sxs-lookup"><span data-stu-id="7e2c1-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-114">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7e2c1-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-115">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="7e2c1-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-116">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="7e2c1-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-117">nvarchar  (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7e2c1-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-118">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="7e2c1-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7e2c1-119">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7e2c1-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e2c1-120">Spalte</span><span class="sxs-lookup"><span data-stu-id="7e2c1-120">Column</span></span></th>
<th><span data-ttu-id="7e2c1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e2c1-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-122">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="7e2c1-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7e2c1-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e2c1-124">AttributeID</span><span class="sxs-lookup"><span data-stu-id="7e2c1-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-125">Fremdschlüssel mit Suche in der Tabelle "tblEnumAttribute.attributeID".</span><span class="sxs-lookup"><span data-stu-id="7e2c1-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="7e2c1-126">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="7e2c1-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e2c1-127">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="7e2c1-127">valueID</span></span></th>
<th><span data-ttu-id="7e2c1-128">AttributeID</span><span class="sxs-lookup"><span data-stu-id="7e2c1-128">attributeID</span></span></th>
<th><span data-ttu-id="7e2c1-129">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="7e2c1-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-130">2</span><span class="sxs-lookup"><span data-stu-id="7e2c1-130">2</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-131">1</span><span class="sxs-lookup"><span data-stu-id="7e2c1-131">1</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-132">Private</span><span class="sxs-lookup"><span data-stu-id="7e2c1-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e2c1-133">3</span><span class="sxs-lookup"><span data-stu-id="7e2c1-133">3</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-134">1</span><span class="sxs-lookup"><span data-stu-id="7e2c1-134">1</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-135">Bereich</span><span class="sxs-lookup"><span data-stu-id="7e2c1-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-136">4 </span><span class="sxs-lookup"><span data-stu-id="7e2c1-136">4</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-137">2</span><span class="sxs-lookup"><span data-stu-id="7e2c1-137">2</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-138">normal</span><span class="sxs-lookup"><span data-stu-id="7e2c1-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e2c1-139">5 </span><span class="sxs-lookup"><span data-stu-id="7e2c1-139">5</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-140">2</span><span class="sxs-lookup"><span data-stu-id="7e2c1-140">2</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-141">Auditorium</span><span class="sxs-lookup"><span data-stu-id="7e2c1-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e2c1-142">6 </span><span class="sxs-lookup"><span data-stu-id="7e2c1-142">6</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-143">1</span><span class="sxs-lookup"><span data-stu-id="7e2c1-143">1</span></span></p></td>
<td><p><span data-ttu-id="7e2c1-144">Öffnen</span><span class="sxs-lookup"><span data-stu-id="7e2c1-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7e2c1-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e2c1-145">See Also</span></span>


[<span data-ttu-id="7e2c1-146">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e2c1-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

