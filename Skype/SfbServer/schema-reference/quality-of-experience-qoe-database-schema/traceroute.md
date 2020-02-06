---
title: TraceRoute-Tabelle
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Die traceroute-Tabelle enthält Routinginformationen aus anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805113"
---
# <a name="traceroute-table"></a><span data-ttu-id="d1e27-104">TraceRoute-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d1e27-104">TraceRoute table</span></span>
 
<span data-ttu-id="d1e27-105">Die traceroute-Tabelle enthält Routinginformationen aus anrufen.</span><span class="sxs-lookup"><span data-stu-id="d1e27-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="d1e27-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d1e27-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d1e27-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d1e27-107">**Column**</span></span>|<span data-ttu-id="d1e27-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d1e27-108">**Data Type**</span></span>|<span data-ttu-id="d1e27-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d1e27-109">**Key/Index**</span></span>|<span data-ttu-id="d1e27-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d1e27-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1e27-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d1e27-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d1e27-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d1e27-112">datetime</span></span>  <br/> |<span data-ttu-id="d1e27-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d1e27-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1e27-114">Das Datum und die Uhrzeit, zu der der Anruf begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="d1e27-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="d1e27-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d1e27-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d1e27-116">int</span><span class="sxs-lookup"><span data-stu-id="d1e27-116">int</span></span>  <br/> |<span data-ttu-id="d1e27-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d1e27-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1e27-118">Eindeutiger Bezeichner, der verwendet wird, um zwischen mehreren Anrufen zu unterscheiden, die möglicherweise am gleichen Datum und zur gleichen Zeit begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="d1e27-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="d1e27-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d1e27-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d1e27-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d1e27-120">tinyint</span></span>  <br/> |<span data-ttu-id="d1e27-121">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d1e27-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1e27-122">Stellt den Typ der im Anruf verwendeten Videozeile dar.</span><span class="sxs-lookup"><span data-stu-id="d1e27-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="d1e27-123">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="d1e27-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="d1e27-124">0-Audio</span><span class="sxs-lookup"><span data-stu-id="d1e27-124">0 - Audio</span></span>  <br/> <span data-ttu-id="d1e27-125">1-Video</span><span class="sxs-lookup"><span data-stu-id="d1e27-125">1 - Video</span></span>  <br/> <span data-ttu-id="d1e27-126">2 – Panorama Video</span><span class="sxs-lookup"><span data-stu-id="d1e27-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="d1e27-127">3 – Anwendung/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="d1e27-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="d1e27-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d1e27-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="d1e27-129">bit</span><span class="sxs-lookup"><span data-stu-id="d1e27-129">bit</span></span>  <br/> |<span data-ttu-id="d1e27-130">Primary</span><span class="sxs-lookup"><span data-stu-id="d1e27-130">Primary</span></span>  <br/> |<span data-ttu-id="d1e27-131">Endpunkt, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="d1e27-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="d1e27-132">**Hop**</span><span class="sxs-lookup"><span data-stu-id="d1e27-132">**Hop**</span></span> <br/> |<span data-ttu-id="d1e27-133">int</span><span class="sxs-lookup"><span data-stu-id="d1e27-133">int</span></span>  <br/> ||<span data-ttu-id="d1e27-134">Netzwerk-Hop/</span><span class="sxs-lookup"><span data-stu-id="d1e27-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="d1e27-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="d1e27-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="d1e27-136">int</span><span class="sxs-lookup"><span data-stu-id="d1e27-136">int</span></span>  <br/> |<span data-ttu-id="d1e27-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="d1e27-137">Foreign</span></span>  <br/> |<span data-ttu-id="d1e27-138">Eindeutiger Bezeichner für die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="d1e27-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="d1e27-139">IP-Adressinformationen werden in der [IPAddress-Tabelle](ipaddress.md)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1e27-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="d1e27-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="d1e27-140">**RTT**</span></span> <br/> |<span data-ttu-id="d1e27-141">int</span><span class="sxs-lookup"><span data-stu-id="d1e27-141">int</span></span>  <br/> ||<span data-ttu-id="d1e27-142">Roundtrip-Zeit.</span><span class="sxs-lookup"><span data-stu-id="d1e27-142">Roundtrip time.</span></span> <span data-ttu-id="d1e27-143">Die Roundtrip-Zeit misst die Zeitdauer, die ein Sprachpaket benötigt, um sein Ziel zu erreichen, und sendet dann eine Benachrichtigung, dass es empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d1e27-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

