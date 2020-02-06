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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814613"
---
# <a name="tblenumattribute"></a><span data-ttu-id="bd2d0-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="bd2d0-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="bd2d0-104">tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd2d0-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="bd2d0-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-105">**Columns**</span></span>

|<span data-ttu-id="bd2d0-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-106">**Column**</span></span>|<span data-ttu-id="bd2d0-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-107">**Type**</span></span>|<span data-ttu-id="bd2d0-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd2d0-109">AttributeID</span><span class="sxs-lookup"><span data-stu-id="bd2d0-109">attributeID</span></span>  <br/> |<span data-ttu-id="bd2d0-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bd2d0-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="bd2d0-111">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bd2d0-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="bd2d0-112">AttributeName</span><span class="sxs-lookup"><span data-stu-id="bd2d0-112">attributeName</span></span>  <br/> |<span data-ttu-id="bd2d0-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bd2d0-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="bd2d0-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bd2d0-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="bd2d0-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-115">**Key**</span></span>

|<span data-ttu-id="bd2d0-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-116">**Column**</span></span>|<span data-ttu-id="bd2d0-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd2d0-118">AttributeID</span><span class="sxs-lookup"><span data-stu-id="bd2d0-118">attributeID</span></span>  <br/> |<span data-ttu-id="bd2d0-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="bd2d0-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="bd2d0-120">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-120">**Table Values**</span></span>

|<span data-ttu-id="bd2d0-121">**AttributeID**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-121">**attributeID**</span></span>|<span data-ttu-id="bd2d0-122">**AttributeName**</span><span class="sxs-lookup"><span data-stu-id="bd2d0-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd2d0-123">1</span><span class="sxs-lookup"><span data-stu-id="bd2d0-123">1</span></span>  <br/> |<span data-ttu-id="bd2d0-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="bd2d0-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="bd2d0-125">2</span><span class="sxs-lookup"><span data-stu-id="bd2d0-125">2</span></span>  <br/> |<span data-ttu-id="bd2d0-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="bd2d0-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bd2d0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd2d0-127">See also</span></span>

[<span data-ttu-id="bd2d0-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="bd2d0-128">tblNode</span></span>](tblnode.md)
