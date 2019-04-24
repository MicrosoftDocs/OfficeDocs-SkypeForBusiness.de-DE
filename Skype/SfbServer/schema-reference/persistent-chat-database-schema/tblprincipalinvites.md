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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212467"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="a133f-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="a133f-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="a133f-104">TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a133f-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="a133f-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a133f-105">**Columns**</span></span>

|<span data-ttu-id="a133f-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a133f-106">**Column**</span></span>|<span data-ttu-id="a133f-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a133f-107">**Type**</span></span>|<span data-ttu-id="a133f-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a133f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a133f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a133f-109">prinID</span></span>  <br/> |<span data-ttu-id="a133f-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="a133f-110">int, not null</span></span>  <br/> |<span data-ttu-id="a133f-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="a133f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a133f-112">invID</span><span class="sxs-lookup"><span data-stu-id="a133f-112">invID</span></span>  <br/> |<span data-ttu-id="a133f-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="a133f-113">int, not null</span></span>  <br/> |<span data-ttu-id="a133f-114">Eindeutige fortlaufende Zahl (pro Prinzipal-ID) generiert von der TblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a133f-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="a133f-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="a133f-115">nodeID</span></span>  <br/> |<span data-ttu-id="a133f-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="a133f-116">int, not null</span></span>  <br/> |<span data-ttu-id="a133f-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="a133f-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="a133f-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="a133f-118">createdOn</span></span>  <br/> |<span data-ttu-id="a133f-119">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="a133f-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="a133f-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="a133f-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="a133f-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a133f-121">**Keys**</span></span>

|<span data-ttu-id="a133f-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a133f-122">**Column**</span></span>|<span data-ttu-id="a133f-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a133f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a133f-124">\<PrinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="a133f-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="a133f-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a133f-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a133f-126">prinID</span><span class="sxs-lookup"><span data-stu-id="a133f-126">prinID</span></span>  <br/> |<span data-ttu-id="a133f-127">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a133f-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a133f-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="a133f-128">nodeID</span></span>  <br/> |<span data-ttu-id="a133f-129">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a133f-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

