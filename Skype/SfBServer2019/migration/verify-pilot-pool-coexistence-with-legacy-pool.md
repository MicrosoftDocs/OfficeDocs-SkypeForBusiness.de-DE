---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prozess zur Überprüfung der Koexistenz von pilotpools mit Legacy Pool
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243750"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="9a0a1-103">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="9a0a1-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="9a0a1-104">**In diesem Artikel**</span><span class="sxs-lookup"><span data-stu-id="9a0a1-104">**In this article**</span></span>
  
[<span data-ttu-id="9a0a1-105">Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="9a0a1-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="9a0a1-106">Öffnen der Systemsteuerung von Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9a0a1-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="9a0a1-107">Versuchen Sie nicht, die Topologie im Legacy Topology Builder zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="9a0a1-108">Nachdem Sie den Pilot Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="9a0a1-109">Für die Skype for Business Server 2019-Pools und Legacy-Pools müssen Sie die Skype for Business Server 2019 Control Panel-und Topology Builder-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="9a0a1-110">Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="9a0a1-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="9a0a1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9a0a1-111"></span></span>

1. <span data-ttu-id="9a0a1-112">Navigieren Sie im Skype for Business Server 2019-Front-End-Server zum Administrator Tools\Services-Applet.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="9a0a1-113">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9a0a1-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="9a0a1-114">Zentralisierter Protokollierungsdienst-Agent</span><span class="sxs-lookup"><span data-stu-id="9a0a1-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="9a0a1-115">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="9a0a1-115">Application Sharing</span></span>
    - <span data-ttu-id="9a0a1-116">Audiotestdienst</span><span class="sxs-lookup"><span data-stu-id="9a0a1-116">Audio Test Service</span></span>
    - <span data-ttu-id="9a0a1-117">Audio/Video Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9a0a1-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="9a0a1-118">Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="9a0a1-118">Call Park</span></span>
    - <span data-ttu-id="9a0a1-119">Konferenzankündigung</span><span class="sxs-lookup"><span data-stu-id="9a0a1-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="9a0a1-120">Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="9a0a1-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="9a0a1-121">Front-End</span><span class="sxs-lookup"><span data-stu-id="9a0a1-121">Front-End</span></span>
    - <span data-ttu-id="9a0a1-122">Chat Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9a0a1-122">IM Conferencing</span></span>
    - <span data-ttu-id="9a0a1-123">Vermittlungs-</span><span class="sxs-lookup"><span data-stu-id="9a0a1-123">Mediation</span></span>
    - <span data-ttu-id="9a0a1-124">Replica Replicator-Agent</span><span class="sxs-lookup"><span data-stu-id="9a0a1-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="9a0a1-125">Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="9a0a1-125">Response Group</span></span>
    - <span data-ttu-id="9a0a1-126">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="9a0a1-126">Web Conferencing</span></span>
    - <span data-ttu-id="9a0a1-127">XMPP-Übersetzungs Gateway</span><span class="sxs-lookup"><span data-stu-id="9a0a1-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="9a0a1-128">Öffnen der Systemsteuerung von Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9a0a1-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="9a0a1-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="9a0a1-129"></span></span>

<span data-ttu-id="9a0a1-130">Öffnen Sie auf dem Front-End-Server in Ihrer Skype for Business Server 2019-Bereitstellung die Systemsteuerung von Skype for Business Server 2019, und wählen Sie den Legacy Pool aus.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="9a0a1-131">Wiederholen Sie den Vorgang zum Öffnen des Skype for Business Server 2019-Pools.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a0a1-132">Bei Skype for Business Server 2019 müssen Sie Silverlight auf Silverlight Version 5 aktualisieren, bevor Sie die Skype for Business Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="9a0a1-133">Diese Topologie umfasst jetzt Legacy-und Skype for Business Server 2019-Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="9a0a1-134">Versuchen Sie nicht, die Topologie im Legacy Topology Builder zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="9a0a1-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="9a0a1-135"></span></span>

<span data-ttu-id="9a0a1-136">Die Topologie kann nur mit dem Skype for Business Server 2019-Topologie-Generator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="9a0a1-137">Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools für Skype for Business Server 2019 und die Legacy Installation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a0a1-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

