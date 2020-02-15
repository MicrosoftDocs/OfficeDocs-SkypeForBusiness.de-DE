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
ms.openlocfilehash: eda0cebf15cb1d575978eb0984dc7d9b5a53a30f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="acc5e-102">Einrichten von Systemplattformen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acc5e-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="acc5e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="acc5e-104">Bevor Sie mit der Bereitstellung des Servers für beständigen Chat beginnen, müssen Sie das erforderliche Betriebssystem auf Hardware installieren, die die Systemanforderungen auf Servern erfüllt:</span><span class="sxs-lookup"><span data-stu-id="acc5e-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="acc5e-105">Ausführliche Informationen zur unterstützten Hardware für Server, auf denen lync Server 2013, Datenbankserver und Dateiserver auszuführen sind, finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="acc5e-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="acc5e-106">Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware finden Sie unter [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="acc5e-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="acc5e-107">Ausführliche Informationen zu den Windows Update-Anforderungen finden Sie unter [zusätzliche Server Unterstützung und Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="acc5e-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="acc5e-108">Der Server für beständigen Chat Front-End-Server **PersistentChatService**kann auf einem oder mehreren eigenständigen Computern in einem lync Server 2013 Enterprise Edition-Pool bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="acc5e-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="acc5e-109">Sie können nicht auf den lync Server Enterprise Edition-Front-End-Servern zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="acc5e-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="acc5e-110">Der Server für beständigen Chat kann vom Bootstrapper bereitgestellt werden, genau wie bei anderen lync Server Rollen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="acc5e-111">Die **Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien**und den **beständigen Chat Webdienste für die chatroomverwaltung** sind auf den lync Server 2013-Front-End-Servern bereitgestellte Webkomponenten.</span><span class="sxs-lookup"><span data-stu-id="acc5e-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="acc5e-112">Eine einzelne Server Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="acc5e-113">Sie können einen Server Pool für beständigen Chat mit bis zu 4 aktiven Front-Ends mit einer Gesamtzahl von 80.000 gleichzeitigen Benutzern unterstützen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="acc5e-114">Auf dem Back-End-Server für beständigen Chat, **PersistentChatStore**, werden die Chatrooms und Kategorien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="acc5e-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="acc5e-115">Es wird empfohlen, das **PersistentChatStore** auf einem dedizierten SQL Server Back-End-Server im Enterprise Edition-Pool zu installieren. Obwohl wir abstimmen lync Server 2013 Back-End-Server und **PersistentChatStore** auf derselben SQL Server-Instanz unterstützen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="acc5e-116">Wenn Ihre Organisation Compliance-Unterstützung benötigt, können Sie Sie mithilfe des Topologie-Generators installieren.</span><span class="sxs-lookup"><span data-stu-id="acc5e-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="acc5e-117">Der Kompatibilitätsdienst für den Server für beständigen Chat wird auf demselben Computer wie der Server für beständigen Chat Front-End-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="acc5e-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="acc5e-118">Für die Konformität ist eine separate Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="acc5e-118">A separate database is required for compliance.</span></span> <span data-ttu-id="acc5e-119">Ausführliche Informationen zu den Kompatibilitätsanforderungen für den Server für beständigen Chat finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="acc5e-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="acc5e-120">Für jede Topologie ist mindestens ein Server mit installierter lync Server 2013 und ein Server mit SQL Server-Datenbanksoftware erforderlich.</span><span class="sxs-lookup"><span data-stu-id="acc5e-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="acc5e-121">Der Topologie-Generator unterstützt mehrere Server Pools für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="acc5e-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="acc5e-122">Befolgen Sie die gleichen Bereitstellungsanweisungen für die Bereitstellung mehrerer Server Pools für beständigen Chat wie für jeden Pool, wenn Sie lync Server 2013 in der Bereitstellungsdokumentation [Bereitstellen](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="acc5e-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="acc5e-123">Sie können auch den Server für beständigen Chat mit lync Server 2013 Standard Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="acc5e-124">In diesem Fall wird der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Server zusammengestellt, und Sie können den **PersistentChatStore** -Back-End-Server auf der lokalen SQL Server Express Instanz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acc5e-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="acc5e-125">Wir unterstützen keine persistent Chat Server&nbsp;Standard Edition für hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="acc5e-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="acc5e-126">Leistung und Skalierung sind eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="acc5e-126">Performance and scale will be limited.</span></span> <span data-ttu-id="acc5e-127">Darüber hinaus werden nur neue Server&nbsp;für beständigen Chat Standard Edition-Server-Bereitstellungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="acc5e-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="acc5e-128">Wir unterstützen kein Upgrade von lync Server 2010, Gruppen Chat Server auf eine lync Server 2013&nbsp;persistent Chat Server&nbsp;Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="acc5e-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acc5e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acc5e-129">See Also</span></span>


[<span data-ttu-id="acc5e-130">Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="acc5e-131">Unterstützte Hardware für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="acc5e-132">Server Software und Infrastrukturunterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="acc5e-133">Planen von Servern für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="acc5e-134">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc5e-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

