---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ee191-102">Migrieren von Archivierungsservern und Monitoring Servern</span><span class="sxs-lookup"><span data-stu-id="ee191-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee191-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ee191-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ee191-104">Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer lync Server 2010-Umgebung bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben.</span><span class="sxs-lookup"><span data-stu-id="ee191-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ee191-105">Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch dem lync Server 2013-Pilot Pool Archivierungs-und Überwachungsvorgänge hinzufügen, bevor Sie migrieren, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="ee191-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="ee191-106">Wenn Sie während des Migrationsprozesses Archivierungs-und Überwachungsfunktionen wünschen, sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="ee191-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="ee191-107">Archivierungsdaten und Überwachungsdaten werden nicht in die lync Server 2013-Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="ee191-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ee191-108">Die Daten, die Sie vor dem Stilllegen der Legacyumgebung sichern, sind Ihr Aktivitätsverlauf in der lync Server 2010-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ee191-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="ee191-109">Die lync Server 2010-Version des Archivierungsservers und des Überwachungsservers kann nur einem lync Server 2010-Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ee191-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="ee191-110">In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in den Front-End-Pool von lync Server 2013 integriert sind.</span><span class="sxs-lookup"><span data-stu-id="ee191-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="ee191-111">In der Zeit, in der Ihre Legacy-und lync Server 2013-Bereitstellungen koexistieren, sammeln die lync Server 2010-Version des Archivierungsservers und des Überwachungsservers Daten für Benutzer, die in lync Server 2010-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ee191-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="ee191-112">Archivierung und Überwachung in lync Server 2013 sammeln Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ee191-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ee191-113">Während der Migrationsphase, wenn Sie Ihren Legacy-Edgeserver weiterhin mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die lync Server 2010-Version des Archivierungsservers weiterhin Daten für Benutzer, die in lync Server 2010-Pools und-Archivierung in lync Server 2013 verwaltet werden. sammelt Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ee191-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="ee191-114">Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in lync Server 2013 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Lösung eines Drittanbieters in lync Server 2013 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ee191-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

