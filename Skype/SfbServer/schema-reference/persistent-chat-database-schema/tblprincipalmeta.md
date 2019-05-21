---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295258"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="bb158-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="bb158-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="bb158-104">tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb158-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="bb158-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="bb158-105">**Columns**</span></span>

|<span data-ttu-id="bb158-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bb158-106">**Column**</span></span>|<span data-ttu-id="bb158-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bb158-107">**Type**</span></span>|<span data-ttu-id="bb158-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bb158-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb158-109">prinID</span><span class="sxs-lookup"><span data-stu-id="bb158-109">prinID</span></span>  <br/> |<span data-ttu-id="bb158-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb158-110">int, not null</span></span>  <br/> |<span data-ttu-id="bb158-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="bb158-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="bb158-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="bb158-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="bb158-113">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb158-113">bit, not null</span></span>  <br/> |<span data-ttu-id="bb158-114">"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb158-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="bb158-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="bb158-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="bb158-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb158-116">bit, not null</span></span>  <br/> |<span data-ttu-id="bb158-117">"True", wenn Prinzipal Attribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb158-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="bb158-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="bb158-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="bb158-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb158-119">bit, not null</span></span>  <br/> |<span data-ttu-id="bb158-120">"True", wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="bb158-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="bb158-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="bb158-121">tryCount</span></span>  <br/> |<span data-ttu-id="bb158-122">int</span><span class="sxs-lookup"><span data-stu-id="bb158-122">int</span></span>  <br/> |<span data-ttu-id="bb158-123">Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</span><span class="sxs-lookup"><span data-stu-id="bb158-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="bb158-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="bb158-124">lastTry</span></span>  <br/> |<span data-ttu-id="bb158-125">datetime</span><span class="sxs-lookup"><span data-stu-id="bb158-125">datetime</span></span>  <br/> |<span data-ttu-id="bb158-126">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bb158-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="bb158-127">Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="bb158-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="bb158-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="bb158-128">nextTry</span></span>  <br/> |<span data-ttu-id="bb158-129">datetime</span><span class="sxs-lookup"><span data-stu-id="bb158-129">datetime</span></span>  <br/> |<span data-ttu-id="bb158-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="bb158-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="bb158-131">Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="bb158-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="bb158-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="bb158-132">**Keys**</span></span>

|<span data-ttu-id="bb158-133">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bb158-133">**Column**</span></span>|<span data-ttu-id="bb158-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bb158-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb158-135">prinID</span><span class="sxs-lookup"><span data-stu-id="bb158-135">prinID</span></span>  <br/> |<span data-ttu-id="bb158-136">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="bb158-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bb158-137">prinID</span><span class="sxs-lookup"><span data-stu-id="bb158-137">prinID</span></span>  <br/> |<span data-ttu-id="bb158-138">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bb158-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

