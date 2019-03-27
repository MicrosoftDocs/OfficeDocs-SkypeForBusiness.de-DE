---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: "\"TblEnumValue\" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden."
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881169"
---
# <a name="tblenumvalue"></a><span data-ttu-id="48d39-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="48d39-103">tblEnumValue</span></span>
 
<span data-ttu-id="48d39-104">"TblEnumValue" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48d39-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="48d39-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="48d39-105">**Columns**</span></span>

|<span data-ttu-id="48d39-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48d39-106">**Column**</span></span>|<span data-ttu-id="48d39-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="48d39-107">**Type**</span></span>|<span data-ttu-id="48d39-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48d39-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48d39-109">valueID</span><span class="sxs-lookup"><span data-stu-id="48d39-109">valueID</span></span>  <br/> |<span data-ttu-id="48d39-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="48d39-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="48d39-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="48d39-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="48d39-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="48d39-112">attributeID</span></span>  <br/> |<span data-ttu-id="48d39-113">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="48d39-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="48d39-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="48d39-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="48d39-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="48d39-115">attributeValue</span></span>  <br/> |<span data-ttu-id="48d39-116">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="48d39-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="48d39-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="48d39-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="48d39-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="48d39-118">**Keys**</span></span>

|<span data-ttu-id="48d39-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48d39-119">**Column**</span></span>|<span data-ttu-id="48d39-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48d39-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48d39-121">valueID</span><span class="sxs-lookup"><span data-stu-id="48d39-121">valueID</span></span>  <br/> |<span data-ttu-id="48d39-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="48d39-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="48d39-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="48d39-123">attributeID</span></span>  <br/> |<span data-ttu-id="48d39-124">Fremdschlüssel mit Abfrage der Tabelle "tblenumattribute.AttributeID".</span><span class="sxs-lookup"><span data-stu-id="48d39-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="48d39-125">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="48d39-125">**Table Values**</span></span>

|<span data-ttu-id="48d39-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="48d39-126">**valueID**</span></span>|<span data-ttu-id="48d39-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="48d39-127">**attributeID**</span></span>|<span data-ttu-id="48d39-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="48d39-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48d39-129">2</span><span class="sxs-lookup"><span data-stu-id="48d39-129">2</span></span>  <br/> |<span data-ttu-id="48d39-130">1</span><span class="sxs-lookup"><span data-stu-id="48d39-130">1</span></span>  <br/> |<span data-ttu-id="48d39-131">privat</span><span class="sxs-lookup"><span data-stu-id="48d39-131">private</span></span>  <br/> |
|<span data-ttu-id="48d39-132">3</span><span class="sxs-lookup"><span data-stu-id="48d39-132">3</span></span>  <br/> |<span data-ttu-id="48d39-133">1</span><span class="sxs-lookup"><span data-stu-id="48d39-133">1</span></span>  <br/> |<span data-ttu-id="48d39-134">Umfang</span><span class="sxs-lookup"><span data-stu-id="48d39-134">scope</span></span>  <br/> |
|<span data-ttu-id="48d39-135">4</span><span class="sxs-lookup"><span data-stu-id="48d39-135">4</span></span>  <br/> |<span data-ttu-id="48d39-136">2</span><span class="sxs-lookup"><span data-stu-id="48d39-136">2</span></span>  <br/> |<span data-ttu-id="48d39-137">normale</span><span class="sxs-lookup"><span data-stu-id="48d39-137">normal</span></span>  <br/> |
|<span data-ttu-id="48d39-138">5</span><span class="sxs-lookup"><span data-stu-id="48d39-138">5</span></span>  <br/> |<span data-ttu-id="48d39-139">2</span><span class="sxs-lookup"><span data-stu-id="48d39-139">2</span></span>  <br/> |<span data-ttu-id="48d39-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="48d39-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="48d39-141">6</span><span class="sxs-lookup"><span data-stu-id="48d39-141">6</span></span>  <br/> |<span data-ttu-id="48d39-142">1</span><span class="sxs-lookup"><span data-stu-id="48d39-142">1</span></span>  <br/> |<span data-ttu-id="48d39-143">Öffnen Sie</span><span class="sxs-lookup"><span data-stu-id="48d39-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="48d39-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48d39-144">See also</span></span>

[<span data-ttu-id="48d39-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="48d39-145">tblNode</span></span>](tblnode.md)
