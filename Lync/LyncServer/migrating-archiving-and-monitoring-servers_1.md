---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="fcf6d-102">Migrieren von Archivierungsservern und Monitoring Servern</span><span class="sxs-lookup"><span data-stu-id="fcf6d-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcf6d-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fcf6d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fcf6d-104">Wenn Sie Archivierungsserver und Monitoring Server in Ihrem Office Communications Server 2007 R2 bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013 Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="fcf6d-105">Wenn Archivierungs- und Überwachungsfunktionen in Ihrer Organisation jedoch entscheidend sind, sollten Sie Ihrem Pilotpool vor der Migration Archivierungsserver und Monitoring Server hinzufügen, damit diese Funktionen auch während des Migrationsvorgangs zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="fcf6d-106">Wenn Sie während der Phase der Migration und Koexistenz Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="fcf6d-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="fcf6d-107">Das Archivieren von Daten und Überwachungsdaten wird nicht in die lync Server 2013-Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="fcf6d-108">Die Daten, die Sie vor der Außerbetriebnahme der Vorgänger Umgebung sichern, sind Ihre Aktivitätshistorie im Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="fcf6d-109">Die Office Communications Server 2007 R2 Version von Archivierungsserver und Monitoring Server kann nur einem Office Communications Server 2007 R2 Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="fcf6d-110">In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die lync Server 2013 Front-End-Pool integriert sind.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="fcf6d-111">Während der Koexistenz Ihrer Legacy-und lync Server 2013-Bereitstellungen werden die Office Communications Server 2007 R2-Version von Archivierungsserver und Monitoring Server Daten für Benutzer sammeln, die in Office Communications Server 2007 R2 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="fcf6d-112">Die lync Server 2013 Version von Archivierungsserver und Monitoring Server sammeln von Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcf6d-113">Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die Office Communications Server 2007 R2 Version von Archivierungsserver weiterhin Daten für Benutzer, die in Office Communications Server 2007 R2 Pools verwaltet werden, und die lync Server 2013 Version von Archivierungsserver sammelt Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="fcf6d-114">Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit Archivierungsserver und Monitoring Server verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit lync Server 2013 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fcf6d-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

