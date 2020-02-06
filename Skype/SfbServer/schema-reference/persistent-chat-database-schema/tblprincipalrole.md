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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813363"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="ce6d3-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="ce6d3-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="ce6d3-104">tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="ce6d3-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-105">**Columns**</span></span>

|<span data-ttu-id="ce6d3-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-106">**Column**</span></span>|<span data-ttu-id="ce6d3-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-107">**Type**</span></span>|<span data-ttu-id="ce6d3-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce6d3-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="ce6d3-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ce6d3-110">int, not null</span></span>  <br/> |<span data-ttu-id="ce6d3-111">Die Knoten-ID, auf die sich die Rolle bezieht.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="ce6d3-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="ce6d3-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ce6d3-113">int, not null</span></span>  <br/> |<span data-ttu-id="ce6d3-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ce6d3-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="ce6d3-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ce6d3-116">int, not null</span></span>  <br/> |<span data-ttu-id="ce6d3-117">Rollentyp-ID (aus tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="ce6d3-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="ce6d3-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="ce6d3-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="ce6d3-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ce6d3-119">int, not null</span></span>  <br/> |<span data-ttu-id="ce6d3-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="ce6d3-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-121">**Keys**</span></span>

|<span data-ttu-id="ce6d3-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-122">**Column**</span></span>|<span data-ttu-id="ce6d3-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ce6d3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce6d3-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="ce6d3-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="ce6d3-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="ce6d3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ce6d3-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="ce6d3-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ce6d3-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="ce6d3-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="ce6d3-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="ce6d3-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="ce6d3-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="ce6d3-131">Fremdschlüssel mit Lookup in der tblRoleType. rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ce6d3-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

