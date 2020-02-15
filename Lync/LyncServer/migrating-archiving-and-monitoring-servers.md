---
title: Migrieren von Archivierungs-und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f201b1f7520b365654635c61e4fcebae3c46a0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="3b424-102">Migrieren von Archivierungs-und Monitoring Servern</span><span class="sxs-lookup"><span data-stu-id="3b424-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b424-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3b424-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3b424-104">Wenn Sie Archivierungsserver und Monitoring Server in ihrer lync Server 2010 Umgebung bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013 Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben.</span><span class="sxs-lookup"><span data-stu-id="3b424-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="3b424-105">Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration die Archivierung und Überwachung zu Ihrem lync Server 2013 Pilot-Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="3b424-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="3b424-106">Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="3b424-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="3b424-107">Das Archivieren von Daten und Überwachungsdaten wird nicht in die lync Server 2013-Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="3b424-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="3b424-108">Die Daten, die Sie vor der Außerbetriebsetzung der Vorversionsumgebung sichern, sind Bestandteil der aufgezeichneten Aktivitäten der Lync Server 2010-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="3b424-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="3b424-109">Die lync Server 2010 Version von Archivierungsserver und Monitoring Server kann nur einem lync Server 2010 Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3b424-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="3b424-110">In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die lync Server 2013 Front-End-Pool integriert sind.</span><span class="sxs-lookup"><span data-stu-id="3b424-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="3b424-111">Während der Koexistenz Ihrer Legacy-und lync Server 2013-Bereitstellungen werden die lync Server 2010-Version von Archivierungsserver und Monitoring Server Daten für Benutzer sammeln, die in lync Server 2010 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3b424-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="3b424-112">Archivierung und Überwachung in lync Server 2013 Sammeln von Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3b424-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b424-113">Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die lync Server 2010 Version von Archivierungsserver weiterhin Daten für Benutzer, die in lync Server 2010 Pools verwaltet werden und in lync Server 2013 archiviert werden. sammelt Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3b424-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="3b424-114">Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in lync Server 2013 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit lync Server 2013 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="3b424-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

