---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906826"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="7b173-104">VideoClientEvent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7b173-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="7b173-105">Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="7b173-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="7b173-106">In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="7b173-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="7b173-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7b173-107">**Column**</span></span>|<span data-ttu-id="7b173-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7b173-108">**Data Type**</span></span>|<span data-ttu-id="7b173-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7b173-109">**Key/Index**</span></span>|<span data-ttu-id="7b173-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7b173-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b173-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="7b173-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="7b173-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7b173-112">datetime</span></span>  <br/> |<span data-ttu-id="7b173-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7b173-113">Primary</span></span>  <br/> |<span data-ttu-id="7b173-114">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="7b173-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b173-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="7b173-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="7b173-116">int</span><span class="sxs-lookup"><span data-stu-id="7b173-116">int</span></span>  <br/> |<span data-ttu-id="7b173-117">Primary</span><span class="sxs-lookup"><span data-stu-id="7b173-117">Primary</span></span>  <br/> |<span data-ttu-id="7b173-118">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="7b173-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b173-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="7b173-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="7b173-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b173-120">tinyint</span></span>  <br/> |<span data-ttu-id="7b173-121">Primary</span><span class="sxs-lookup"><span data-stu-id="7b173-121">Primary</span></span>  <br/> |<span data-ttu-id="7b173-122">Verweis von der [MediaLine-Tabelle](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="7b173-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b173-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="7b173-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="7b173-124">bit</span><span class="sxs-lookup"><span data-stu-id="7b173-124">bit</span></span>  <br/> |<span data-ttu-id="7b173-125">Primary</span><span class="sxs-lookup"><span data-stu-id="7b173-125">Primary</span></span>  <br/> |<span data-ttu-id="7b173-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="7b173-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="7b173-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="7b173-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="7b173-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="7b173-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="7b173-129">Prozentsatz von Sitzungen, in denen das LowBandwidth-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="7b173-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="7b173-130">Die verfügbare Bandbreite ist für eine akzeptable VoIP wünschen unzureichend.</span><span class="sxs-lookup"><span data-stu-id="7b173-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="7b173-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="7b173-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="7b173-132">Prozentsatz von Sitzungen, in denen das ReceiveSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.</span><span class="sxs-lookup"><span data-stu-id="7b173-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="7b173-133">Netzwerkqualität in Bezug auf Jitter oder Paketverlusten ist erheblich und wirkt sich auf die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="7b173-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

