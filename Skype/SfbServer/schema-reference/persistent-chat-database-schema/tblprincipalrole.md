---
title: tblPrincipalRole
ms.reviewer: ''
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
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890769"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="04529-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="04529-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="04529-104">TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="04529-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="04529-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="04529-105">**Columns**</span></span>

|<span data-ttu-id="04529-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="04529-106">**Column**</span></span>|<span data-ttu-id="04529-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="04529-107">**Type**</span></span>|<span data-ttu-id="04529-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04529-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04529-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="04529-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="04529-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="04529-110">int, not null</span></span>  <br/> |<span data-ttu-id="04529-111">Knoten-ID, die für die Rolle gilt.</span><span class="sxs-lookup"><span data-stu-id="04529-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="04529-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="04529-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="04529-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="04529-113">int, not null</span></span>  <br/> |<span data-ttu-id="04529-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="04529-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="04529-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="04529-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="04529-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="04529-116">int, not null</span></span>  <br/> |<span data-ttu-id="04529-117">Rollentyp-ID (von TblRoleType).</span><span class="sxs-lookup"><span data-stu-id="04529-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="04529-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="04529-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="04529-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="04529-119">int, not null</span></span>  <br/> |<span data-ttu-id="04529-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="04529-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="04529-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="04529-121">**Keys**</span></span>

|<span data-ttu-id="04529-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="04529-122">**Column**</span></span>|<span data-ttu-id="04529-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04529-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04529-124">\<PrinRoleNodeID, PrinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="04529-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="04529-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="04529-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="04529-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="04529-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="04529-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04529-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="04529-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="04529-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="04529-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04529-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="04529-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="04529-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="04529-131">Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04529-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

