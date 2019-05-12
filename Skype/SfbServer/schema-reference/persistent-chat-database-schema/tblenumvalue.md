---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: "\"TblEnumValue\" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden."
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929868"
---
# <a name="tblenumvalue"></a><span data-ttu-id="9f9c8-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="9f9c8-103">tblEnumValue</span></span>
 
<span data-ttu-id="9f9c8-104">"TblEnumValue" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f9c8-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="9f9c8-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-105">**Columns**</span></span>

|<span data-ttu-id="9f9c8-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-106">**Column**</span></span>|<span data-ttu-id="9f9c8-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-107">**Type**</span></span>|<span data-ttu-id="9f9c8-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f9c8-109">valueID</span><span class="sxs-lookup"><span data-stu-id="9f9c8-109">valueID</span></span>  <br/> |<span data-ttu-id="9f9c8-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="9f9c8-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="9f9c8-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="9f9c8-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="9f9c8-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="9f9c8-112">attributeID</span></span>  <br/> |<span data-ttu-id="9f9c8-113">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="9f9c8-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="9f9c8-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="9f9c8-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="9f9c8-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9f9c8-115">attributeValue</span></span>  <br/> |<span data-ttu-id="9f9c8-116">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="9f9c8-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9f9c8-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="9f9c8-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="9f9c8-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-118">**Keys**</span></span>

|<span data-ttu-id="9f9c8-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-119">**Column**</span></span>|<span data-ttu-id="9f9c8-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f9c8-121">valueID</span><span class="sxs-lookup"><span data-stu-id="9f9c8-121">valueID</span></span>  <br/> |<span data-ttu-id="9f9c8-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="9f9c8-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9f9c8-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="9f9c8-123">attributeID</span></span>  <br/> |<span data-ttu-id="9f9c8-124">Fremdschlüssel mit Abfrage der Tabelle "tblenumattribute.AttributeID".</span><span class="sxs-lookup"><span data-stu-id="9f9c8-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="9f9c8-125">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-125">**Table Values**</span></span>

|<span data-ttu-id="9f9c8-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-126">**valueID**</span></span>|<span data-ttu-id="9f9c8-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-127">**attributeID**</span></span>|<span data-ttu-id="9f9c8-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f9c8-129">2</span><span class="sxs-lookup"><span data-stu-id="9f9c8-129">2</span></span>  <br/> |<span data-ttu-id="9f9c8-130">1</span><span class="sxs-lookup"><span data-stu-id="9f9c8-130">1</span></span>  <br/> |<span data-ttu-id="9f9c8-131">privat</span><span class="sxs-lookup"><span data-stu-id="9f9c8-131">private</span></span>  <br/> |
|<span data-ttu-id="9f9c8-132">3</span><span class="sxs-lookup"><span data-stu-id="9f9c8-132">3</span></span>  <br/> |<span data-ttu-id="9f9c8-133">1</span><span class="sxs-lookup"><span data-stu-id="9f9c8-133">1</span></span>  <br/> |<span data-ttu-id="9f9c8-134">Umfang</span><span class="sxs-lookup"><span data-stu-id="9f9c8-134">scope</span></span>  <br/> |
|<span data-ttu-id="9f9c8-135">4</span><span class="sxs-lookup"><span data-stu-id="9f9c8-135">4</span></span>  <br/> |<span data-ttu-id="9f9c8-136">2</span><span class="sxs-lookup"><span data-stu-id="9f9c8-136">2</span></span>  <br/> |<span data-ttu-id="9f9c8-137">normale</span><span class="sxs-lookup"><span data-stu-id="9f9c8-137">normal</span></span>  <br/> |
|<span data-ttu-id="9f9c8-138">5</span><span class="sxs-lookup"><span data-stu-id="9f9c8-138">5</span></span>  <br/> |<span data-ttu-id="9f9c8-139">2</span><span class="sxs-lookup"><span data-stu-id="9f9c8-139">2</span></span>  <br/> |<span data-ttu-id="9f9c8-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="9f9c8-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="9f9c8-141">6</span><span class="sxs-lookup"><span data-stu-id="9f9c8-141">6</span></span>  <br/> |<span data-ttu-id="9f9c8-142">1</span><span class="sxs-lookup"><span data-stu-id="9f9c8-142">1</span></span>  <br/> |<span data-ttu-id="9f9c8-143">Öffnen Sie</span><span class="sxs-lookup"><span data-stu-id="9f9c8-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9f9c8-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f9c8-144">See also</span></span>

[<span data-ttu-id="9f9c8-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="9f9c8-145">tblNode</span></span>](tblnode.md)
