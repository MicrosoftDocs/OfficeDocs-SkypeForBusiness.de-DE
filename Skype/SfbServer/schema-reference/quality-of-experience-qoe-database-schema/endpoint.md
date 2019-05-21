---
title: Endpoint-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294992"
---
# <a name="endpoint-table"></a><span data-ttu-id="df056-104">Endpoint-Tabelle</span><span class="sxs-lookup"><span data-stu-id="df056-104">Endpoint table</span></span>
 
<span data-ttu-id="df056-105">Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="df056-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="df056-106">Jeder Datensatz in der Tabelle steht für einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="df056-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="df056-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="df056-107">**Column**</span></span>|<span data-ttu-id="df056-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="df056-108">**Data Type**</span></span>|<span data-ttu-id="df056-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="df056-109">**Key/Index**</span></span>|<span data-ttu-id="df056-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="df056-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df056-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="df056-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="df056-112">int</span><span class="sxs-lookup"><span data-stu-id="df056-112">int</span></span>  <br/> |<span data-ttu-id="df056-113">Primary</span><span class="sxs-lookup"><span data-stu-id="df056-113">Primary</span></span>  <br/> |<span data-ttu-id="df056-114">Eindeutige Zahl, die diesen Endpunkt kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="df056-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="df056-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="df056-115">**Name**</span></span> <br/> |<span data-ttu-id="df056-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="df056-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="df056-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="df056-117">Unique</span></span>  <br/> |<span data-ttu-id="df056-118">Endpunktname</span><span class="sxs-lookup"><span data-stu-id="df056-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="df056-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="df056-119">**OS**</span></span> <br/> |<span data-ttu-id="df056-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="df056-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="df056-121">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="df056-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="df056-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="df056-122">**CPUName**</span></span> <br/> |<span data-ttu-id="df056-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="df056-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="df056-124">Der CPU-Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="df056-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="df056-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="df056-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="df056-126">smallint</span><span class="sxs-lookup"><span data-stu-id="df056-126">smallint</span></span>  <br/> ||<span data-ttu-id="df056-127">Die Anzahl von CPU-Kernen des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="df056-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="df056-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="df056-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="df056-129">int</span><span class="sxs-lookup"><span data-stu-id="df056-129">int</span></span>  <br/> ||<span data-ttu-id="df056-130">CPU-Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="df056-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="df056-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="df056-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="df056-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="df056-132">tinyint</span></span>  <br/> || <span data-ttu-id="df056-133">Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="df056-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="df056-134">0x0000-None</span><span class="sxs-lookup"><span data-stu-id="df056-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="df056-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="df056-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="df056-136">0x0002-VMware</span><span class="sxs-lookup"><span data-stu-id="df056-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="df056-137">0x0004 – virtueller PC</span><span class="sxs-lookup"><span data-stu-id="df056-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="df056-138">0x0008-xen-PC</span><span class="sxs-lookup"><span data-stu-id="df056-138">0x0008 - Xen PC</span></span> <br/> |
   

