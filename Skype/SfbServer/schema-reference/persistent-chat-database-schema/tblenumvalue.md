---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295426"
---
# <a name="tblenumvalue"></a><span data-ttu-id="d8fee-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d8fee-103">tblEnumValue</span></span>
 
<span data-ttu-id="d8fee-104">tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8fee-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d8fee-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d8fee-105">**Columns**</span></span>

|<span data-ttu-id="d8fee-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d8fee-106">**Column**</span></span>|<span data-ttu-id="d8fee-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d8fee-107">**Type**</span></span>|<span data-ttu-id="d8fee-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d8fee-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8fee-109">Werttyp</span><span class="sxs-lookup"><span data-stu-id="d8fee-109">valueID</span></span>  <br/> |<span data-ttu-id="d8fee-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8fee-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d8fee-111">Die ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="d8fee-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="d8fee-112">AttributeID</span><span class="sxs-lookup"><span data-stu-id="d8fee-112">attributeID</span></span>  <br/> |<span data-ttu-id="d8fee-113">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8fee-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="d8fee-114">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="d8fee-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d8fee-115">AttributeValue</span><span class="sxs-lookup"><span data-stu-id="d8fee-115">attributeValue</span></span>  <br/> |<span data-ttu-id="d8fee-116">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8fee-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d8fee-117">Der Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="d8fee-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="d8fee-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d8fee-118">**Keys**</span></span>

|<span data-ttu-id="d8fee-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d8fee-119">**Column**</span></span>|<span data-ttu-id="d8fee-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d8fee-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8fee-121">Werttyp</span><span class="sxs-lookup"><span data-stu-id="d8fee-121">valueID</span></span>  <br/> |<span data-ttu-id="d8fee-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="d8fee-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d8fee-123">AttributeID</span><span class="sxs-lookup"><span data-stu-id="d8fee-123">attributeID</span></span>  <br/> |<span data-ttu-id="d8fee-124">Fremdschlüssel mit Lookup in der tblEnumAttribute. AttributeCollection-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d8fee-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="d8fee-125">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="d8fee-125">**Table Values**</span></span>

|<span data-ttu-id="d8fee-126">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="d8fee-126">**valueID**</span></span>|<span data-ttu-id="d8fee-127">**AttributeID**</span><span class="sxs-lookup"><span data-stu-id="d8fee-127">**attributeID**</span></span>|<span data-ttu-id="d8fee-128">**AttributeValue**</span><span class="sxs-lookup"><span data-stu-id="d8fee-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8fee-129">2</span><span class="sxs-lookup"><span data-stu-id="d8fee-129">2</span></span>  <br/> |<span data-ttu-id="d8fee-130">1</span><span class="sxs-lookup"><span data-stu-id="d8fee-130">1</span></span>  <br/> |<span data-ttu-id="d8fee-131">privat</span><span class="sxs-lookup"><span data-stu-id="d8fee-131">private</span></span>  <br/> |
|<span data-ttu-id="d8fee-132">3</span><span class="sxs-lookup"><span data-stu-id="d8fee-132">3</span></span>  <br/> |<span data-ttu-id="d8fee-133">1</span><span class="sxs-lookup"><span data-stu-id="d8fee-133">1</span></span>  <br/> |<span data-ttu-id="d8fee-134">Bereich</span><span class="sxs-lookup"><span data-stu-id="d8fee-134">scope</span></span>  <br/> |
|<span data-ttu-id="d8fee-135">4</span><span class="sxs-lookup"><span data-stu-id="d8fee-135">4</span></span>  <br/> |<span data-ttu-id="d8fee-136">2</span><span class="sxs-lookup"><span data-stu-id="d8fee-136">2</span></span>  <br/> |<span data-ttu-id="d8fee-137">normal</span><span class="sxs-lookup"><span data-stu-id="d8fee-137">normal</span></span>  <br/> |
|<span data-ttu-id="d8fee-138">5</span><span class="sxs-lookup"><span data-stu-id="d8fee-138">5</span></span>  <br/> |<span data-ttu-id="d8fee-139">2</span><span class="sxs-lookup"><span data-stu-id="d8fee-139">2</span></span>  <br/> |<span data-ttu-id="d8fee-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="d8fee-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="d8fee-141">6</span><span class="sxs-lookup"><span data-stu-id="d8fee-141">6</span></span>  <br/> |<span data-ttu-id="d8fee-142">1</span><span class="sxs-lookup"><span data-stu-id="d8fee-142">1</span></span>  <br/> |<span data-ttu-id="d8fee-143">Öffnen</span><span class="sxs-lookup"><span data-stu-id="d8fee-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d8fee-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8fee-144">See also</span></span>

[<span data-ttu-id="d8fee-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="d8fee-145">tblNode</span></span>](tblnode.md)
