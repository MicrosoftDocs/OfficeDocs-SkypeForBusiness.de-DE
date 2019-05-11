---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904181"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="200b8-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="200b8-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="200b8-104">TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="200b8-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="200b8-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="200b8-105">**Columns**</span></span>

|<span data-ttu-id="200b8-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="200b8-106">**Column**</span></span>|<span data-ttu-id="200b8-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="200b8-107">**Type**</span></span>|<span data-ttu-id="200b8-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="200b8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="200b8-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="200b8-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="200b8-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="200b8-110">int, not null</span></span>  <br/> |<span data-ttu-id="200b8-111">Knoten-ID, die für die Rolle gilt.</span><span class="sxs-lookup"><span data-stu-id="200b8-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="200b8-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="200b8-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="200b8-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="200b8-113">int, not null</span></span>  <br/> |<span data-ttu-id="200b8-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="200b8-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="200b8-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="200b8-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="200b8-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="200b8-116">int, not null</span></span>  <br/> |<span data-ttu-id="200b8-117">Rollentyp-ID (von TblRoleType).</span><span class="sxs-lookup"><span data-stu-id="200b8-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="200b8-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="200b8-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="200b8-119">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="200b8-119">int, not null</span></span>  <br/> |<span data-ttu-id="200b8-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="200b8-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="200b8-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="200b8-121">**Keys**</span></span>

|<span data-ttu-id="200b8-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="200b8-122">**Column**</span></span>|<span data-ttu-id="200b8-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="200b8-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="200b8-124">\<PrinRoleNodeID, PrinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="200b8-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="200b8-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="200b8-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="200b8-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="200b8-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="200b8-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="200b8-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="200b8-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="200b8-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="200b8-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="200b8-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="200b8-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="200b8-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="200b8-131">Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="200b8-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

