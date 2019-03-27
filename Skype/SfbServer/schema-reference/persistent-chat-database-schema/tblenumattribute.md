---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: "\"Enumattribute\" ist eine hardkodierte Tabelle mit den Attributen Visibility und Behavior, die in der Node-Tabelle verwendet werden."
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879699"
---
# <a name="tblenumattribute"></a><span data-ttu-id="48d08-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="48d08-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="48d08-104">"Enumattribute" ist eine hardkodierte Tabelle mit den Attributen Visibility und Behavior, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48d08-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="48d08-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="48d08-105">**Columns**</span></span>

|<span data-ttu-id="48d08-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48d08-106">**Column**</span></span>|<span data-ttu-id="48d08-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="48d08-107">**Type**</span></span>|<span data-ttu-id="48d08-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48d08-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48d08-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="48d08-109">attributeID</span></span>  <br/> |<span data-ttu-id="48d08-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="48d08-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="48d08-111">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="48d08-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="48d08-112">Attributname</span><span class="sxs-lookup"><span data-stu-id="48d08-112">attributeName</span></span>  <br/> |<span data-ttu-id="48d08-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="48d08-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="48d08-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="48d08-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="48d08-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="48d08-115">**Key**</span></span>

|<span data-ttu-id="48d08-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48d08-116">**Column**</span></span>|<span data-ttu-id="48d08-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48d08-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48d08-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="48d08-118">attributeID</span></span>  <br/> |<span data-ttu-id="48d08-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="48d08-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="48d08-120">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="48d08-120">**Table Values**</span></span>

|<span data-ttu-id="48d08-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="48d08-121">**attributeID**</span></span>|<span data-ttu-id="48d08-122">**Attributname**</span><span class="sxs-lookup"><span data-stu-id="48d08-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48d08-123">1</span><span class="sxs-lookup"><span data-stu-id="48d08-123">1</span></span>  <br/> |<span data-ttu-id="48d08-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="48d08-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="48d08-125">2</span><span class="sxs-lookup"><span data-stu-id="48d08-125">2</span></span>  <br/> |<span data-ttu-id="48d08-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="48d08-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="48d08-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48d08-127">See also</span></span>

[<span data-ttu-id="48d08-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="48d08-128">tblNode</span></span>](tblnode.md)
