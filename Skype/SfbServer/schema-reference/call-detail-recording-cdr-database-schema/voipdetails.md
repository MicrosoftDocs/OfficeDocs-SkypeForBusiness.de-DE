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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814773"
---
# <a name="voipdetails-view"></a><span data-ttu-id="cadda-104">VoIPDetails-Ansicht</span><span class="sxs-lookup"><span data-stu-id="cadda-104">VoIPDetails view</span></span>
 
<span data-ttu-id="cadda-105">In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="cadda-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="cadda-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cadda-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cadda-107">Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="cadda-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="cadda-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cadda-108">**Column**</span></span>|<span data-ttu-id="cadda-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cadda-109">**Data Type**</span></span>|<span data-ttu-id="cadda-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="cadda-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cadda-111">**Vom Telefon**</span><span class="sxs-lookup"><span data-stu-id="cadda-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="cadda-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cadda-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cadda-113">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-114">**Tophone**</span><span class="sxs-lookup"><span data-stu-id="cadda-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="cadda-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cadda-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cadda-116">Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cadda-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="cadda-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="cadda-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cadda-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cadda-119">Der URI des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="cadda-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="cadda-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-122">Der Typ des URIs des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="cadda-123">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="cadda-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cadda-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="cadda-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="cadda-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-126">Der Mandant des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="cadda-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="cadda-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cadda-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cadda-129">Telefon-URI des Benutzers, der die Sitzung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="cadda-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="cadda-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-132">Der von dem Benutzer, der die Sitzung gestartet hat, verwendete Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="cadda-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="cadda-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="cadda-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-135">Vermittlungs Server, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cadda-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="cadda-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="cadda-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-138">Gateway, das vom Benutzer verwendet wird, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="cadda-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="cadda-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="cadda-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="cadda-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cadda-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cadda-141">Gateway, das vom Benutzer verwendet wird, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cadda-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

