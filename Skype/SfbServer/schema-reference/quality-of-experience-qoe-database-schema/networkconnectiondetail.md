---
title: NetworkConnectionDetail-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212390"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="3eb62-104">NetworkConnectionDetail-Tabelle</span><span class="sxs-lookup"><span data-stu-id="3eb62-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="3eb62-105">NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="3eb62-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3eb62-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3eb62-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3eb62-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3eb62-107">**Column**</span></span>|<span data-ttu-id="3eb62-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="3eb62-108">**Data Type**</span></span>|<span data-ttu-id="3eb62-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="3eb62-109">**Key/Index**</span></span>|<span data-ttu-id="3eb62-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="3eb62-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3eb62-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="3eb62-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="3eb62-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="3eb62-112">tinyint</span></span>  <br/> |<span data-ttu-id="3eb62-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3eb62-113">Primary</span></span>  <br/> |<span data-ttu-id="3eb62-114">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="3eb62-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="3eb62-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="3eb62-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="3eb62-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="3eb62-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="3eb62-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="3eb62-117">Unique</span></span>  <br/> |<span data-ttu-id="3eb62-118">Typ der Netzwerkverbindung, die die NetworkConnectionDetailKey entspricht.</span><span class="sxs-lookup"><span data-stu-id="3eb62-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="3eb62-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3eb62-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="3eb62-120">0 – verkabelt</span><span class="sxs-lookup"><span data-stu-id="3eb62-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="3eb62-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="3eb62-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="3eb62-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="3eb62-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="3eb62-123">3 – MobileBB</span><span class="sxs-lookup"><span data-stu-id="3eb62-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="3eb62-124">4 – andere</span><span class="sxs-lookup"><span data-stu-id="3eb62-124">4 -- Other</span></span>  <br/> <span data-ttu-id="3eb62-125">5 – tunnel</span><span class="sxs-lookup"><span data-stu-id="3eb62-125">5 -- Tunnel</span></span>  <br/> |
   

