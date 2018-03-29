---
title: "\"tblprincipalmeta\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: "\"tblprincipalmeta\" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen."
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="d69a5-103">"tblprincipalmeta"</span><span class="sxs-lookup"><span data-stu-id="d69a5-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="d69a5-104">"tblprincipalmeta" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d69a5-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="d69a5-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d69a5-105">**Columns**</span></span>

|<span data-ttu-id="d69a5-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d69a5-106">**Column**</span></span>|<span data-ttu-id="d69a5-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d69a5-107">**Type**</span></span>|<span data-ttu-id="d69a5-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d69a5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d69a5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d69a5-109">prinID</span></span>  <br/> |<span data-ttu-id="d69a5-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d69a5-110">int, not null</span></span>  <br/> |<span data-ttu-id="d69a5-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="d69a5-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d69a5-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="d69a5-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="d69a5-113">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="d69a5-113">bit, not null</span></span>  <br/> |<span data-ttu-id="d69a5-114">True, wenn prinzipalzuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d69a5-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="d69a5-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="d69a5-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="d69a5-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="d69a5-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d69a5-117">True, wenn prinzipalattribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d69a5-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="d69a5-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d69a5-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="d69a5-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="d69a5-119">bit, not null</span></span>  <br/> |<span data-ttu-id="d69a5-120">True, wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="d69a5-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="d69a5-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="d69a5-121">tryCount</span></span>  <br/> |<span data-ttu-id="d69a5-122">int</span><span class="sxs-lookup"><span data-stu-id="d69a5-122">int</span></span>  <br/> |<span data-ttu-id="d69a5-123">Anzahl der Versuche zum Erstellen den Prinzipal aus AD DS zu aktualisieren, die bisher ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d69a5-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="d69a5-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="d69a5-124">lastTry</span></span>  <br/> |<span data-ttu-id="d69a5-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d69a5-125">datetime</span></span>  <br/> |<span data-ttu-id="d69a5-126">Zeitstempel vom aktuellen Versuch, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d69a5-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="d69a5-127">Kann null sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="d69a5-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="d69a5-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="d69a5-128">nextTry</span></span>  <br/> |<span data-ttu-id="d69a5-129">datetime</span><span class="sxs-lookup"><span data-stu-id="d69a5-129">datetime</span></span>  <br/> |<span data-ttu-id="d69a5-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="d69a5-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="d69a5-131">Kann null sein, wenn keine weiteren Refresh geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="d69a5-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="d69a5-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d69a5-132">**Keys**</span></span>

|<span data-ttu-id="d69a5-133">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d69a5-133">**Column**</span></span>|<span data-ttu-id="d69a5-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d69a5-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d69a5-135">prinID</span><span class="sxs-lookup"><span data-stu-id="d69a5-135">prinID</span></span>  <br/> |<span data-ttu-id="d69a5-136">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d69a5-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d69a5-137">prinID</span><span class="sxs-lookup"><span data-stu-id="d69a5-137">prinID</span></span>  <br/> |<span data-ttu-id="d69a5-138">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d69a5-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

