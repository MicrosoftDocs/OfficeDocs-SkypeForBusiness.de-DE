---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814643"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="50952-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="50952-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="50952-104">tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="50952-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="50952-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="50952-105">**Columns**</span></span>

|<span data-ttu-id="50952-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="50952-106">**Column**</span></span>|<span data-ttu-id="50952-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="50952-107">**Type**</span></span>|<span data-ttu-id="50952-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="50952-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50952-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="50952-109">channelUri</span></span>  <br/> |<span data-ttu-id="50952-110">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="50952-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="50952-111">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="50952-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="50952-112">UserID</span><span class="sxs-lookup"><span data-stu-id="50952-112">userId</span></span>  <br/> |<span data-ttu-id="50952-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="50952-113">int, not null</span></span>  <br/> |<span data-ttu-id="50952-114">Prinzipal-ID des Teilnehmers (entsprechend der Tabelle tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="50952-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="50952-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="50952-115">joinedAt</span></span>  <br/> |<span data-ttu-id="50952-116">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="50952-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="50952-117">Zeitstempel des Joining-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="50952-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="50952-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="50952-118">partedAt</span></span>  <br/> |<span data-ttu-id="50952-119">bigint</span><span class="sxs-lookup"><span data-stu-id="50952-119">bigint</span></span>  <br/> |<span data-ttu-id="50952-120">NULL, wenn der Teilnehmer noch verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="50952-120">Null if participant is still joined.</span></span> <span data-ttu-id="50952-121">Der Zeitstempel des Kanals, der das Ereignis verlässt, wenn nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="50952-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="50952-122">Diese Einträge werden schließlich entfernt, wenn alle Übersetzer das Ereignis verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="50952-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="50952-123">userUri</span><span class="sxs-lookup"><span data-stu-id="50952-123">userUri</span></span>  <br/> |<span data-ttu-id="50952-124">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="50952-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="50952-125">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="50952-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="50952-126">ServerID</span><span class="sxs-lookup"><span data-stu-id="50952-126">serverID</span></span>  <br/> |<span data-ttu-id="50952-127">int</span><span class="sxs-lookup"><span data-stu-id="50952-127">int</span></span>  <br/> |<span data-ttu-id="50952-128">Serveridentität (wie in der Tabelle tblServerIdentity. Server-ID).</span><span class="sxs-lookup"><span data-stu-id="50952-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="50952-129">SessionID</span><span class="sxs-lookup"><span data-stu-id="50952-129">sessionId</span></span>  <br/> |<span data-ttu-id="50952-130">bigint</span><span class="sxs-lookup"><span data-stu-id="50952-130">bigint</span></span>  <br/> |<span data-ttu-id="50952-131">Server Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50952-131">Server session.</span></span> <span data-ttu-id="50952-132">Hierbei handelt es sich um eine Zufallszahl, die bei jedem Start eines Chat-Diensts generiert wird.</span><span class="sxs-lookup"><span data-stu-id="50952-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="50952-133">Sie wird zur Unterscheidung von Sitzungen zum Zweck der Identifizierung verwaister Teilnehmer verwendet.</span><span class="sxs-lookup"><span data-stu-id="50952-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="50952-134">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="50952-134">**Key**</span></span>

|<span data-ttu-id="50952-135">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="50952-135">**Column**</span></span>|<span data-ttu-id="50952-136">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="50952-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50952-137">\<channelUri, UserID, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="50952-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="50952-138">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="50952-138">Primary key.</span></span>  <br/> |
   

