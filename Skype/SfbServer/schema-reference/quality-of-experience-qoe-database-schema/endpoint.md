---
title: Endpoint-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Die Endpunkt-Tabelle ist eine unterstützende Tabelle, die Informationen zu den Endpunkten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a><span data-ttu-id="5f11d-104">Endpoint-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5f11d-104">Endpoint table</span></span>
 
<span data-ttu-id="5f11d-105">Die Endpunkt-Tabelle ist eine unterstützende Tabelle, die Informationen zu den Endpunkten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="5f11d-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5f11d-106">Jeder Datensatz in der Tabelle steht für einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="5f11d-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="5f11d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5f11d-107">**Column**</span></span>|<span data-ttu-id="5f11d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5f11d-108">**Data Type**</span></span>|<span data-ttu-id="5f11d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5f11d-109">**Key/Index**</span></span>|<span data-ttu-id="5f11d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5f11d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f11d-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="5f11d-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="5f11d-112">int</span><span class="sxs-lookup"><span data-stu-id="5f11d-112">int</span></span>  <br/> |<span data-ttu-id="5f11d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5f11d-113">Primary</span></span>  <br/> |<span data-ttu-id="5f11d-114">Eindeutige Zahl, die diesen Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5f11d-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="5f11d-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="5f11d-115">**Name**</span></span> <br/> |<span data-ttu-id="5f11d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f11d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5f11d-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="5f11d-117">Unique</span></span>  <br/> |<span data-ttu-id="5f11d-118">Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="5f11d-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="5f11d-119">**BETRIEBSSYSTEM**</span><span class="sxs-lookup"><span data-stu-id="5f11d-119">**OS**</span></span> <br/> |<span data-ttu-id="5f11d-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="5f11d-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="5f11d-121">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="5f11d-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="5f11d-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="5f11d-122">**CPUName**</span></span> <br/> |<span data-ttu-id="5f11d-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="5f11d-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="5f11d-124">Prozessorname des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="5f11d-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="5f11d-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="5f11d-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="5f11d-126">smallint</span><span class="sxs-lookup"><span data-stu-id="5f11d-126">smallint</span></span>  <br/> ||<span data-ttu-id="5f11d-127">Anzahl der Prozessorkerne des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="5f11d-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="5f11d-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="5f11d-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="5f11d-129">int</span><span class="sxs-lookup"><span data-stu-id="5f11d-129">int</span></span>  <br/> ||<span data-ttu-id="5f11d-130">Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="5f11d-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="5f11d-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="5f11d-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="5f11d-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="5f11d-132">tinyint</span></span>  <br/> || <span data-ttu-id="5f11d-133">Bitflag, die angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="5f11d-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="5f11d-134">0 x 0000 - keine</span><span class="sxs-lookup"><span data-stu-id="5f11d-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="5f11d-135">0 x 0001 - Hyper-v</span><span class="sxs-lookup"><span data-stu-id="5f11d-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="5f11d-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="5f11d-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="5f11d-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="5f11d-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="5f11d-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="5f11d-138">0x0008 - Xen PC</span></span> <br/> |
   

