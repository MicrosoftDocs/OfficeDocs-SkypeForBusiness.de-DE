---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prozess zum Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion.
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231343"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="d1c50-103">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="d1c50-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="d1c50-104">**In diesem Artikel**</span><span class="sxs-lookup"><span data-stu-id="d1c50-104">**In this article**</span></span>
  
[<span data-ttu-id="d1c50-105">Stellen Sie sicher, dass Skype für Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="d1c50-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="d1c50-106">Öffnen Sie die Skype für Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d1c50-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="d1c50-107">Versuchen Sie nicht, öffnen Sie die Topologie in der Vorversion Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="d1c50-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="d1c50-108">Nachdem Sie den pilotpool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools zu überprüfen, indem Sie mithilfe der Verwaltungstools die Poolinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1c50-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="d1c50-109">Für die Skype für Business Server 2019 Pools und legacypools müssen Sie die Skype für Business Server 2019-Systemsteuerung und Topologie-Generator-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1c50-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="d1c50-110">Stellen Sie sicher, dass Skype für Business Server 2019-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="d1c50-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="d1c50-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="d1c50-111"></span></span>

1. <span data-ttu-id="d1c50-112">Navigieren Sie aus der Skype für Business Server 2019 Front-End-Server zum Applet verwaltungstools\dienste.</span><span class="sxs-lookup"><span data-stu-id="d1c50-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="d1c50-113">Stellen Sie sicher, dass die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d1c50-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="d1c50-114">Zentralisierte Protokollierungs-Dienst-Agenten</span><span class="sxs-lookup"><span data-stu-id="d1c50-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="d1c50-115">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="d1c50-115">Application Sharing</span></span>
    - <span data-ttu-id="d1c50-116">Dienst zum Testen der Audioqualität</span><span class="sxs-lookup"><span data-stu-id="d1c50-116">Audio Test Service</span></span>
    - <span data-ttu-id="d1c50-117">A/v-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="d1c50-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="d1c50-118">Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="d1c50-118">Call Park</span></span>
    - <span data-ttu-id="d1c50-119">Konferenzankündigung</span><span class="sxs-lookup"><span data-stu-id="d1c50-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="d1c50-120">Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="d1c50-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="d1c50-121">Front-End-</span><span class="sxs-lookup"><span data-stu-id="d1c50-121">Front-End</span></span>
    - <span data-ttu-id="d1c50-122">Instant Messaging-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="d1c50-122">IM Conferencing</span></span>
    - <span data-ttu-id="d1c50-123">Vermittlungs-</span><span class="sxs-lookup"><span data-stu-id="d1c50-123">Mediation</span></span>
    - <span data-ttu-id="d1c50-124">Replikat Replikations-Agent</span><span class="sxs-lookup"><span data-stu-id="d1c50-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="d1c50-125">Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="d1c50-125">Response Group</span></span>
    - <span data-ttu-id="d1c50-126">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="d1c50-126">Web Conferencing</span></span>
    - <span data-ttu-id="d1c50-127">Übersetzen von XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="d1c50-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="d1c50-128">Öffnen Sie die Skype für Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d1c50-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="d1c50-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="d1c50-129"></span></span>

<span data-ttu-id="d1c50-130">Öffnen Sie von den Front-End-Server in Ihrer Skype für Business Server 2019 Bereitstellung der Skype Business Server 2019-Systemsteuerung zu, und wählen Sie Pool den Vorgängerversion.</span><span class="sxs-lookup"><span data-stu-id="d1c50-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="d1c50-131">Wiederholen Sie das Schritte aus, um die Skype für Business Server 2019 Pool zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d1c50-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1c50-132">In Skype für Business Server 2019 müssen Sie Silverlight auf Silverlight, Version 5, bevor Sie die Skype Business Server-Systemsteuerung verwenden upgraden.</span><span class="sxs-lookup"><span data-stu-id="d1c50-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="d1c50-133">Diese Topologie enthält nun Legacy und Skype für Business Server 2019 Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="d1c50-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="d1c50-134">Versuchen Sie nicht, öffnen Sie die Topologie in der Vorversion Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="d1c50-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="d1c50-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="d1c50-135"></span></span>

<span data-ttu-id="d1c50-136">Wenn Sie versuchen, die Topologie mithilfe des legacy-Topologie-Generators öffnen, treten Sie die unten angegebene Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="d1c50-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="d1c50-137">Die Topologie kann nur mithilfe der Skype für Business Server 2019 Topologie-Generator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1c50-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="d1c50-138">Zum Erstellen von Pools für Skype für Business Server 2019 und der Vorversion installieren, muss der Skype für Business Server 2019 Topologie-Generator verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1c50-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

