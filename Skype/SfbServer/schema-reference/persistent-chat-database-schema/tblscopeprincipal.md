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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812443"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b3ba0-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b3ba0-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b3ba0-104">tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b3ba0-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-105">**Columns**</span></span>

|<span data-ttu-id="b3ba0-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-106">**Column**</span></span>|<span data-ttu-id="b3ba0-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-107">**Type**</span></span>|<span data-ttu-id="b3ba0-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b3ba0-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b3ba0-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b3ba0-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3ba0-110">int, not null</span></span>  <br/> |<span data-ttu-id="b3ba0-111">Knoten-ID, auf die sich der Bereich bezieht.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b3ba0-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b3ba0-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b3ba0-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3ba0-113">int, not null</span></span>  <br/> |<span data-ttu-id="b3ba0-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b3ba0-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b3ba0-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b3ba0-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3ba0-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b3ba0-117">"True", wenn der Typ des Bereichs "verweigern" lautet. False, wenn allow.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b3ba0-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b3ba0-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b3ba0-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3ba0-119">int, not null</span></span>  <br/> |<span data-ttu-id="b3ba0-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b3ba0-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-121">**Keys**</span></span>

|<span data-ttu-id="b3ba0-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-122">**Column**</span></span>|<span data-ttu-id="b3ba0-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b3ba0-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3ba0-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="b3ba0-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="b3ba0-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b3ba0-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b3ba0-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b3ba0-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b3ba0-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b3ba0-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b3ba0-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b3ba0-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="b3ba0-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b3ba0-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

