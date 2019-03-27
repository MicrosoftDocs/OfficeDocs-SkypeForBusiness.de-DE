---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881416"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="89588-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="89588-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="89588-104">TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="89588-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="89588-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="89588-105">**Columns**</span></span>

|<span data-ttu-id="89588-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="89588-106">**Column**</span></span>|<span data-ttu-id="89588-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="89588-107">**Type**</span></span>|<span data-ttu-id="89588-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89588-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89588-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="89588-109">channelUri</span></span>  <br/> |<span data-ttu-id="89588-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="89588-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="89588-111">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="89588-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="89588-112">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="89588-112">userId</span></span>  <br/> |<span data-ttu-id="89588-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="89588-113">int, not null</span></span>  <br/> |<span data-ttu-id="89588-114">Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="89588-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="89588-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="89588-115">joinedAt</span></span>  <br/> |<span data-ttu-id="89588-116">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="89588-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="89588-117">Zeitstempel des Ereignisses des Beitritts.</span><span class="sxs-lookup"><span data-stu-id="89588-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="89588-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="89588-118">partedAt</span></span>  <br/> |<span data-ttu-id="89588-119">bigint</span><span class="sxs-lookup"><span data-stu-id="89588-119">bigint</span></span>  <br/> |<span data-ttu-id="89588-120">"NULL" Wenn Teilnehmer noch angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="89588-120">Null if participant is still joined.</span></span> <span data-ttu-id="89588-121">Der Zeitstempel des Kanals Ereignis verlassen, wenn nicht null.</span><span class="sxs-lookup"><span data-stu-id="89588-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="89588-122">Diese Einträge werden schließlich entfernt, wenn alle Übersetzer des Ereignisses Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="89588-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="89588-123">userUri</span><span class="sxs-lookup"><span data-stu-id="89588-123">userUri</span></span>  <br/> |<span data-ttu-id="89588-124">nvarchar(255), nicht null</span><span class="sxs-lookup"><span data-stu-id="89588-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="89588-125">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="89588-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="89588-126">serverID</span><span class="sxs-lookup"><span data-stu-id="89588-126">serverID</span></span>  <br/> |<span data-ttu-id="89588-127">int</span><span class="sxs-lookup"><span data-stu-id="89588-127">int</span></span>  <br/> |<span data-ttu-id="89588-128">Serveridentität (wie in tblserveridentity.ServerID).</span><span class="sxs-lookup"><span data-stu-id="89588-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="89588-129">Sitzungs-ID</span><span class="sxs-lookup"><span data-stu-id="89588-129">sessionId</span></span>  <br/> |<span data-ttu-id="89588-130">bigint</span><span class="sxs-lookup"><span data-stu-id="89588-130">bigint</span></span>  <br/> |<span data-ttu-id="89588-131">Server-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="89588-131">Server session.</span></span> <span data-ttu-id="89588-132">Dies ist eine Zufallszahl generiert jedes Mal, wenn ein Chatdienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="89588-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="89588-133">Es wird zur Unterscheidung von Sitzungen zur Identifizierung von verwaisten Teilnehmer verwendet.</span><span class="sxs-lookup"><span data-stu-id="89588-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="89588-134">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="89588-134">**Key**</span></span>

|<span data-ttu-id="89588-135">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="89588-135">**Column**</span></span>|<span data-ttu-id="89588-136">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89588-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89588-137">\<ChannelUri, UserId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="89588-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="89588-138">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="89588-138">Primary key.</span></span>  <br/> |
   

