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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212642"
---
# <a name="tbladupdates"></a><span data-ttu-id="c4f76-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="c4f76-103">tblADUpdates</span></span>
 
<span data-ttu-id="c4f76-104">TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="c4f76-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="c4f76-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c4f76-105">**Columns**</span></span>

|<span data-ttu-id="c4f76-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c4f76-106">**Column**</span></span>|<span data-ttu-id="c4f76-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c4f76-107">**Type**</span></span>|<span data-ttu-id="c4f76-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c4f76-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4f76-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c4f76-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c4f76-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c4f76-111">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="c4f76-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="c4f76-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c4f76-112">prinADPath</span></span>  <br/> |<span data-ttu-id="c4f76-113">Nvarchar (384), nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="c4f76-114">Distinguished Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="c4f76-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="c4f76-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="c4f76-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="c4f76-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c4f76-117">True, wenn mindestens ein Attribut des Objekts geändert.</span><span class="sxs-lookup"><span data-stu-id="c4f76-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="c4f76-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="c4f76-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="c4f76-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-119">bit, not null</span></span>  <br/> |<span data-ttu-id="c4f76-120">True, wenn die Mitgliedschaft geändert hat.</span><span class="sxs-lookup"><span data-stu-id="c4f76-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="c4f76-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="c4f76-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="c4f76-122">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-122">bit, not null</span></span>  <br/> |<span data-ttu-id="c4f76-123">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4f76-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="c4f76-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c4f76-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="c4f76-125">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-125">bit, not null</span></span>  <br/> |<span data-ttu-id="c4f76-126">True, wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="c4f76-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="c4f76-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c4f76-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="c4f76-128">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="c4f76-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="c4f76-129">Zeitstempel der, wenn die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4f76-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

