---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929938"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="e13a6-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e13a6-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="e13a6-104">TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="e13a6-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="e13a6-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="e13a6-105">**Columns**</span></span>

|<span data-ttu-id="e13a6-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e13a6-106">**Column**</span></span>|<span data-ttu-id="e13a6-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e13a6-107">**Type**</span></span>|<span data-ttu-id="e13a6-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e13a6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e13a6-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="e13a6-109">channelUri</span></span>  <br/> |<span data-ttu-id="e13a6-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="e13a6-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e13a6-111">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="e13a6-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="e13a6-112">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="e13a6-112">userId</span></span>  <br/> |<span data-ttu-id="e13a6-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e13a6-113">int, not null</span></span>  <br/> |<span data-ttu-id="e13a6-114">Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="e13a6-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="e13a6-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="e13a6-115">joinedAt</span></span>  <br/> |<span data-ttu-id="e13a6-116">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="e13a6-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="e13a6-117">Zeitstempel des Ereignisses des Beitritts.</span><span class="sxs-lookup"><span data-stu-id="e13a6-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="e13a6-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="e13a6-118">partedAt</span></span>  <br/> |<span data-ttu-id="e13a6-119">bigint</span><span class="sxs-lookup"><span data-stu-id="e13a6-119">bigint</span></span>  <br/> |<span data-ttu-id="e13a6-120">"NULL" Wenn Teilnehmer noch angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e13a6-120">Null if participant is still joined.</span></span> <span data-ttu-id="e13a6-121">Der Zeitstempel des Kanals Ereignis verlassen, wenn nicht null.</span><span class="sxs-lookup"><span data-stu-id="e13a6-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="e13a6-122">Diese Einträge werden schließlich entfernt, wenn alle Übersetzer des Ereignisses Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="e13a6-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="e13a6-123">userUri</span><span class="sxs-lookup"><span data-stu-id="e13a6-123">userUri</span></span>  <br/> |<span data-ttu-id="e13a6-124">nvarchar(255), nicht null</span><span class="sxs-lookup"><span data-stu-id="e13a6-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="e13a6-125">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e13a6-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="e13a6-126">serverID</span><span class="sxs-lookup"><span data-stu-id="e13a6-126">serverID</span></span>  <br/> |<span data-ttu-id="e13a6-127">int</span><span class="sxs-lookup"><span data-stu-id="e13a6-127">int</span></span>  <br/> |<span data-ttu-id="e13a6-128">Serveridentität (wie in tblserveridentity.ServerID).</span><span class="sxs-lookup"><span data-stu-id="e13a6-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="e13a6-129">Sitzungs-ID</span><span class="sxs-lookup"><span data-stu-id="e13a6-129">sessionId</span></span>  <br/> |<span data-ttu-id="e13a6-130">bigint</span><span class="sxs-lookup"><span data-stu-id="e13a6-130">bigint</span></span>  <br/> |<span data-ttu-id="e13a6-131">Server-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e13a6-131">Server session.</span></span> <span data-ttu-id="e13a6-132">Dies ist eine Zufallszahl generiert jedes Mal, wenn ein Chatdienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e13a6-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="e13a6-133">Es wird zur Unterscheidung von Sitzungen zur Identifizierung von verwaisten Teilnehmer verwendet.</span><span class="sxs-lookup"><span data-stu-id="e13a6-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="e13a6-134">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="e13a6-134">**Key**</span></span>

|<span data-ttu-id="e13a6-135">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e13a6-135">**Column**</span></span>|<span data-ttu-id="e13a6-136">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e13a6-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e13a6-137">\<ChannelUri, UserId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="e13a6-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="e13a6-138">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e13a6-138">Primary key.</span></span>  <br/> |
   

