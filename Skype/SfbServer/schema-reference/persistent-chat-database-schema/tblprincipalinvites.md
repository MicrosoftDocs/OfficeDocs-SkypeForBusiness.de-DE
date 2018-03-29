---
title: tblPrincipalInvites
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
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="4fda2-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4fda2-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="4fda2-104">TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4fda2-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="4fda2-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="4fda2-105">**Columns**</span></span>

|<span data-ttu-id="4fda2-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4fda2-106">**Column**</span></span>|<span data-ttu-id="4fda2-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4fda2-107">**Type**</span></span>|<span data-ttu-id="4fda2-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4fda2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4fda2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4fda2-109">prinID</span></span>  <br/> |<span data-ttu-id="4fda2-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="4fda2-110">int, not null</span></span>  <br/> |<span data-ttu-id="4fda2-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="4fda2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4fda2-112">invID</span><span class="sxs-lookup"><span data-stu-id="4fda2-112">invID</span></span>  <br/> |<span data-ttu-id="4fda2-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="4fda2-113">int, not null</span></span>  <br/> |<span data-ttu-id="4fda2-114">Eindeutige fortlaufende Zahl (pro Prinzipal-ID) generiert von der TblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fda2-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="4fda2-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="4fda2-115">nodeID</span></span>  <br/> |<span data-ttu-id="4fda2-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="4fda2-116">int, not null</span></span>  <br/> |<span data-ttu-id="4fda2-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="4fda2-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="4fda2-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="4fda2-118">createdOn</span></span>  <br/> |<span data-ttu-id="4fda2-119">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="4fda2-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="4fda2-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="4fda2-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="4fda2-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4fda2-121">**Keys**</span></span>

|<span data-ttu-id="4fda2-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4fda2-122">**Column**</span></span>|<span data-ttu-id="4fda2-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4fda2-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fda2-124">\<PrinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="4fda2-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="4fda2-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4fda2-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4fda2-126">prinID</span><span class="sxs-lookup"><span data-stu-id="4fda2-126">prinID</span></span>  <br/> |<span data-ttu-id="4fda2-127">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fda2-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="4fda2-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="4fda2-128">nodeID</span></span>  <br/> |<span data-ttu-id="4fda2-129">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fda2-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

