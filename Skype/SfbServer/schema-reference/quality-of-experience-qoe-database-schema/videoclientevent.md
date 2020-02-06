---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804993"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="545c7-104">VideoClientEvent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="545c7-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="545c7-105">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="545c7-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="545c7-106">In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="545c7-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="545c7-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="545c7-107">**Column**</span></span>|<span data-ttu-id="545c7-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="545c7-108">**Data Type**</span></span>|<span data-ttu-id="545c7-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="545c7-109">**Key/Index**</span></span>|<span data-ttu-id="545c7-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="545c7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="545c7-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="545c7-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="545c7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="545c7-112">datetime</span></span>  <br/> |<span data-ttu-id="545c7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="545c7-113">Primary</span></span>  <br/> |<span data-ttu-id="545c7-114">In der [medialinie-Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="545c7-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="545c7-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="545c7-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="545c7-116">int</span><span class="sxs-lookup"><span data-stu-id="545c7-116">int</span></span>  <br/> |<span data-ttu-id="545c7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="545c7-117">Primary</span></span>  <br/> |<span data-ttu-id="545c7-118">In der [medialinie-Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="545c7-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="545c7-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="545c7-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="545c7-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="545c7-120">tinyint</span></span>  <br/> |<span data-ttu-id="545c7-121">Primary</span><span class="sxs-lookup"><span data-stu-id="545c7-121">Primary</span></span>  <br/> |<span data-ttu-id="545c7-122">In der [medialinie-Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="545c7-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="545c7-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="545c7-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="545c7-124">bit</span><span class="sxs-lookup"><span data-stu-id="545c7-124">bit</span></span>  <br/> |<span data-ttu-id="545c7-125">Primary</span><span class="sxs-lookup"><span data-stu-id="545c7-125">Primary</span></span>  <br/> |<span data-ttu-id="545c7-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="545c7-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="545c7-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="545c7-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="545c7-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="545c7-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="545c7-129">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="545c7-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="545c7-130">Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.</span><span class="sxs-lookup"><span data-stu-id="545c7-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="545c7-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="545c7-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="545c7-132">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="545c7-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="545c7-133">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.</span><span class="sxs-lookup"><span data-stu-id="545c7-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

