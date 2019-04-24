---
title: Endpoint-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212242"
---
# <a name="endpoint-table"></a><span data-ttu-id="b62ac-104">Endpoint-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b62ac-104">Endpoint table</span></span>
 
<span data-ttu-id="b62ac-105">Die Endpunkt-Tabelle ist eine unterstützende Tabelle, die Informationen zu den Endpunkten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="b62ac-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b62ac-106">Jeder Datensatz in der Tabelle steht für einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b62ac-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="b62ac-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b62ac-107">**Column**</span></span>|<span data-ttu-id="b62ac-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b62ac-108">**Data Type**</span></span>|<span data-ttu-id="b62ac-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b62ac-109">**Key/Index**</span></span>|<span data-ttu-id="b62ac-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b62ac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b62ac-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="b62ac-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="b62ac-112">int</span><span class="sxs-lookup"><span data-stu-id="b62ac-112">int</span></span>  <br/> |<span data-ttu-id="b62ac-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b62ac-113">Primary</span></span>  <br/> |<span data-ttu-id="b62ac-114">Eindeutige Zahl, die diesen Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b62ac-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="b62ac-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="b62ac-115">**Name**</span></span> <br/> |<span data-ttu-id="b62ac-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b62ac-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b62ac-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="b62ac-117">Unique</span></span>  <br/> |<span data-ttu-id="b62ac-118">Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="b62ac-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="b62ac-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="b62ac-119">**OS**</span></span> <br/> |<span data-ttu-id="b62ac-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="b62ac-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="b62ac-121">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="b62ac-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b62ac-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="b62ac-122">**CPUName**</span></span> <br/> |<span data-ttu-id="b62ac-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="b62ac-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="b62ac-124">Prozessorname des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="b62ac-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b62ac-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="b62ac-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="b62ac-126">smallint</span><span class="sxs-lookup"><span data-stu-id="b62ac-126">smallint</span></span>  <br/> ||<span data-ttu-id="b62ac-127">Anzahl der Prozessorkerne des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="b62ac-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b62ac-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="b62ac-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="b62ac-129">int</span><span class="sxs-lookup"><span data-stu-id="b62ac-129">int</span></span>  <br/> ||<span data-ttu-id="b62ac-130">Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="b62ac-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="b62ac-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="b62ac-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="b62ac-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="b62ac-132">tinyint</span></span>  <br/> || <span data-ttu-id="b62ac-133">Bitflag, die angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="b62ac-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="b62ac-134">0 x 0000 - keine</span><span class="sxs-lookup"><span data-stu-id="b62ac-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="b62ac-135">0 x 0001 - Hyper-v</span><span class="sxs-lookup"><span data-stu-id="b62ac-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="b62ac-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="b62ac-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="b62ac-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="b62ac-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="b62ac-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="b62ac-138">0x0008 - Xen PC</span></span> <br/> |
   

