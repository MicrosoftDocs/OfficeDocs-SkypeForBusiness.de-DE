---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="83f7d-102">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="83f7d-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83f7d-103">_**Letztes Änderungsdatum des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="83f7d-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="83f7d-104">Nachdem Sie den Pilot Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="83f7d-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="83f7d-105">Für die lync Server 2013-Pools und Legacy Pools müssen Sie die lync Server 2013-Systemsteuerung und die Tools für die Topologie-Builder verwenden.</span><span class="sxs-lookup"><span data-stu-id="83f7d-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="83f7d-106">Überprüfen, ob die lync Server 2013-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="83f7d-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="83f7d-107">Navigieren Sie vom lync Server 2013-Front-End-Server zum Applet\\Dienste für administrative Tools.</span><span class="sxs-lookup"><span data-stu-id="83f7d-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="83f7d-108">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="83f7d-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="83f7d-109">**Lync Server 2013-Dienste**</span><span class="sxs-lookup"><span data-stu-id="83f7d-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="83f7d-110">![Liste der gestarteten lync Server-Dienste](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste der gestarteten lync Server-Dienste")</span><span class="sxs-lookup"><span data-stu-id="83f7d-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="83f7d-111">Öffnen der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="83f7d-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="83f7d-112">Öffnen Sie auf dem Front-End-Server in ihrer lync Server 2013-Bereitstellung die lync Server 2013-Systemsteuerung, und wählen Sie den lync Server 2010-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="83f7d-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="83f7d-113">Wiederholen Sie den Vorgang, um den lync Server 2013-Pool zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83f7d-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="83f7d-114">**Öffnen der lync Server 2013-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="83f7d-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="83f7d-115">![Dialogfeld ' URL auswählen '](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Dialogfeld ' URL auswählen '")</span><span class="sxs-lookup"><span data-stu-id="83f7d-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83f7d-116">Bei lync Server 2013 müssen Sie Silverlight vor der Verwendung der lync Server-Systemsteuerung auf Silverlight, Version 5, aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="83f7d-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="83f7d-117">Diese Topologie umfasst jetzt lync Server 2010 und lync Server 2013-Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="83f7d-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="83f7d-118">**Lync Server 2013-Seite "Systemsteuerung"**</span><span class="sxs-lookup"><span data-stu-id="83f7d-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="83f7d-119">![Lync Server Control Panel – Seite "Topologie"](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel – Seite "Topologie"")</span><span class="sxs-lookup"><span data-stu-id="83f7d-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="83f7d-120">Versuchen Sie nicht, die Topologie im lync Server 2010-Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83f7d-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="83f7d-121">Wenn Sie versuchen, die Topologie mit lync Server 2010 Topology Builder zu öffnen, wird der folgende Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83f7d-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="83f7d-122">Die Topologie kann nur mit dem lync Server 2013-Topologie-Generator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="83f7d-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="83f7d-123">Der lync Server 2013-Topologie-Generator muss zum Erstellen von Pools für lync Server 2013 und lync Server 2010 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83f7d-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="83f7d-124">**Fehlermeldung zum lync Server 2010-Topologie-Generator**</span><span class="sxs-lookup"><span data-stu-id="83f7d-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="83f7d-125">![MMC-Snap-Fehler in lync Server Topology Builder](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "MMC-Snap-Fehler in lync Server Topology Builder")</span><span class="sxs-lookup"><span data-stu-id="83f7d-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

