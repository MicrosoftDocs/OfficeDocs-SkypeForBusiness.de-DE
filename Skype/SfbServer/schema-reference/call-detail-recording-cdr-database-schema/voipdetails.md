---
title: VoIPDetails-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295664"
---
# <a name="voipdetails-view"></a><span data-ttu-id="9fd9a-104">VoIPDetails-Ansicht</span><span class="sxs-lookup"><span data-stu-id="9fd9a-104">VoIPDetails view</span></span>
 
<span data-ttu-id="9fd9a-105">In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="9fd9a-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fd9a-107">Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="9fd9a-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-108">**Column**</span></span>|<span data-ttu-id="9fd9a-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-109">**Data Type**</span></span>|<span data-ttu-id="9fd9a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9fd9a-111">**Vom Telefon**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="9fd9a-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9fd9a-113">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-114">**Tophone**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="9fd9a-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9fd9a-116">Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="9fd9a-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9fd9a-119">Der URI des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="9fd9a-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-122">Der Typ des URIs des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="9fd9a-123">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd9a-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9fd9a-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="9fd9a-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-126">Der Mandant des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="9fd9a-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9fd9a-129">Telefon-URI des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="9fd9a-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-132">Der von dem Benutzer, der die Sitzung gestartet hat, verwendete Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="9fd9a-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-135">Vermittlungs Server, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="9fd9a-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-138">Gateway, das vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="9fd9a-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="9fd9a-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="9fd9a-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fd9a-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fd9a-141">Gateway, das vom Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9fd9a-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

