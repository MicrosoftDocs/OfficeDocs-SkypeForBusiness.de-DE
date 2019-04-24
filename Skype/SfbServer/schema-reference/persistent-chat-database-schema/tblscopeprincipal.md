---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212397"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="8ab16-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="8ab16-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="8ab16-104">in "tblscopeprincipal" enthält die Bereiche, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8ab16-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="8ab16-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="8ab16-105">**Columns**</span></span>

|<span data-ttu-id="8ab16-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8ab16-106">**Column**</span></span>|<span data-ttu-id="8ab16-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8ab16-107">**Type**</span></span>|<span data-ttu-id="8ab16-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8ab16-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ab16-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="8ab16-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="8ab16-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="8ab16-110">int, not null</span></span>  <br/> |<span data-ttu-id="8ab16-111">Knoten-ID, die auf der Bereich angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ab16-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="8ab16-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="8ab16-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="8ab16-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="8ab16-113">int, not null</span></span>  <br/> |<span data-ttu-id="8ab16-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="8ab16-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8ab16-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="8ab16-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="8ab16-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="8ab16-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8ab16-117">True, wenn Bereichstyp verweigern. False, wenn ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8ab16-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="8ab16-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8ab16-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="8ab16-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="8ab16-119">int, not null</span></span>  <br/> |<span data-ttu-id="8ab16-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8ab16-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="8ab16-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8ab16-121">**Keys**</span></span>

|<span data-ttu-id="8ab16-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8ab16-122">**Column**</span></span>|<span data-ttu-id="8ab16-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8ab16-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ab16-124">\<ScopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="8ab16-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="8ab16-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="8ab16-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8ab16-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="8ab16-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="8ab16-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ab16-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="8ab16-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="8ab16-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="8ab16-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ab16-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

