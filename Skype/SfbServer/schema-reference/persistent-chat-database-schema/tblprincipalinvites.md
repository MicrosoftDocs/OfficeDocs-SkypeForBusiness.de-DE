---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814183"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="c40f1-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c40f1-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="c40f1-104">tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c40f1-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="c40f1-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c40f1-105">**Columns**</span></span>

|<span data-ttu-id="c40f1-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c40f1-106">**Column**</span></span>|<span data-ttu-id="c40f1-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c40f1-107">**Type**</span></span>|<span data-ttu-id="c40f1-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c40f1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c40f1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c40f1-109">prinID</span></span>  <br/> |<span data-ttu-id="c40f1-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c40f1-110">int, not null</span></span>  <br/> |<span data-ttu-id="c40f1-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="c40f1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c40f1-112">invID</span><span class="sxs-lookup"><span data-stu-id="c40f1-112">invID</span></span>  <br/> |<span data-ttu-id="c40f1-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c40f1-113">int, not null</span></span>  <br/> |<span data-ttu-id="c40f1-114">Eindeutige sequenzielle Zahl (pro Prinzipal-ID), die aus der tblLastInviteId-Tabelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c40f1-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="c40f1-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="c40f1-115">nodeID</span></span>  <br/> |<span data-ttu-id="c40f1-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c40f1-116">int, not null</span></span>  <br/> |<span data-ttu-id="c40f1-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="c40f1-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="c40f1-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="c40f1-118">createdOn</span></span>  <br/> |<span data-ttu-id="c40f1-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c40f1-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c40f1-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c40f1-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="c40f1-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="c40f1-121">**Keys**</span></span>

|<span data-ttu-id="c40f1-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c40f1-122">**Column**</span></span>|<span data-ttu-id="c40f1-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c40f1-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c40f1-124">\<prinID, Knoten-Nr.\></span><span class="sxs-lookup"><span data-stu-id="c40f1-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="c40f1-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="c40f1-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c40f1-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c40f1-126">prinID</span></span>  <br/> |<span data-ttu-id="c40f1-127">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c40f1-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c40f1-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="c40f1-128">nodeID</span></span>  <br/> |<span data-ttu-id="c40f1-129">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c40f1-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

