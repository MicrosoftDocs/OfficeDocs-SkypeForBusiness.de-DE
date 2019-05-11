---
title: NetworkConnectionDetail-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919991"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="f8d1a-104">NetworkConnectionDetail-Tabelle</span><span class="sxs-lookup"><span data-stu-id="f8d1a-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="f8d1a-105">NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="f8d1a-106">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f8d1a-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-107">**Column**</span></span>|<span data-ttu-id="f8d1a-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-108">**Data Type**</span></span>|<span data-ttu-id="f8d1a-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-109">**Key/Index**</span></span>|<span data-ttu-id="f8d1a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8d1a-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="f8d1a-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="f8d1a-112">tinyint</span></span>  <br/> |<span data-ttu-id="f8d1a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f8d1a-113">Primary</span></span>  <br/> |<span data-ttu-id="f8d1a-114">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="f8d1a-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="f8d1a-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="f8d1a-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="f8d1a-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="f8d1a-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="f8d1a-117">Unique</span></span>  <br/> |<span data-ttu-id="f8d1a-118">Typ der Netzwerkverbindung, die die NetworkConnectionDetailKey entspricht.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="f8d1a-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="f8d1a-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="f8d1a-120">0 – verkabelt</span><span class="sxs-lookup"><span data-stu-id="f8d1a-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="f8d1a-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="f8d1a-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="f8d1a-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="f8d1a-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="f8d1a-123">3 – MobileBB</span><span class="sxs-lookup"><span data-stu-id="f8d1a-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="f8d1a-124">4 – andere</span><span class="sxs-lookup"><span data-stu-id="f8d1a-124">4 -- Other</span></span>  <br/> <span data-ttu-id="f8d1a-125">5 – tunnel</span><span class="sxs-lookup"><span data-stu-id="f8d1a-125">5 -- Tunnel</span></span>  <br/> |
   

