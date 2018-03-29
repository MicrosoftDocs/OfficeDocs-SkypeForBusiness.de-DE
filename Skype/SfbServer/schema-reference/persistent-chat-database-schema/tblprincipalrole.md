---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a><span data-ttu-id="e5ede-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="e5ede-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="e5ede-104">TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e5ede-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="e5ede-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="e5ede-105">**Columns**</span></span>

|<span data-ttu-id="e5ede-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e5ede-106">**Column**</span></span>|<span data-ttu-id="e5ede-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e5ede-107">**Type**</span></span>|<span data-ttu-id="e5ede-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e5ede-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5ede-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e5ede-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e5ede-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e5ede-110">int, not null</span></span>  <br/> |<span data-ttu-id="e5ede-111">Knoten-ID, die für die Rolle gilt.</span><span class="sxs-lookup"><span data-stu-id="e5ede-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="e5ede-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e5ede-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e5ede-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e5ede-113">int, not null</span></span>  <br/> |<span data-ttu-id="e5ede-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="e5ede-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e5ede-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e5ede-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e5ede-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e5ede-116">int, not null</span></span>  <br/> |<span data-ttu-id="e5ede-117">Rollentyp-ID (von TblRoleType).</span><span class="sxs-lookup"><span data-stu-id="e5ede-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="e5ede-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e5ede-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="e5ede-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e5ede-119">int, not null</span></span>  <br/> |<span data-ttu-id="e5ede-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e5ede-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="e5ede-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="e5ede-121">**Keys**</span></span>

|<span data-ttu-id="e5ede-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e5ede-122">**Column**</span></span>|<span data-ttu-id="e5ede-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e5ede-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5ede-124">\<PrinRoleNodeID, PrinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="e5ede-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="e5ede-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e5ede-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e5ede-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e5ede-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e5ede-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e5ede-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="e5ede-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e5ede-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e5ede-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e5ede-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e5ede-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e5ede-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e5ede-131">Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e5ede-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

