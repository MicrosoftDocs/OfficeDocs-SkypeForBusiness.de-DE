---
title: NetworkConnectionDetail table
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database. This table was introduced in Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="0c5d0-104">NetworkConnectionDetail table</span><span class="sxs-lookup"><span data-stu-id="0c5d0-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="0c5d0-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span><span class="sxs-lookup"><span data-stu-id="0c5d0-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="0c5d0-106">This table was introduced in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c5d0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="0c5d0-107">**Column**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-107">**Column**</span></span>|<span data-ttu-id="0c5d0-108">**Data Type**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-108">**Data Type**</span></span>|<span data-ttu-id="0c5d0-109">**Key/Index**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-109">**Key/Index**</span></span>|<span data-ttu-id="0c5d0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c5d0-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="0c5d0-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="0c5d0-112">tinyint</span></span>  <br/> |<span data-ttu-id="0c5d0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0c5d0-113">Primary</span></span>  <br/> |<span data-ttu-id="0c5d0-114">Unique identifier for the network connection type.</span><span class="sxs-lookup"><span data-stu-id="0c5d0-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="0c5d0-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="0c5d0-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="0c5d0-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c5d0-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="0c5d0-117">Unique</span><span class="sxs-lookup"><span data-stu-id="0c5d0-117">Unique</span></span>  <br/> |<span data-ttu-id="0c5d0-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="0c5d0-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="0c5d0-119">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="0c5d0-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="0c5d0-120">0 -- Wired</span><span class="sxs-lookup"><span data-stu-id="0c5d0-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="0c5d0-121">1 -- WiFi</span><span class="sxs-lookup"><span data-stu-id="0c5d0-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="0c5d0-122">2 -- Ethernet</span><span class="sxs-lookup"><span data-stu-id="0c5d0-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="0c5d0-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="0c5d0-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="0c5d0-124">4 -- Other</span><span class="sxs-lookup"><span data-stu-id="0c5d0-124">4 -- Other</span></span>  <br/> <span data-ttu-id="0c5d0-125">5 -- Tunnel</span><span class="sxs-lookup"><span data-stu-id="0c5d0-125">5 -- Tunnel</span></span>  <br/> |
   

