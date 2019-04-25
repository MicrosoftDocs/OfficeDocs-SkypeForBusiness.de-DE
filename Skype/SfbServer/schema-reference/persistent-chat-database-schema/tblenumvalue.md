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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212880"
---
# <a name="tblenumvalue"></a><span data-ttu-id="409fd-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="409fd-103">tblEnumValue</span></span>
 
<span data-ttu-id="409fd-104">"TblEnumValue" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="409fd-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="409fd-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="409fd-105">**Columns**</span></span>

|<span data-ttu-id="409fd-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="409fd-106">**Column**</span></span>|<span data-ttu-id="409fd-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="409fd-107">**Type**</span></span>|<span data-ttu-id="409fd-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="409fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="409fd-109">valueID</span><span class="sxs-lookup"><span data-stu-id="409fd-109">valueID</span></span>  <br/> |<span data-ttu-id="409fd-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="409fd-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="409fd-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="409fd-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="409fd-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="409fd-112">attributeID</span></span>  <br/> |<span data-ttu-id="409fd-113">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="409fd-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="409fd-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="409fd-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="409fd-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="409fd-115">attributeValue</span></span>  <br/> |<span data-ttu-id="409fd-116">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="409fd-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="409fd-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="409fd-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="409fd-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="409fd-118">**Keys**</span></span>

|<span data-ttu-id="409fd-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="409fd-119">**Column**</span></span>|<span data-ttu-id="409fd-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="409fd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="409fd-121">valueID</span><span class="sxs-lookup"><span data-stu-id="409fd-121">valueID</span></span>  <br/> |<span data-ttu-id="409fd-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="409fd-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="409fd-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="409fd-123">attributeID</span></span>  <br/> |<span data-ttu-id="409fd-124">Fremdschlüssel mit Abfrage der Tabelle "tblenumattribute.AttributeID".</span><span class="sxs-lookup"><span data-stu-id="409fd-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="409fd-125">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="409fd-125">**Table Values**</span></span>

|<span data-ttu-id="409fd-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="409fd-126">**valueID**</span></span>|<span data-ttu-id="409fd-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="409fd-127">**attributeID**</span></span>|<span data-ttu-id="409fd-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="409fd-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="409fd-129">2</span><span class="sxs-lookup"><span data-stu-id="409fd-129">2</span></span>  <br/> |<span data-ttu-id="409fd-130">1</span><span class="sxs-lookup"><span data-stu-id="409fd-130">1</span></span>  <br/> |<span data-ttu-id="409fd-131">privat</span><span class="sxs-lookup"><span data-stu-id="409fd-131">private</span></span>  <br/> |
|<span data-ttu-id="409fd-132">3</span><span class="sxs-lookup"><span data-stu-id="409fd-132">3</span></span>  <br/> |<span data-ttu-id="409fd-133">1</span><span class="sxs-lookup"><span data-stu-id="409fd-133">1</span></span>  <br/> |<span data-ttu-id="409fd-134">Umfang</span><span class="sxs-lookup"><span data-stu-id="409fd-134">scope</span></span>  <br/> |
|<span data-ttu-id="409fd-135">4</span><span class="sxs-lookup"><span data-stu-id="409fd-135">4</span></span>  <br/> |<span data-ttu-id="409fd-136">2</span><span class="sxs-lookup"><span data-stu-id="409fd-136">2</span></span>  <br/> |<span data-ttu-id="409fd-137">normale</span><span class="sxs-lookup"><span data-stu-id="409fd-137">normal</span></span>  <br/> |
|<span data-ttu-id="409fd-138">5</span><span class="sxs-lookup"><span data-stu-id="409fd-138">5</span></span>  <br/> |<span data-ttu-id="409fd-139">2</span><span class="sxs-lookup"><span data-stu-id="409fd-139">2</span></span>  <br/> |<span data-ttu-id="409fd-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="409fd-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="409fd-141">6</span><span class="sxs-lookup"><span data-stu-id="409fd-141">6</span></span>  <br/> |<span data-ttu-id="409fd-142">1</span><span class="sxs-lookup"><span data-stu-id="409fd-142">1</span></span>  <br/> |<span data-ttu-id="409fd-143">Öffnen Sie</span><span class="sxs-lookup"><span data-stu-id="409fd-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="409fd-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="409fd-144">See also</span></span>

[<span data-ttu-id="409fd-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="409fd-145">tblNode</span></span>](tblnode.md)
