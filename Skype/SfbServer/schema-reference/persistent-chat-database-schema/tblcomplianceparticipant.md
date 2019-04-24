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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212951"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="2bf81-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="2bf81-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="2bf81-104">TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="2bf81-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="2bf81-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="2bf81-105">**Columns**</span></span>

|<span data-ttu-id="2bf81-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2bf81-106">**Column**</span></span>|<span data-ttu-id="2bf81-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2bf81-107">**Type**</span></span>|<span data-ttu-id="2bf81-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2bf81-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2bf81-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="2bf81-109">channelUri</span></span>  <br/> |<span data-ttu-id="2bf81-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="2bf81-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2bf81-111">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="2bf81-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="2bf81-112">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="2bf81-112">userId</span></span>  <br/> |<span data-ttu-id="2bf81-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2bf81-113">int, not null</span></span>  <br/> |<span data-ttu-id="2bf81-114">Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="2bf81-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="2bf81-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="2bf81-115">joinedAt</span></span>  <br/> |<span data-ttu-id="2bf81-116">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="2bf81-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="2bf81-117">Zeitstempel des Ereignisses des Beitritts.</span><span class="sxs-lookup"><span data-stu-id="2bf81-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="2bf81-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="2bf81-118">partedAt</span></span>  <br/> |<span data-ttu-id="2bf81-119">bigint</span><span class="sxs-lookup"><span data-stu-id="2bf81-119">bigint</span></span>  <br/> |<span data-ttu-id="2bf81-120">"NULL" Wenn Teilnehmer noch angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2bf81-120">Null if participant is still joined.</span></span> <span data-ttu-id="2bf81-121">Der Zeitstempel des Kanals Ereignis verlassen, wenn nicht null.</span><span class="sxs-lookup"><span data-stu-id="2bf81-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="2bf81-122">Diese Einträge werden schließlich entfernt, wenn alle Übersetzer des Ereignisses Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="2bf81-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="2bf81-123">userUri</span><span class="sxs-lookup"><span data-stu-id="2bf81-123">userUri</span></span>  <br/> |<span data-ttu-id="2bf81-124">nvarchar(255), nicht null</span><span class="sxs-lookup"><span data-stu-id="2bf81-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="2bf81-125">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="2bf81-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="2bf81-126">serverID</span><span class="sxs-lookup"><span data-stu-id="2bf81-126">serverID</span></span>  <br/> |<span data-ttu-id="2bf81-127">int</span><span class="sxs-lookup"><span data-stu-id="2bf81-127">int</span></span>  <br/> |<span data-ttu-id="2bf81-128">Serveridentität (wie in tblserveridentity.ServerID).</span><span class="sxs-lookup"><span data-stu-id="2bf81-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="2bf81-129">Sitzungs-ID</span><span class="sxs-lookup"><span data-stu-id="2bf81-129">sessionId</span></span>  <br/> |<span data-ttu-id="2bf81-130">bigint</span><span class="sxs-lookup"><span data-stu-id="2bf81-130">bigint</span></span>  <br/> |<span data-ttu-id="2bf81-131">Server-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2bf81-131">Server session.</span></span> <span data-ttu-id="2bf81-132">Dies ist eine Zufallszahl generiert jedes Mal, wenn ein Chatdienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2bf81-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="2bf81-133">Es wird zur Unterscheidung von Sitzungen zur Identifizierung von verwaisten Teilnehmer verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bf81-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="2bf81-134">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="2bf81-134">**Key**</span></span>

|<span data-ttu-id="2bf81-135">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2bf81-135">**Column**</span></span>|<span data-ttu-id="2bf81-136">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2bf81-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bf81-137">\<ChannelUri, UserId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="2bf81-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="2bf81-138">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="2bf81-138">Primary key.</span></span>  <br/> |
   

