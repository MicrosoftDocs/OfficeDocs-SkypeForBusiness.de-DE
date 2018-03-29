---
title: Enumattribute
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
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a><span data-ttu-id="bccee-103">Enumattribute</span><span class="sxs-lookup"><span data-stu-id="bccee-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="bccee-104">"Enumattribute" ist eine hardkodierte Tabelle mit den Attributen Visibility und Behavior, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bccee-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="bccee-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="bccee-105">**Columns**</span></span>

|<span data-ttu-id="bccee-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bccee-106">**Column**</span></span>|<span data-ttu-id="bccee-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bccee-107">**Type**</span></span>|<span data-ttu-id="bccee-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bccee-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bccee-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="bccee-109">attributeID</span></span>  <br/> |<span data-ttu-id="bccee-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="bccee-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="bccee-111">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bccee-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="bccee-112">Attributname</span><span class="sxs-lookup"><span data-stu-id="bccee-112">attributeName</span></span>  <br/> |<span data-ttu-id="bccee-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="bccee-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="bccee-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bccee-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="bccee-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="bccee-115">**Key**</span></span>

|<span data-ttu-id="bccee-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bccee-116">**Column**</span></span>|<span data-ttu-id="bccee-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bccee-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bccee-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="bccee-118">attributeID</span></span>  <br/> |<span data-ttu-id="bccee-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="bccee-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="bccee-120">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="bccee-120">**Table Values**</span></span>

|<span data-ttu-id="bccee-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="bccee-121">**attributeID**</span></span>|<span data-ttu-id="bccee-122">**Attributname**</span><span class="sxs-lookup"><span data-stu-id="bccee-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bccee-123">1</span><span class="sxs-lookup"><span data-stu-id="bccee-123">1</span></span>  <br/> |<span data-ttu-id="bccee-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="bccee-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="bccee-125">2</span><span class="sxs-lookup"><span data-stu-id="bccee-125">2</span></span>  <br/> |<span data-ttu-id="bccee-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="bccee-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bccee-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bccee-127">See also</span></span>

#### 

[<span data-ttu-id="bccee-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="bccee-128">tblNode</span></span>](tblnode.md)

