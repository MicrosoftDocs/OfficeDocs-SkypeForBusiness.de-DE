---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: in "tblscopeprincipal" enthält die Bereiche, die Knoten zugewiesen.
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924927"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="362f9-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="362f9-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="362f9-104">in "tblscopeprincipal" enthält die Bereiche, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="362f9-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="362f9-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="362f9-105">**Columns**</span></span>

|<span data-ttu-id="362f9-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="362f9-106">**Column**</span></span>|<span data-ttu-id="362f9-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="362f9-107">**Type**</span></span>|<span data-ttu-id="362f9-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="362f9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="362f9-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="362f9-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="362f9-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="362f9-110">int, not null</span></span>  <br/> |<span data-ttu-id="362f9-111">Knoten-ID, die auf der Bereich angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="362f9-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="362f9-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="362f9-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="362f9-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="362f9-113">int, not null</span></span>  <br/> |<span data-ttu-id="362f9-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="362f9-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="362f9-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="362f9-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="362f9-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="362f9-116">bit, not null</span></span>  <br/> |<span data-ttu-id="362f9-117">True, wenn Bereichstyp verweigern. False, wenn ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="362f9-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="362f9-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="362f9-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="362f9-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="362f9-119">int, not null</span></span>  <br/> |<span data-ttu-id="362f9-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="362f9-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="362f9-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="362f9-121">**Keys**</span></span>

|<span data-ttu-id="362f9-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="362f9-122">**Column**</span></span>|<span data-ttu-id="362f9-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="362f9-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="362f9-124">\<ScopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="362f9-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="362f9-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="362f9-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="362f9-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="362f9-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="362f9-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="362f9-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="362f9-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="362f9-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="362f9-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="362f9-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

