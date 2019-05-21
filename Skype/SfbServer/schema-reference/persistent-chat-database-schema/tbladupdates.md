---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295559"
---
# <a name="tbladupdates"></a><span data-ttu-id="f6115-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="f6115-103">tblADUpdates</span></span>
 
<span data-ttu-id="f6115-104">tblADUpdates enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="f6115-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="f6115-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="f6115-105">**Columns**</span></span>

|<span data-ttu-id="f6115-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f6115-106">**Column**</span></span>|<span data-ttu-id="f6115-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f6115-107">**Type**</span></span>|<span data-ttu-id="f6115-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f6115-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6115-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f6115-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f6115-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f6115-111">Prinzipal-GUID des geänderten Objekts.</span><span class="sxs-lookup"><span data-stu-id="f6115-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="f6115-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f6115-112">prinADPath</span></span>  <br/> |<span data-ttu-id="f6115-113">nvarchar (384); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="f6115-114">Distinguished Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="f6115-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="f6115-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="f6115-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="f6115-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f6115-117">"True", wenn mindestens ein Attribut des Objekts geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f6115-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="f6115-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="f6115-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="f6115-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f6115-120">"True", wenn die Mitgliedschaft geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f6115-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="f6115-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="f6115-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="f6115-122">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-122">bit, not null</span></span>  <br/> |<span data-ttu-id="f6115-123">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6115-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="f6115-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f6115-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="f6115-125">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-125">bit, not null</span></span>  <br/> |<span data-ttu-id="f6115-126">"True", wenn das Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="f6115-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="f6115-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f6115-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="f6115-128">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f6115-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="f6115-129">Zeitstempel, wann die Zeile eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f6115-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

