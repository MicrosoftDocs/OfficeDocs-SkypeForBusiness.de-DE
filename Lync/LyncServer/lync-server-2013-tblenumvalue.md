---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="355db-102">tblEnumValue in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="355db-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="355db-103">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="355db-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="355db-104">"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="355db-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="355db-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="355db-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="355db-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="355db-106">Column</span></span></th>
<th><span data-ttu-id="355db-107">Typ</span><span class="sxs-lookup"><span data-stu-id="355db-107">Type</span></span></th>
<th><span data-ttu-id="355db-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="355db-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="355db-109">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="355db-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="355db-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="355db-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="355db-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="355db-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355db-112">AttributeID</span><span class="sxs-lookup"><span data-stu-id="355db-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="355db-113">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="355db-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="355db-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="355db-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355db-115">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="355db-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="355db-116">nvarchar  (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="355db-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="355db-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="355db-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="355db-118">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="355db-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="355db-119">Spalte</span><span class="sxs-lookup"><span data-stu-id="355db-119">Column</span></span></th>
<th><span data-ttu-id="355db-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="355db-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="355db-121">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="355db-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="355db-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="355db-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355db-123">AttributeID</span><span class="sxs-lookup"><span data-stu-id="355db-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="355db-124">Fremdschlüssel mit Suche in der Tabelle "tblEnumAttribute.attributeID".</span><span class="sxs-lookup"><span data-stu-id="355db-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="355db-125">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="355db-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="355db-126">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="355db-126">valueID</span></span></th>
<th><span data-ttu-id="355db-127">AttributeID</span><span class="sxs-lookup"><span data-stu-id="355db-127">attributeID</span></span></th>
<th><span data-ttu-id="355db-128">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="355db-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="355db-129">2</span><span class="sxs-lookup"><span data-stu-id="355db-129">2</span></span></p></td>
<td><p><span data-ttu-id="355db-130">1</span><span class="sxs-lookup"><span data-stu-id="355db-130">1</span></span></p></td>
<td><p><span data-ttu-id="355db-131">Private</span><span class="sxs-lookup"><span data-stu-id="355db-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355db-132">3</span><span class="sxs-lookup"><span data-stu-id="355db-132">3</span></span></p></td>
<td><p><span data-ttu-id="355db-133">1</span><span class="sxs-lookup"><span data-stu-id="355db-133">1</span></span></p></td>
<td><p><span data-ttu-id="355db-134">scope</span><span class="sxs-lookup"><span data-stu-id="355db-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355db-135">4</span><span class="sxs-lookup"><span data-stu-id="355db-135">4</span></span></p></td>
<td><p><span data-ttu-id="355db-136">2</span><span class="sxs-lookup"><span data-stu-id="355db-136">2</span></span></p></td>
<td><p><span data-ttu-id="355db-137">normal</span><span class="sxs-lookup"><span data-stu-id="355db-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355db-138">5</span><span class="sxs-lookup"><span data-stu-id="355db-138">5</span></span></p></td>
<td><p><span data-ttu-id="355db-139">2</span><span class="sxs-lookup"><span data-stu-id="355db-139">2</span></span></p></td>
<td><p><span data-ttu-id="355db-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="355db-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355db-141">6 </span><span class="sxs-lookup"><span data-stu-id="355db-141">6</span></span></p></td>
<td><p><span data-ttu-id="355db-142">1</span><span class="sxs-lookup"><span data-stu-id="355db-142">1</span></span></p></td>
<td><p><span data-ttu-id="355db-143">Öffnen</span><span class="sxs-lookup"><span data-stu-id="355db-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="355db-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="355db-144">See Also</span></span>


[<span data-ttu-id="355db-145">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="355db-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

