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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212453"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="3aa80-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="3aa80-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="3aa80-104">TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3aa80-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="3aa80-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3aa80-105">**Columns**</span></span>

|<span data-ttu-id="3aa80-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3aa80-106">**Column**</span></span>|<span data-ttu-id="3aa80-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3aa80-107">**Type**</span></span>|<span data-ttu-id="3aa80-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3aa80-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3aa80-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="3aa80-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="3aa80-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="3aa80-110">int, not null</span></span>  <br/> |<span data-ttu-id="3aa80-111">Knoten-ID, die für die Rolle gilt.</span><span class="sxs-lookup"><span data-stu-id="3aa80-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="3aa80-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="3aa80-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="3aa80-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="3aa80-113">int, not null</span></span>  <br/> |<span data-ttu-id="3aa80-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="3aa80-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3aa80-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="3aa80-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="3aa80-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="3aa80-116">int, not null</span></span>  <br/> |<span data-ttu-id="3aa80-117">Rollentyp-ID (von TblRoleType).</span><span class="sxs-lookup"><span data-stu-id="3aa80-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="3aa80-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="3aa80-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="3aa80-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="3aa80-119">int, not null</span></span>  <br/> |<span data-ttu-id="3aa80-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3aa80-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="3aa80-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="3aa80-121">**Keys**</span></span>

|<span data-ttu-id="3aa80-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3aa80-122">**Column**</span></span>|<span data-ttu-id="3aa80-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3aa80-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3aa80-124">\<PrinRoleNodeID, PrinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="3aa80-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="3aa80-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="3aa80-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3aa80-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="3aa80-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="3aa80-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3aa80-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="3aa80-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="3aa80-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="3aa80-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3aa80-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="3aa80-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="3aa80-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="3aa80-131">Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3aa80-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

