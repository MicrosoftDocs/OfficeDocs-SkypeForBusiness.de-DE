---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876690"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="b6d41-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b6d41-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="b6d41-104">TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6d41-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="b6d41-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="b6d41-105">**Columns**</span></span>

|<span data-ttu-id="b6d41-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b6d41-106">**Column**</span></span>|<span data-ttu-id="b6d41-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b6d41-107">**Type**</span></span>|<span data-ttu-id="b6d41-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b6d41-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6d41-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b6d41-109">prinID</span></span>  <br/> |<span data-ttu-id="b6d41-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="b6d41-110">int, not null</span></span>  <br/> |<span data-ttu-id="b6d41-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="b6d41-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b6d41-112">invID</span><span class="sxs-lookup"><span data-stu-id="b6d41-112">invID</span></span>  <br/> |<span data-ttu-id="b6d41-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="b6d41-113">int, not null</span></span>  <br/> |<span data-ttu-id="b6d41-114">Eindeutige fortlaufende Zahl (pro Prinzipal-ID) generiert von der TblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b6d41-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="b6d41-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="b6d41-115">nodeID</span></span>  <br/> |<span data-ttu-id="b6d41-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="b6d41-116">int, not null</span></span>  <br/> |<span data-ttu-id="b6d41-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="b6d41-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="b6d41-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="b6d41-118">createdOn</span></span>  <br/> |<span data-ttu-id="b6d41-119">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="b6d41-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="b6d41-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="b6d41-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="b6d41-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="b6d41-121">**Keys**</span></span>

|<span data-ttu-id="b6d41-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b6d41-122">**Column**</span></span>|<span data-ttu-id="b6d41-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b6d41-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6d41-124">\<PrinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="b6d41-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="b6d41-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="b6d41-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b6d41-126">prinID</span><span class="sxs-lookup"><span data-stu-id="b6d41-126">prinID</span></span>  <br/> |<span data-ttu-id="b6d41-127">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b6d41-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b6d41-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="b6d41-128">nodeID</span></span>  <br/> |<span data-ttu-id="b6d41-129">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b6d41-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

