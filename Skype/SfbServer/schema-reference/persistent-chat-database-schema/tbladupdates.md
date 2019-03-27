---
title: tblADUpdates
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899603"
---
# <a name="tbladupdates"></a><span data-ttu-id="c8735-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="c8735-103">tblADUpdates</span></span>
 
<span data-ttu-id="c8735-104">TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="c8735-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="c8735-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c8735-105">**Columns**</span></span>

|<span data-ttu-id="c8735-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c8735-106">**Column**</span></span>|<span data-ttu-id="c8735-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c8735-107">**Type**</span></span>|<span data-ttu-id="c8735-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c8735-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8735-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c8735-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c8735-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c8735-111">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="c8735-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="c8735-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c8735-112">prinADPath</span></span>  <br/> |<span data-ttu-id="c8735-113">Nvarchar (384), nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="c8735-114">Distinguished Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="c8735-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="c8735-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="c8735-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="c8735-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c8735-117">True, wenn mindestens ein Attribut des Objekts geändert.</span><span class="sxs-lookup"><span data-stu-id="c8735-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="c8735-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="c8735-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="c8735-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-119">bit, not null</span></span>  <br/> |<span data-ttu-id="c8735-120">True, wenn die Mitgliedschaft geändert hat.</span><span class="sxs-lookup"><span data-stu-id="c8735-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="c8735-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="c8735-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="c8735-122">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-122">bit, not null</span></span>  <br/> |<span data-ttu-id="c8735-123">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8735-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="c8735-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c8735-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="c8735-125">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-125">bit, not null</span></span>  <br/> |<span data-ttu-id="c8735-126">True, wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="c8735-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="c8735-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c8735-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="c8735-128">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="c8735-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="c8735-129">Zeitstempel der, wenn die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8735-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

