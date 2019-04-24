---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212039"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="d6565-104">VideoClientEvent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d6565-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="d6565-105">Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="d6565-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d6565-106">In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d6565-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="d6565-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d6565-107">**Column**</span></span>|<span data-ttu-id="d6565-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d6565-108">**Data Type**</span></span>|<span data-ttu-id="d6565-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d6565-109">**Key/Index**</span></span>|<span data-ttu-id="d6565-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d6565-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6565-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d6565-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d6565-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d6565-112">datetime</span></span>  <br/> |<span data-ttu-id="d6565-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d6565-113">Primary</span></span>  <br/> |<span data-ttu-id="d6565-114">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d6565-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d6565-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d6565-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d6565-116">int</span><span class="sxs-lookup"><span data-stu-id="d6565-116">int</span></span>  <br/> |<span data-ttu-id="d6565-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d6565-117">Primary</span></span>  <br/> |<span data-ttu-id="d6565-118">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d6565-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d6565-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d6565-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d6565-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d6565-120">tinyint</span></span>  <br/> |<span data-ttu-id="d6565-121">Primary</span><span class="sxs-lookup"><span data-stu-id="d6565-121">Primary</span></span>  <br/> |<span data-ttu-id="d6565-122">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d6565-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d6565-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d6565-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="d6565-124">bit</span><span class="sxs-lookup"><span data-stu-id="d6565-124">bit</span></span>  <br/> |<span data-ttu-id="d6565-125">Primary</span><span class="sxs-lookup"><span data-stu-id="d6565-125">Primary</span></span>  <br/> |<span data-ttu-id="d6565-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="d6565-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="d6565-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="d6565-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="d6565-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d6565-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d6565-129">Prozentsatz von Sitzungen, in denen das LowBandwidth-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="d6565-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="d6565-130">Die verfügbare Bandbreite ist für eine akzeptable VoIP wünschen unzureichend.</span><span class="sxs-lookup"><span data-stu-id="d6565-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="d6565-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d6565-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d6565-132">Prozentsatz von Sitzungen, in denen das ReceiveSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="d6565-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="d6565-133">Netzwerkqualität in Bezug auf Jitter oder Paketverlusten ist erheblich und wirkt sich auf die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="d6565-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

