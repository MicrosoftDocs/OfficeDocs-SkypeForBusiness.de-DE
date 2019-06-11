---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="52f83-102">tblEnumValue in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f83-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52f83-103">_**Letztes Änderungsdatum des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="52f83-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="52f83-104">tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52f83-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="52f83-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="52f83-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52f83-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="52f83-106">Column</span></span></th>
<th><span data-ttu-id="52f83-107">Typ</span><span class="sxs-lookup"><span data-stu-id="52f83-107">Type</span></span></th>
<th><span data-ttu-id="52f83-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52f83-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52f83-109">Werttyp</span><span class="sxs-lookup"><span data-stu-id="52f83-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="52f83-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="52f83-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="52f83-111">Die ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="52f83-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f83-112">AttributeID</span><span class="sxs-lookup"><span data-stu-id="52f83-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="52f83-113">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="52f83-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="52f83-114">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="52f83-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52f83-115">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="52f83-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="52f83-116">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="52f83-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="52f83-117">Der Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="52f83-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="52f83-118">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="52f83-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52f83-119">Spalte</span><span class="sxs-lookup"><span data-stu-id="52f83-119">Column</span></span></th>
<th><span data-ttu-id="52f83-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52f83-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52f83-121">Werttyp</span><span class="sxs-lookup"><span data-stu-id="52f83-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="52f83-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="52f83-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f83-123">AttributeID</span><span class="sxs-lookup"><span data-stu-id="52f83-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="52f83-124">Fremdschlüssel mit Lookup in der tblEnumAttribute. AttributeCollection-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="52f83-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="52f83-125">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="52f83-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52f83-126">Werttyp</span><span class="sxs-lookup"><span data-stu-id="52f83-126">valueID</span></span></th>
<th><span data-ttu-id="52f83-127">AttributeID</span><span class="sxs-lookup"><span data-stu-id="52f83-127">attributeID</span></span></th>
<th><span data-ttu-id="52f83-128">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="52f83-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52f83-129">2</span><span class="sxs-lookup"><span data-stu-id="52f83-129">2</span></span></p></td>
<td><p><span data-ttu-id="52f83-130">1</span><span class="sxs-lookup"><span data-stu-id="52f83-130">1</span></span></p></td>
<td><p><span data-ttu-id="52f83-131">privat</span><span class="sxs-lookup"><span data-stu-id="52f83-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f83-132">3</span><span class="sxs-lookup"><span data-stu-id="52f83-132">3</span></span></p></td>
<td><p><span data-ttu-id="52f83-133">1</span><span class="sxs-lookup"><span data-stu-id="52f83-133">1</span></span></p></td>
<td><p><span data-ttu-id="52f83-134">Bereich</span><span class="sxs-lookup"><span data-stu-id="52f83-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52f83-135">4</span><span class="sxs-lookup"><span data-stu-id="52f83-135">4</span></span></p></td>
<td><p><span data-ttu-id="52f83-136">2</span><span class="sxs-lookup"><span data-stu-id="52f83-136">2</span></span></p></td>
<td><p><span data-ttu-id="52f83-137">normal</span><span class="sxs-lookup"><span data-stu-id="52f83-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f83-138">5</span><span class="sxs-lookup"><span data-stu-id="52f83-138">5</span></span></p></td>
<td><p><span data-ttu-id="52f83-139">2</span><span class="sxs-lookup"><span data-stu-id="52f83-139">2</span></span></p></td>
<td><p><span data-ttu-id="52f83-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="52f83-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52f83-141">6</span><span class="sxs-lookup"><span data-stu-id="52f83-141">6</span></span></p></td>
<td><p><span data-ttu-id="52f83-142">1</span><span class="sxs-lookup"><span data-stu-id="52f83-142">1</span></span></p></td>
<td><p><span data-ttu-id="52f83-143">Öffnen</span><span class="sxs-lookup"><span data-stu-id="52f83-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="52f83-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52f83-144">See Also</span></span>


[<span data-ttu-id="52f83-145">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f83-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

