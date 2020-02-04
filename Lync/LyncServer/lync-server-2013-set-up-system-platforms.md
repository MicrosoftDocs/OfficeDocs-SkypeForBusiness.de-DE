---
title: 'Lync Server 2013: Einrichten von Systemplattformen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="76f6b-102">Einrichten von Systemplattformen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76f6b-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="76f6b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="76f6b-104">Bevor Sie die Bereitstellung des beständigen Chat Servers starten, müssen Sie das erforderliche Betriebssystem auf Hardware installieren, die den Systemanforderungen auf Servern entspricht:</span><span class="sxs-lookup"><span data-stu-id="76f6b-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="76f6b-105">Details zur unterstützten Hardware für Server mit lync Server 2013, Datenbankservern und Dateiservern finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="76f6b-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="76f6b-106">Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware finden Sie unter Unterstützung für [Server Software und-Infrastruktur in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="76f6b-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="76f6b-107">Details zu den Windows Update-Anforderungen finden Sie unter [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="76f6b-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="76f6b-108">Der beständige Chat Server-Front-End-Server, **PersistentChatService**, kann auf einem oder mehreren eigenständigen Computern in einem lync Server 2013 Enterprise Edition-Pool bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76f6b-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="76f6b-109">Sie können nicht auf den lync Server Enterprise Edition-Front-End-Servern zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76f6b-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="76f6b-110">Der Server für beständigen Chat kann vom Bootstrapper bereitgestellt werden, genau wie andere lync-Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="76f6b-111">Die **beständigen Chat-Webdienste für Datei Upload/-Download**und **beständige Chat-Webdienste für die chatroomverwaltung** sind Webkomponenten, die auf den lync Server 2013-Front-End-Servern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76f6b-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="76f6b-112">Ein einzelner beständiger Chat Server-Front-End-Server kann 20.000-aktive Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="76f6b-113">Sie können einen Server Pool für beständigen Chat mit bis zu vier aktiven Front-Ends haben, der insgesamt 80.000 gleichzeitige Benutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="76f6b-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="76f6b-114">Der beständige Chat-Back-End-Server, **PersistentChatStore**, speichert die Chatrooms und Kategorien.</span><span class="sxs-lookup"><span data-stu-id="76f6b-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="76f6b-115">Wir empfehlen, die **PersistentChatStore** auf einem dedizierten SQL Server-Back-End-Server in Ihrem Enterprise Edition-Pool zu installieren. Obwohl wir abstimmen lync Server 2013-Back-End-Server und- **PersistentChatStore** auf derselben SQL Server-Instanz unterstützen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="76f6b-116">Wenn Ihre Organisation Compliance-Unterstützung erfordert, können Sie Sie mithilfe des Topologie-Generators installieren.</span><span class="sxs-lookup"><span data-stu-id="76f6b-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="76f6b-117">Der beständige Chat Server-Kompatibilitätsdienst ist auf demselben Computer wie der Front-End-Server des beständigen Chat Servers installiert.</span><span class="sxs-lookup"><span data-stu-id="76f6b-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="76f6b-118">Für die Compliance ist eine separate Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76f6b-118">A separate database is required for compliance.</span></span> <span data-ttu-id="76f6b-119">Ausführliche Informationen zu den Konformitätsanforderungen für den Server für beständigen Chat finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76f6b-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="76f6b-120">Für jede Topologie ist mindestens ein Server mit lync Server 2013 und ein Server mit installierter SQL Server-Datenbanksoftware erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76f6b-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="76f6b-121">Der Topologie-Generator unterstützt mehrere beständige Chat Server Pools.</span><span class="sxs-lookup"><span data-stu-id="76f6b-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="76f6b-122">Befolgen Sie die gleichen Bereitstellungsanweisungen für die Bereitstellung mehrerer beständiger Chat Server Pools wie für jeden Pool, wenn Sie [lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="76f6b-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="76f6b-123">Sie können den Server für beständigen Chat auch mit lync Server 2013 Standard Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="76f6b-124">In diesem Fall befindet sich der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Server, und Sie können den **PersistentChatStore** -Back-End-Server auf der lokalen SQL Server Express-Instanz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="76f6b-125">Wir unterstützen keine persistent Chat Server&nbsp;Standard Edition für eine höhere Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="76f6b-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="76f6b-126">Leistung und Skalierung sind limitiert.</span><span class="sxs-lookup"><span data-stu-id="76f6b-126">Performance and scale will be limited.</span></span> <span data-ttu-id="76f6b-127">Darüber hinaus unterstützen wir nur neue Server Bereitstellungen für beständigen Chat Server&nbsp;-Standard Editionen.</span><span class="sxs-lookup"><span data-stu-id="76f6b-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="76f6b-128">Wir unterstützen kein Upgrade von lync Server 2010, Gruppen-Chat Server auf eine lync Server 2013&nbsp;persistent Chat Server&nbsp;Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="76f6b-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76f6b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76f6b-129">See Also</span></span>


[<span data-ttu-id="76f6b-130">Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="76f6b-131">Unterstützte Hardware für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="76f6b-132">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="76f6b-133">Planen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="76f6b-134">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f6b-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

