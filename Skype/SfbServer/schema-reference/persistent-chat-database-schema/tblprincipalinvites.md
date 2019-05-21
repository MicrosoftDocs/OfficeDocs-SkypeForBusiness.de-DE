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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295293"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="c9601-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c9601-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="c9601-104">tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c9601-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="c9601-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c9601-105">**Columns**</span></span>

|<span data-ttu-id="c9601-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c9601-106">**Column**</span></span>|<span data-ttu-id="c9601-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c9601-107">**Type**</span></span>|<span data-ttu-id="c9601-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c9601-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9601-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c9601-109">prinID</span></span>  <br/> |<span data-ttu-id="c9601-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c9601-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9601-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="c9601-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c9601-112">invID</span><span class="sxs-lookup"><span data-stu-id="c9601-112">invID</span></span>  <br/> |<span data-ttu-id="c9601-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c9601-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9601-114">Eindeutige sequenzielle Zahl (pro Prinzipal-ID), die aus der tblLastInviteId-Tabelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c9601-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="c9601-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9601-115">nodeID</span></span>  <br/> |<span data-ttu-id="c9601-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c9601-116">int, not null</span></span>  <br/> |<span data-ttu-id="c9601-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="c9601-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="c9601-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="c9601-118">createdOn</span></span>  <br/> |<span data-ttu-id="c9601-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c9601-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c9601-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c9601-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="c9601-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="c9601-121">**Keys**</span></span>

|<span data-ttu-id="c9601-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c9601-122">**Column**</span></span>|<span data-ttu-id="c9601-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c9601-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9601-124">\<prinID, Knoten-Nr.\></span><span class="sxs-lookup"><span data-stu-id="c9601-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="c9601-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="c9601-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9601-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c9601-126">prinID</span></span>  <br/> |<span data-ttu-id="c9601-127">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c9601-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c9601-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9601-128">nodeID</span></span>  <br/> |<span data-ttu-id="c9601-129">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c9601-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

