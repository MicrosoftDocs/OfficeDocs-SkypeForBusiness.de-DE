---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: "\"Enumattribute\" ist eine hardkodierte Tabelle mit den Attributen Visibility und Behavior, die in der Node-Tabelle verwendet werden."
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929952"
---
# <a name="tblenumattribute"></a><span data-ttu-id="52a84-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="52a84-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="52a84-104">"Enumattribute" ist eine hardkodierte Tabelle mit den Attributen Visibility und Behavior, die in der Node-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52a84-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="52a84-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="52a84-105">**Columns**</span></span>

|<span data-ttu-id="52a84-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="52a84-106">**Column**</span></span>|<span data-ttu-id="52a84-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="52a84-107">**Type**</span></span>|<span data-ttu-id="52a84-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="52a84-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52a84-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="52a84-109">attributeID</span></span>  <br/> |<span data-ttu-id="52a84-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="52a84-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="52a84-111">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="52a84-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="52a84-112">Attributname</span><span class="sxs-lookup"><span data-stu-id="52a84-112">attributeName</span></span>  <br/> |<span data-ttu-id="52a84-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="52a84-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="52a84-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="52a84-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="52a84-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="52a84-115">**Key**</span></span>

|<span data-ttu-id="52a84-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="52a84-116">**Column**</span></span>|<span data-ttu-id="52a84-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="52a84-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52a84-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="52a84-118">attributeID</span></span>  <br/> |<span data-ttu-id="52a84-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="52a84-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="52a84-120">**Tabellenwerte**</span><span class="sxs-lookup"><span data-stu-id="52a84-120">**Table Values**</span></span>

|<span data-ttu-id="52a84-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="52a84-121">**attributeID**</span></span>|<span data-ttu-id="52a84-122">**Attributname**</span><span class="sxs-lookup"><span data-stu-id="52a84-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52a84-123">1</span><span class="sxs-lookup"><span data-stu-id="52a84-123">1</span></span>  <br/> |<span data-ttu-id="52a84-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="52a84-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="52a84-125">2</span><span class="sxs-lookup"><span data-stu-id="52a84-125">2</span></span>  <br/> |<span data-ttu-id="52a84-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="52a84-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="52a84-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52a84-127">See also</span></span>

[<span data-ttu-id="52a84-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="52a84-128">tblNode</span></span>](tblnode.md)
