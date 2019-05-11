---
title: Servertabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server-Tabelle ist eine Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920131"
---
# <a name="server-table"></a><span data-ttu-id="eff2d-104">Servertabelle</span><span class="sxs-lookup"><span data-stu-id="eff2d-104">Server table</span></span>
 
<span data-ttu-id="eff2d-105">Die Server-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="eff2d-105">The Server table is a supporting table.</span></span> <span data-ttu-id="eff2d-106">Jeder Datensatz steht für einen Server.</span><span class="sxs-lookup"><span data-stu-id="eff2d-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="eff2d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="eff2d-107">**Column**</span></span>|<span data-ttu-id="eff2d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="eff2d-108">**Data Type**</span></span>|<span data-ttu-id="eff2d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="eff2d-109">**Key/Index**</span></span>|<span data-ttu-id="eff2d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="eff2d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eff2d-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="eff2d-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="eff2d-112">int</span><span class="sxs-lookup"><span data-stu-id="eff2d-112">int</span></span>  <br/> |<span data-ttu-id="eff2d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="eff2d-113">Primary</span></span>  <br/> |<span data-ttu-id="eff2d-114">Eindeutige Zahl, die den Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="eff2d-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="eff2d-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="eff2d-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="eff2d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eff2d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="eff2d-117">Index</span><span class="sxs-lookup"><span data-stu-id="eff2d-117">index</span></span>  <br/> |<span data-ttu-id="eff2d-118">MAC-Adresszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eff2d-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="eff2d-119">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="eff2d-119">**ServerType**</span></span> <br/> |<span data-ttu-id="eff2d-120">int</span><span class="sxs-lookup"><span data-stu-id="eff2d-120">int</span></span>  <br/> |<span data-ttu-id="eff2d-121">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="eff2d-121">Foreign</span></span>  <br/> |<span data-ttu-id="eff2d-122">1: Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="eff2d-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="eff2d-123">2: A / V-konferenzserver16394: A / V-Edgedienst32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="eff2d-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="eff2d-124">**"Poolname"**</span><span class="sxs-lookup"><span data-stu-id="eff2d-124">**PoolName**</span></span> <br/> |<span data-ttu-id="eff2d-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="eff2d-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="eff2d-126">Pool der Server gehört.</span><span class="sxs-lookup"><span data-stu-id="eff2d-126">Pool the server belongs to.</span></span> <span data-ttu-id="eff2d-127">Gilt nur für den A / V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="eff2d-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="eff2d-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="eff2d-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="eff2d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="eff2d-129">datetime</span></span>  <br/> ||<span data-ttu-id="eff2d-130">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="eff2d-130">For internal use only.</span></span>  <br/> |
   

