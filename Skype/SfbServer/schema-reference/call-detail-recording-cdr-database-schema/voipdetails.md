---
title: VoIPDetails-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, wobei mindestens ein Benutzer einen VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="6c644-104">VoIPDetails-Ansicht</span><span class="sxs-lookup"><span data-stu-id="6c644-104">VoIPDetails view</span></span>
 
<span data-ttu-id="6c644-105">Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, wobei mindestens ein Benutzer einen VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="6c644-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="6c644-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6c644-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c644-107">Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) außerdem die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="6c644-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="6c644-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6c644-108">**Column**</span></span>|<span data-ttu-id="6c644-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6c644-109">**Data Type**</span></span>|<span data-ttu-id="6c644-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6c644-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c644-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="6c644-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="6c644-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c644-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c644-113">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6c644-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="6c644-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="6c644-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c644-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c644-116">Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6c644-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="6c644-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="6c644-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c644-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c644-119">Der URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6c644-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="6c644-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="6c644-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-122">Typ der URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6c644-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="6c644-123">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="6c644-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6c644-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="6c644-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="6c644-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-126">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6c644-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="6c644-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="6c644-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c644-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c644-129">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6c644-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="6c644-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="6c644-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-132">Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="6c644-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="6c644-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="6c644-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-135">Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="6c644-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="6c644-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="6c644-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-138">Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="6c644-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6c644-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="6c644-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="6c644-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c644-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c644-141">Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="6c644-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

