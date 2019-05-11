---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924423"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="678e5-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="678e5-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="678e5-104">TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="678e5-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="678e5-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="678e5-105">**Columns**</span></span>

|<span data-ttu-id="678e5-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="678e5-106">**Column**</span></span>|<span data-ttu-id="678e5-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="678e5-107">**Type**</span></span>|<span data-ttu-id="678e5-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="678e5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="678e5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="678e5-109">prinID</span></span>  <br/> |<span data-ttu-id="678e5-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="678e5-110">int, not null</span></span>  <br/> |<span data-ttu-id="678e5-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="678e5-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="678e5-112">invID</span><span class="sxs-lookup"><span data-stu-id="678e5-112">invID</span></span>  <br/> |<span data-ttu-id="678e5-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="678e5-113">int, not null</span></span>  <br/> |<span data-ttu-id="678e5-114">Eindeutige fortlaufende Zahl (pro Prinzipal-ID) generiert von der TblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="678e5-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="678e5-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="678e5-115">nodeID</span></span>  <br/> |<span data-ttu-id="678e5-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="678e5-116">int, not null</span></span>  <br/> |<span data-ttu-id="678e5-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="678e5-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="678e5-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="678e5-118">createdOn</span></span>  <br/> |<span data-ttu-id="678e5-119">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="678e5-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="678e5-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="678e5-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="678e5-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="678e5-121">**Keys**</span></span>

|<span data-ttu-id="678e5-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="678e5-122">**Column**</span></span>|<span data-ttu-id="678e5-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="678e5-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="678e5-124">\<PrinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="678e5-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="678e5-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="678e5-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="678e5-126">prinID</span><span class="sxs-lookup"><span data-stu-id="678e5-126">prinID</span></span>  <br/> |<span data-ttu-id="678e5-127">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="678e5-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="678e5-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="678e5-128">nodeID</span></span>  <br/> |<span data-ttu-id="678e5-129">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="678e5-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

