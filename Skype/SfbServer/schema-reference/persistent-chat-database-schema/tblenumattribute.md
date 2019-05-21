---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295419"
---
# <a name="tblenumattribute"></a><span data-ttu-id="d506b-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="d506b-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="d506b-104">tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d506b-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d506b-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d506b-105">**Columns**</span></span>

|<span data-ttu-id="d506b-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d506b-106">**Column**</span></span>|<span data-ttu-id="d506b-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d506b-107">**Type**</span></span>|<span data-ttu-id="d506b-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d506b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d506b-109">AttributeID</span><span class="sxs-lookup"><span data-stu-id="d506b-109">attributeID</span></span>  <br/> |<span data-ttu-id="d506b-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d506b-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d506b-111">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="d506b-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d506b-112">AttributeName</span><span class="sxs-lookup"><span data-stu-id="d506b-112">attributeName</span></span>  <br/> |<span data-ttu-id="d506b-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d506b-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d506b-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="d506b-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="d506b-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d506b-115">**Key**</span></span>

|<span data-ttu-id="d506b-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d506b-116">**Column**</span></span>|<span data-ttu-id="d506b-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d506b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d506b-118">AttributeID</span><span class="sxs-lookup"><span data-stu-id="d506b-118">attributeID</span></span>  <br/> |<span data-ttu-id="d506b-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="d506b-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="d506b-120">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="d506b-120">**Table Values**</span></span>

|<span data-ttu-id="d506b-121">**AttributeID**</span><span class="sxs-lookup"><span data-stu-id="d506b-121">**attributeID**</span></span>|<span data-ttu-id="d506b-122">**AttributeName**</span><span class="sxs-lookup"><span data-stu-id="d506b-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d506b-123">1</span><span class="sxs-lookup"><span data-stu-id="d506b-123">1</span></span>  <br/> |<span data-ttu-id="d506b-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d506b-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="d506b-125">2</span><span class="sxs-lookup"><span data-stu-id="d506b-125">2</span></span>  <br/> |<span data-ttu-id="d506b-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d506b-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d506b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d506b-127">See also</span></span>

[<span data-ttu-id="d506b-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="d506b-128">tblNode</span></span>](tblnode.md)
