---
title: VideoClientEvent-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="5d9d2-104">VideoClientEvent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5d9d2-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="5d9d2-105">Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="5d9d2-106">In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="5d9d2-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-107">**Column**</span></span>|<span data-ttu-id="5d9d2-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-108">**Data Type**</span></span>|<span data-ttu-id="5d9d2-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-109">**Key/Index**</span></span>|<span data-ttu-id="5d9d2-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d9d2-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="5d9d2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5d9d2-112">datetime</span></span>  <br/> |<span data-ttu-id="5d9d2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5d9d2-113">Primary</span></span>  <br/> |<span data-ttu-id="5d9d2-114">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d9d2-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5d9d2-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="5d9d2-116">int</span><span class="sxs-lookup"><span data-stu-id="5d9d2-116">int</span></span>  <br/> |<span data-ttu-id="5d9d2-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5d9d2-117">Primary</span></span>  <br/> |<span data-ttu-id="5d9d2-118">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d9d2-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5d9d2-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="5d9d2-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5d9d2-120">tinyint</span></span>  <br/> |<span data-ttu-id="5d9d2-121">Primary</span><span class="sxs-lookup"><span data-stu-id="5d9d2-121">Primary</span></span>  <br/> |<span data-ttu-id="5d9d2-122">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d9d2-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5d9d2-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="5d9d2-124">bit</span><span class="sxs-lookup"><span data-stu-id="5d9d2-124">bit</span></span>  <br/> |<span data-ttu-id="5d9d2-125">Primary</span><span class="sxs-lookup"><span data-stu-id="5d9d2-125">Primary</span></span>  <br/> |<span data-ttu-id="5d9d2-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="5d9d2-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="5d9d2-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="5d9d2-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="5d9d2-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5d9d2-129">Prozentsatz von Sitzungen, in denen das LowBandwidth-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="5d9d2-130">Die verfügbare Bandbreite ist für eine akzeptable VoIP wünschen unzureichend.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="5d9d2-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="5d9d2-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5d9d2-132">Prozentsatz von Sitzungen, in denen das ReceiveSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="5d9d2-133">Netzwerkqualität in Bezug auf Jitter oder Paketverlusten ist erheblich und wirkt sich auf die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="5d9d2-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

