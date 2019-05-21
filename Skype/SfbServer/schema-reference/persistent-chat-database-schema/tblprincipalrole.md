---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295237"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="00f84-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="00f84-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="00f84-104">tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="00f84-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="00f84-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="00f84-105">**Columns**</span></span>

|<span data-ttu-id="00f84-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="00f84-106">**Column**</span></span>|<span data-ttu-id="00f84-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="00f84-107">**Type**</span></span>|<span data-ttu-id="00f84-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00f84-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00f84-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="00f84-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="00f84-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="00f84-110">int, not null</span></span>  <br/> |<span data-ttu-id="00f84-111">Die Knoten-ID, auf die sich die Rolle bezieht.</span><span class="sxs-lookup"><span data-stu-id="00f84-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="00f84-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="00f84-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="00f84-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="00f84-113">int, not null</span></span>  <br/> |<span data-ttu-id="00f84-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="00f84-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="00f84-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="00f84-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="00f84-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="00f84-116">int, not null</span></span>  <br/> |<span data-ttu-id="00f84-117">Rollentyp-ID (aus tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="00f84-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="00f84-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="00f84-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="00f84-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="00f84-119">int, not null</span></span>  <br/> |<span data-ttu-id="00f84-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="00f84-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="00f84-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="00f84-121">**Keys**</span></span>

|<span data-ttu-id="00f84-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="00f84-122">**Column**</span></span>|<span data-ttu-id="00f84-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00f84-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00f84-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="00f84-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="00f84-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="00f84-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="00f84-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="00f84-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="00f84-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="00f84-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="00f84-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="00f84-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="00f84-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="00f84-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="00f84-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="00f84-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="00f84-131">Fremdschlüssel mit Lookup in der tblRoleType. rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="00f84-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

