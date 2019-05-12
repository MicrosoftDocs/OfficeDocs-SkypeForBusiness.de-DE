---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: "\"tblprincipalmeta\" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen."
ms.openlocfilehash: a13fdcf705075188ae4febd5a2e0c3bc93a4738f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924542"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="89919-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="89919-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="89919-104">"tblprincipalmeta" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="89919-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="89919-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="89919-105">**Columns**</span></span>

|<span data-ttu-id="89919-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="89919-106">**Column**</span></span>|<span data-ttu-id="89919-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="89919-107">**Type**</span></span>|<span data-ttu-id="89919-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89919-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89919-109">prinID</span><span class="sxs-lookup"><span data-stu-id="89919-109">prinID</span></span>  <br/> |<span data-ttu-id="89919-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="89919-110">int, not null</span></span>  <br/> |<span data-ttu-id="89919-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="89919-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="89919-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="89919-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="89919-113">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="89919-113">bit, not null</span></span>  <br/> |<span data-ttu-id="89919-114">True, wenn prinzipalzuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="89919-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="89919-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="89919-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="89919-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="89919-116">bit, not null</span></span>  <br/> |<span data-ttu-id="89919-117">True, wenn prinzipalattribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="89919-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="89919-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="89919-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="89919-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="89919-119">bit, not null</span></span>  <br/> |<span data-ttu-id="89919-120">True, wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="89919-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="89919-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="89919-121">tryCount</span></span>  <br/> |<span data-ttu-id="89919-122">int</span><span class="sxs-lookup"><span data-stu-id="89919-122">int</span></span>  <br/> |<span data-ttu-id="89919-123">Anzahl der Versuche zum Erstellen den Prinzipal aus AD DS zu aktualisieren, die bisher ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="89919-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="89919-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="89919-124">lastTry</span></span>  <br/> |<span data-ttu-id="89919-125">datetime</span><span class="sxs-lookup"><span data-stu-id="89919-125">datetime</span></span>  <br/> |<span data-ttu-id="89919-126">Zeitstempel vom aktuellen Versuch, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="89919-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="89919-127">Kann null sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="89919-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="89919-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="89919-128">nextTry</span></span>  <br/> |<span data-ttu-id="89919-129">datetime</span><span class="sxs-lookup"><span data-stu-id="89919-129">datetime</span></span>  <br/> |<span data-ttu-id="89919-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="89919-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="89919-131">Kann null sein, wenn keine weiteren Refresh geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="89919-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="89919-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="89919-132">**Keys**</span></span>

|<span data-ttu-id="89919-133">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="89919-133">**Column**</span></span>|<span data-ttu-id="89919-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89919-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89919-135">prinID</span><span class="sxs-lookup"><span data-stu-id="89919-135">prinID</span></span>  <br/> |<span data-ttu-id="89919-136">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="89919-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="89919-137">prinID</span><span class="sxs-lookup"><span data-stu-id="89919-137">prinID</span></span>  <br/> |<span data-ttu-id="89919-138">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="89919-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

