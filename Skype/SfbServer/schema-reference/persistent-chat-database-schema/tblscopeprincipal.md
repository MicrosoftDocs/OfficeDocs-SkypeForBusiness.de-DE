---
title: in "tblscopeprincipal"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: in "tblscopeprincipal" enthält die Bereiche, die Knoten zugewiesen.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="d4539-103">in "tblscopeprincipal"</span><span class="sxs-lookup"><span data-stu-id="d4539-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="d4539-104">in "tblscopeprincipal" enthält die Bereiche, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d4539-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="d4539-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d4539-105">**Columns**</span></span>

|<span data-ttu-id="d4539-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d4539-106">**Column**</span></span>|<span data-ttu-id="d4539-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d4539-107">**Type**</span></span>|<span data-ttu-id="d4539-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d4539-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4539-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d4539-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="d4539-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d4539-110">int, not null</span></span>  <br/> |<span data-ttu-id="d4539-111">Knoten-ID, die auf der Bereich angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4539-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="d4539-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d4539-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="d4539-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d4539-113">int, not null</span></span>  <br/> |<span data-ttu-id="d4539-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="d4539-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d4539-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d4539-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="d4539-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="d4539-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d4539-117">True, wenn Bereichstyp verweigern. False, wenn ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d4539-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="d4539-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d4539-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="d4539-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d4539-119">int, not null</span></span>  <br/> |<span data-ttu-id="d4539-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d4539-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="d4539-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d4539-121">**Keys**</span></span>

|<span data-ttu-id="d4539-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d4539-122">**Column**</span></span>|<span data-ttu-id="d4539-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d4539-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4539-124">\<ScopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="d4539-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="d4539-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d4539-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d4539-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d4539-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="d4539-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d4539-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="d4539-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d4539-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="d4539-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d4539-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

