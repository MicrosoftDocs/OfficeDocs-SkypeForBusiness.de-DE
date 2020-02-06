---
title: Servertabelle
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806133"
---
# <a name="server-table"></a><span data-ttu-id="69a5d-104">Servertabelle</span><span class="sxs-lookup"><span data-stu-id="69a5d-104">Server table</span></span>
 
<span data-ttu-id="69a5d-105">Die Server Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="69a5d-105">The Server table is a supporting table.</span></span> <span data-ttu-id="69a5d-106">Jeder Datensatz steht für einen Server.</span><span class="sxs-lookup"><span data-stu-id="69a5d-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="69a5d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="69a5d-107">**Column**</span></span>|<span data-ttu-id="69a5d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="69a5d-108">**Data Type**</span></span>|<span data-ttu-id="69a5d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="69a5d-109">**Key/Index**</span></span>|<span data-ttu-id="69a5d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="69a5d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69a5d-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="69a5d-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="69a5d-112">int</span><span class="sxs-lookup"><span data-stu-id="69a5d-112">int</span></span>  <br/> |<span data-ttu-id="69a5d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="69a5d-113">Primary</span></span>  <br/> |<span data-ttu-id="69a5d-114">Eindeutige Nummer, die den Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="69a5d-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="69a5d-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="69a5d-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="69a5d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="69a5d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69a5d-117">Index</span><span class="sxs-lookup"><span data-stu-id="69a5d-117">index</span></span>  <br/> |<span data-ttu-id="69a5d-118">Mac-Adresszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69a5d-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="69a5d-119">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="69a5d-119">**ServerType**</span></span> <br/> |<span data-ttu-id="69a5d-120">int</span><span class="sxs-lookup"><span data-stu-id="69a5d-120">int</span></span>  <br/> |<span data-ttu-id="69a5d-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="69a5d-121">Foreign</span></span>  <br/> |<span data-ttu-id="69a5d-122">1: Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="69a5d-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="69a5d-123">2: a/v Conferencing Server16394: a/v Edge service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="69a5d-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="69a5d-124">**Poolname**</span><span class="sxs-lookup"><span data-stu-id="69a5d-124">**PoolName**</span></span> <br/> |<span data-ttu-id="69a5d-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="69a5d-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="69a5d-126">Pool, zu dem der Server gehört.</span><span class="sxs-lookup"><span data-stu-id="69a5d-126">Pool the server belongs to.</span></span> <span data-ttu-id="69a5d-127">Gilt nur für den A/V-Konferenz Server.</span><span class="sxs-lookup"><span data-stu-id="69a5d-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="69a5d-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="69a5d-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="69a5d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="69a5d-129">datetime</span></span>  <br/> ||<span data-ttu-id="69a5d-130">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="69a5d-130">For internal use only.</span></span>  <br/> |
   

