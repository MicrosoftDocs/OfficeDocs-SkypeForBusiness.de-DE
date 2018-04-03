---
title: NetworkConnectionDetail-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="7c9bc-104">NetworkConnectionDetail-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7c9bc-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="7c9bc-105">NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c9bc-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="7c9bc-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c9bc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7c9bc-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-107">**Column**</span></span>|<span data-ttu-id="7c9bc-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-108">**Data Type**</span></span>|<span data-ttu-id="7c9bc-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-109">**Key/Index**</span></span>|<span data-ttu-id="7c9bc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7c9bc-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="7c9bc-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="7c9bc-112">tinyint</span></span>  <br/> |<span data-ttu-id="7c9bc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7c9bc-113">Primary</span></span>  <br/> |<span data-ttu-id="7c9bc-114">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="7c9bc-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="7c9bc-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="7c9bc-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="7c9bc-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="7c9bc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="7c9bc-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="7c9bc-117">Unique</span></span>  <br/> |<span data-ttu-id="7c9bc-118">Typ der Netzwerkverbindung, die die NetworkConnectionDetailKey entspricht.</span><span class="sxs-lookup"><span data-stu-id="7c9bc-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="7c9bc-119">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="7c9bc-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="7c9bc-120">0 – verkabelt</span><span class="sxs-lookup"><span data-stu-id="7c9bc-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="7c9bc-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="7c9bc-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="7c9bc-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="7c9bc-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="7c9bc-123">3 – MobileBB</span><span class="sxs-lookup"><span data-stu-id="7c9bc-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="7c9bc-124">4 – andere</span><span class="sxs-lookup"><span data-stu-id="7c9bc-124">4 -- Other</span></span>  <br/> <span data-ttu-id="7c9bc-125">5 – tunnel</span><span class="sxs-lookup"><span data-stu-id="7c9bc-125">5 -- Tunnel</span></span>  <br/> |
   

