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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813573"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="f7131-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="f7131-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="f7131-104">tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7131-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="f7131-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="f7131-105">**Columns**</span></span>

|<span data-ttu-id="f7131-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f7131-106">**Column**</span></span>|<span data-ttu-id="f7131-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f7131-107">**Type**</span></span>|<span data-ttu-id="f7131-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f7131-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7131-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f7131-109">prinID</span></span>  <br/> |<span data-ttu-id="f7131-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f7131-110">int, not null</span></span>  <br/> |<span data-ttu-id="f7131-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="f7131-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f7131-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="f7131-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="f7131-113">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f7131-113">bit, not null</span></span>  <br/> |<span data-ttu-id="f7131-114">"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7131-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f7131-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="f7131-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="f7131-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f7131-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f7131-117">"True", wenn Prinzipal Attribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7131-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f7131-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f7131-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="f7131-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f7131-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f7131-120">"True", wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="f7131-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="f7131-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="f7131-121">tryCount</span></span>  <br/> |<span data-ttu-id="f7131-122">int</span><span class="sxs-lookup"><span data-stu-id="f7131-122">int</span></span>  <br/> |<span data-ttu-id="f7131-123">Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</span><span class="sxs-lookup"><span data-stu-id="f7131-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="f7131-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="f7131-124">lastTry</span></span>  <br/> |<span data-ttu-id="f7131-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f7131-125">datetime</span></span>  <br/> |<span data-ttu-id="f7131-126">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7131-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="f7131-127">Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="f7131-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="f7131-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="f7131-128">nextTry</span></span>  <br/> |<span data-ttu-id="f7131-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f7131-129">datetime</span></span>  <br/> |<span data-ttu-id="f7131-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="f7131-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="f7131-131">Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="f7131-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="f7131-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f7131-132">**Keys**</span></span>

|<span data-ttu-id="f7131-133">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f7131-133">**Column**</span></span>|<span data-ttu-id="f7131-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f7131-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f7131-135">prinID</span><span class="sxs-lookup"><span data-stu-id="f7131-135">prinID</span></span>  <br/> |<span data-ttu-id="f7131-136">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="f7131-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f7131-137">prinID</span><span class="sxs-lookup"><span data-stu-id="f7131-137">prinID</span></span>  <br/> |<span data-ttu-id="f7131-138">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f7131-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

