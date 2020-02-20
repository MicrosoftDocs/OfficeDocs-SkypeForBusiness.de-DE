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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="65267-102">tblEnumValue in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65267-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65267-103">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="65267-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="65267-104">"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65267-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="65267-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="65267-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65267-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="65267-106">Column</span></span></th>
<th><span data-ttu-id="65267-107">Typ</span><span class="sxs-lookup"><span data-stu-id="65267-107">Type</span></span></th>
<th><span data-ttu-id="65267-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65267-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65267-109">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="65267-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="65267-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="65267-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="65267-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="65267-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65267-112">AttributeID</span><span class="sxs-lookup"><span data-stu-id="65267-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="65267-113">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="65267-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="65267-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="65267-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65267-115">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="65267-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="65267-116">nvarchar  (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="65267-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="65267-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="65267-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="65267-118">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="65267-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65267-119">Spalte</span><span class="sxs-lookup"><span data-stu-id="65267-119">Column</span></span></th>
<th><span data-ttu-id="65267-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65267-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65267-121">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="65267-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="65267-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="65267-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65267-123">AttributeID</span><span class="sxs-lookup"><span data-stu-id="65267-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="65267-124">Fremdschlüssel mit Suche in der Tabelle "tblEnumAttribute.attributeID".</span><span class="sxs-lookup"><span data-stu-id="65267-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="65267-125">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="65267-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65267-126">Wert-Nr</span><span class="sxs-lookup"><span data-stu-id="65267-126">valueID</span></span></th>
<th><span data-ttu-id="65267-127">AttributeID</span><span class="sxs-lookup"><span data-stu-id="65267-127">attributeID</span></span></th>
<th><span data-ttu-id="65267-128">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="65267-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65267-129">2</span><span class="sxs-lookup"><span data-stu-id="65267-129">2</span></span></p></td>
<td><p><span data-ttu-id="65267-130">1</span><span class="sxs-lookup"><span data-stu-id="65267-130">1</span></span></p></td>
<td><p><span data-ttu-id="65267-131">Private</span><span class="sxs-lookup"><span data-stu-id="65267-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65267-132">3</span><span class="sxs-lookup"><span data-stu-id="65267-132">3</span></span></p></td>
<td><p><span data-ttu-id="65267-133">1</span><span class="sxs-lookup"><span data-stu-id="65267-133">1</span></span></p></td>
<td><p><span data-ttu-id="65267-134">scope</span><span class="sxs-lookup"><span data-stu-id="65267-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65267-135">4</span><span class="sxs-lookup"><span data-stu-id="65267-135">4</span></span></p></td>
<td><p><span data-ttu-id="65267-136">2</span><span class="sxs-lookup"><span data-stu-id="65267-136">2</span></span></p></td>
<td><p><span data-ttu-id="65267-137">normal</span><span class="sxs-lookup"><span data-stu-id="65267-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65267-138">5</span><span class="sxs-lookup"><span data-stu-id="65267-138">5</span></span></p></td>
<td><p><span data-ttu-id="65267-139">2</span><span class="sxs-lookup"><span data-stu-id="65267-139">2</span></span></p></td>
<td><p><span data-ttu-id="65267-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="65267-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65267-141">6 </span><span class="sxs-lookup"><span data-stu-id="65267-141">6</span></span></p></td>
<td><p><span data-ttu-id="65267-142">1</span><span class="sxs-lookup"><span data-stu-id="65267-142">1</span></span></p></td>
<td><p><span data-ttu-id="65267-143">Öffnen</span><span class="sxs-lookup"><span data-stu-id="65267-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="65267-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65267-144">See Also</span></span>


[<span data-ttu-id="65267-145">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65267-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

