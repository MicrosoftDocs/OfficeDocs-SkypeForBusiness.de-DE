---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295195"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="5d2be-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="5d2be-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="5d2be-104">tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5d2be-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="5d2be-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="5d2be-105">**Columns**</span></span>

|<span data-ttu-id="5d2be-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5d2be-106">**Column**</span></span>|<span data-ttu-id="5d2be-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="5d2be-107">**Type**</span></span>|<span data-ttu-id="5d2be-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5d2be-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d2be-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5d2be-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5d2be-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5d2be-110">int, not null</span></span>  <br/> |<span data-ttu-id="5d2be-111">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="5d2be-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="5d2be-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5d2be-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="5d2be-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5d2be-113">int, not null</span></span>  <br/> |<span data-ttu-id="5d2be-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="5d2be-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5d2be-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="5d2be-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="5d2be-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5d2be-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5d2be-117">"True", wenn der Typ des Bereichs "verweigern" lautet. False, wenn allow.</span><span class="sxs-lookup"><span data-stu-id="5d2be-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="5d2be-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5d2be-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="5d2be-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5d2be-119">int, not null</span></span>  <br/> |<span data-ttu-id="5d2be-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="5d2be-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5d2be-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5d2be-121">**Keys**</span></span>

|<span data-ttu-id="5d2be-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5d2be-122">**Column**</span></span>|<span data-ttu-id="5d2be-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5d2be-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d2be-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="5d2be-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="5d2be-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="5d2be-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5d2be-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5d2be-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5d2be-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5d2be-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5d2be-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5d2be-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="5d2be-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5d2be-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

