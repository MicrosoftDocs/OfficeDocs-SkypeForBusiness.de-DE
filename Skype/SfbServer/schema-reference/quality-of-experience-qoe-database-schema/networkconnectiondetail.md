---
title: NetworkConnectionDetail-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindungs Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294817"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="c9575-104">NetworkConnectionDetail-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c9575-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="c9575-105">Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindungs Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9575-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="c9575-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c9575-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c9575-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c9575-107">**Column**</span></span>|<span data-ttu-id="c9575-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c9575-108">**Data Type**</span></span>|<span data-ttu-id="c9575-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="c9575-109">**Key/Index**</span></span>|<span data-ttu-id="c9575-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="c9575-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9575-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="c9575-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="c9575-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9575-112">tinyint</span></span>  <br/> |<span data-ttu-id="c9575-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c9575-113">Primary</span></span>  <br/> |<span data-ttu-id="c9575-114">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="c9575-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="c9575-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="c9575-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="c9575-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9575-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="c9575-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="c9575-117">Unique</span></span>  <br/> |<span data-ttu-id="c9575-118">Der Netzwerkverbindungstyp, der dem NetworkConnectionDetailKey-Element entspricht.</span><span class="sxs-lookup"><span data-stu-id="c9575-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="c9575-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c9575-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="c9575-120">0-verkabelt</span><span class="sxs-lookup"><span data-stu-id="c9575-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="c9575-121">1 – WiFi</span><span class="sxs-lookup"><span data-stu-id="c9575-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="c9575-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="c9575-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="c9575-123">3-MobileBB</span><span class="sxs-lookup"><span data-stu-id="c9575-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="c9575-124">4--Sonstige</span><span class="sxs-lookup"><span data-stu-id="c9575-124">4 -- Other</span></span>  <br/> <span data-ttu-id="c9575-125">5 – Tunnel</span><span class="sxs-lookup"><span data-stu-id="c9575-125">5 -- Tunnel</span></span>  <br/> |
   

