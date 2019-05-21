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
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294552"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="57789-104">VideoClientEvent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="57789-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="57789-105">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="57789-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="57789-106">In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="57789-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="57789-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="57789-107">**Column**</span></span>|<span data-ttu-id="57789-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="57789-108">**Data Type**</span></span>|<span data-ttu-id="57789-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="57789-109">**Key/Index**</span></span>|<span data-ttu-id="57789-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="57789-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57789-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="57789-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="57789-112">datetime</span><span class="sxs-lookup"><span data-stu-id="57789-112">datetime</span></span>  <br/> |<span data-ttu-id="57789-113">Primary</span><span class="sxs-lookup"><span data-stu-id="57789-113">Primary</span></span>  <br/> |<span data-ttu-id="57789-114">In der medialinie- [Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="57789-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="57789-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="57789-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="57789-116">int</span><span class="sxs-lookup"><span data-stu-id="57789-116">int</span></span>  <br/> |<span data-ttu-id="57789-117">Primary</span><span class="sxs-lookup"><span data-stu-id="57789-117">Primary</span></span>  <br/> |<span data-ttu-id="57789-118">In der medialinie- [Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="57789-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="57789-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="57789-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="57789-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="57789-120">tinyint</span></span>  <br/> |<span data-ttu-id="57789-121">Primary</span><span class="sxs-lookup"><span data-stu-id="57789-121">Primary</span></span>  <br/> |<span data-ttu-id="57789-122">In der medialinie- [Tabelle](medialine-0.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="57789-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="57789-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="57789-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="57789-124">bit</span><span class="sxs-lookup"><span data-stu-id="57789-124">bit</span></span>  <br/> |<span data-ttu-id="57789-125">Primary</span><span class="sxs-lookup"><span data-stu-id="57789-125">Primary</span></span>  <br/> |<span data-ttu-id="57789-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="57789-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="57789-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="57789-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="57789-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="57789-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="57789-129">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="57789-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="57789-130">Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.</span><span class="sxs-lookup"><span data-stu-id="57789-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="57789-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="57789-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="57789-132">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="57789-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="57789-133">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.</span><span class="sxs-lookup"><span data-stu-id="57789-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

