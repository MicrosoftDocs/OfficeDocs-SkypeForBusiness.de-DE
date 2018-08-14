---
title: tblEnumValue
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
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505076"
---
# <a name="tblenumvalue"></a><span data-ttu-id="ba4b0-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="ba4b0-103">tblEnumValue</span></span>
 
<span data-ttu-id="ba4b0-104">"TblEnumValue" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba4b0-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="ba4b0-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-105">**Columns**</span></span>

|<span data-ttu-id="ba4b0-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-106">**Column**</span></span>|<span data-ttu-id="ba4b0-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-107">**Type**</span></span>|<span data-ttu-id="ba4b0-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba4b0-109">valueID</span><span class="sxs-lookup"><span data-stu-id="ba4b0-109">valueID</span></span>  <br/> |<span data-ttu-id="ba4b0-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="ba4b0-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="ba4b0-111">ID des Werts.</span><span class="sxs-lookup"><span data-stu-id="ba4b0-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="ba4b0-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="ba4b0-112">attributeID</span></span>  <br/> |<span data-ttu-id="ba4b0-113">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="ba4b0-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="ba4b0-114">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="ba4b0-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="ba4b0-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="ba4b0-115">attributeValue</span></span>  <br/> |<span data-ttu-id="ba4b0-116">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="ba4b0-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ba4b0-117">Name des Werts.</span><span class="sxs-lookup"><span data-stu-id="ba4b0-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="ba4b0-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-118">**Keys**</span></span>

|<span data-ttu-id="ba4b0-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-119">**Column**</span></span>|<span data-ttu-id="ba4b0-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba4b0-121">valueID</span><span class="sxs-lookup"><span data-stu-id="ba4b0-121">valueID</span></span>  <br/> |<span data-ttu-id="ba4b0-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba4b0-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ba4b0-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="ba4b0-123">attributeID</span></span>  <br/> |<span data-ttu-id="ba4b0-124">Fremdschlüssel mit Abfrage der Tabelle "tblenumattribute.AttributeID".</span><span class="sxs-lookup"><span data-stu-id="ba4b0-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="ba4b0-125">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-125">**Table Values**</span></span>

|<span data-ttu-id="ba4b0-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-126">**valueID**</span></span>|<span data-ttu-id="ba4b0-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-127">**attributeID**</span></span>|<span data-ttu-id="ba4b0-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="ba4b0-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba4b0-129">2</span><span class="sxs-lookup"><span data-stu-id="ba4b0-129">2</span></span>  <br/> |<span data-ttu-id="ba4b0-130">1</span><span class="sxs-lookup"><span data-stu-id="ba4b0-130">1</span></span>  <br/> |<span data-ttu-id="ba4b0-131">privat</span><span class="sxs-lookup"><span data-stu-id="ba4b0-131">private</span></span>  <br/> |
|<span data-ttu-id="ba4b0-132">3</span><span class="sxs-lookup"><span data-stu-id="ba4b0-132">3</span></span>  <br/> |<span data-ttu-id="ba4b0-133">1</span><span class="sxs-lookup"><span data-stu-id="ba4b0-133">1</span></span>  <br/> |<span data-ttu-id="ba4b0-134">Bereich</span><span class="sxs-lookup"><span data-stu-id="ba4b0-134">scope</span></span>  <br/> |
|<span data-ttu-id="ba4b0-135">4</span><span class="sxs-lookup"><span data-stu-id="ba4b0-135">4</span></span>  <br/> |<span data-ttu-id="ba4b0-136">2</span><span class="sxs-lookup"><span data-stu-id="ba4b0-136">2</span></span>  <br/> |<span data-ttu-id="ba4b0-137">normale</span><span class="sxs-lookup"><span data-stu-id="ba4b0-137">normal</span></span>  <br/> |
|<span data-ttu-id="ba4b0-138">5</span><span class="sxs-lookup"><span data-stu-id="ba4b0-138">5</span></span>  <br/> |<span data-ttu-id="ba4b0-139">2</span><span class="sxs-lookup"><span data-stu-id="ba4b0-139">2</span></span>  <br/> |<span data-ttu-id="ba4b0-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="ba4b0-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="ba4b0-141">6</span><span class="sxs-lookup"><span data-stu-id="ba4b0-141">6</span></span>  <br/> |<span data-ttu-id="ba4b0-142">1</span><span class="sxs-lookup"><span data-stu-id="ba4b0-142">1</span></span>  <br/> |<span data-ttu-id="ba4b0-143">Öffnen Sie</span><span class="sxs-lookup"><span data-stu-id="ba4b0-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ba4b0-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba4b0-144">See also</span></span>

[<span data-ttu-id="ba4b0-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="ba4b0-145">tblNode</span></span>](tblnode.md)