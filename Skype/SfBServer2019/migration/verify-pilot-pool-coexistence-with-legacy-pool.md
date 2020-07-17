---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prozess zum Überprüfen der Koexistenz von pilotpools mit dem Legacy Pool.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751657"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="6756a-103">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="6756a-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="6756a-104">**Inhalt dieses Artikels**</span><span class="sxs-lookup"><span data-stu-id="6756a-104">**In this article**</span></span>
  
[<span data-ttu-id="6756a-105">Sicherstellen, dass Skype for Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="6756a-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="6756a-106">Öffnen der Systemsteuerung von Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6756a-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="6756a-107">Versuchen Sie nicht, die Topologie im Legacy Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6756a-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="6756a-108">Nachdem Sie den Pilot-Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6756a-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="6756a-109">Für Skype for Business Server 2019-Pools und Legacy Pools müssen Sie die Skype for Business Server 2019-Systemsteuerung und die Topologie-Generator-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="6756a-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="6756a-110">Sicherstellen, dass Skype for Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="6756a-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="6756a-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="6756a-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="6756a-112">Navigieren Sie im Skype for Business Server 2019 Front-End-Server zum Applet für administrative verwaltungstools\dienste..</span><span class="sxs-lookup"><span data-stu-id="6756a-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="6756a-113">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6756a-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="6756a-114">Zentraler Protokollierungsdienst-Agent</span><span class="sxs-lookup"><span data-stu-id="6756a-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="6756a-115">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="6756a-115">Application Sharing</span></span>
    - <span data-ttu-id="6756a-116">Audio-Test Dienst</span><span class="sxs-lookup"><span data-stu-id="6756a-116">Audio Test Service</span></span>
    - <span data-ttu-id="6756a-117">Audio/Video Konferenzen</span><span class="sxs-lookup"><span data-stu-id="6756a-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="6756a-118">Funktion zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="6756a-118">Call Park</span></span>
    - <span data-ttu-id="6756a-119">Konferenzankündigung</span><span class="sxs-lookup"><span data-stu-id="6756a-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="6756a-120">Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="6756a-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="6756a-121">Front-End</span><span class="sxs-lookup"><span data-stu-id="6756a-121">Front-End</span></span>
    - <span data-ttu-id="6756a-122">Chat Konferenzen</span><span class="sxs-lookup"><span data-stu-id="6756a-122">IM Conferencing</span></span>
    - <span data-ttu-id="6756a-123">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="6756a-123">Mediation</span></span>
    - <span data-ttu-id="6756a-124">Replikat Replikationsdienst-Agent</span><span class="sxs-lookup"><span data-stu-id="6756a-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="6756a-125">Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="6756a-125">Response Group</span></span>
    - <span data-ttu-id="6756a-126">Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="6756a-126">Web Conferencing</span></span>
    - <span data-ttu-id="6756a-127">XMPP-Übersetzungs Gateway</span><span class="sxs-lookup"><span data-stu-id="6756a-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="6756a-128">Öffnen der Systemsteuerung von Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6756a-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="6756a-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="6756a-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="6756a-130">Öffnen Sie in der Front-End-Server Skype for Business Server 2019-Bereitstellung die Skype for Business Server 2019-Systemsteuerung, und wählen Sie den Pool Legacy aus.</span><span class="sxs-lookup"><span data-stu-id="6756a-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="6756a-131">Wiederholen Sie den Vorgang, um den Pool Skype for Business Server 2019 zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6756a-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6756a-132">Auf Skype for Business Server 2019 müssen Sie Silverlight auf Silverlight, Version 5 aktualisieren, bevor Sie die Skype for Business Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="6756a-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="6756a-133">Diese Topologie umfasst nun Legacy-und Skype for Business Server 2019-Server Rollen.</span><span class="sxs-lookup"><span data-stu-id="6756a-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="6756a-134">Versuchen Sie nicht, die Topologie im Legacy Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6756a-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="6756a-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="6756a-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="6756a-136">Die Topologie kann nur mit Skype for Business Server 2019-Topologie-Generator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6756a-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="6756a-137">Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools sowohl für Skype for Business Server 2019 als auch für die Legacy Installation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6756a-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

