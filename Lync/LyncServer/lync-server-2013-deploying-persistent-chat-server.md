---
title: 'Lync Server 2013: Bereitstellen des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="975bf-102">Bereitstellen des Servers für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="975bf-103">_**Letztes Änderungsdatum des Themas:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="975bf-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="975bf-104">Lync Server 2013, beständiger Chat Server ist Teil der lync Server 2013-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="975bf-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="975bf-105">Für die Bereitstellung des beständigen Chat Servers müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="975bf-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="975bf-106">Verwenden Sie den Topologie-Generator, um Ihre Topologie und die Komponenten, die Sie bereitstellen möchten, zu definieren, zu importieren und anschließend zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="975bf-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="975bf-107">Bereiten Sie Ihre Umgebung für die Bereitstellung beständiger Chat Server Komponenten vor.</span><span class="sxs-lookup"><span data-stu-id="975bf-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="975bf-108">Installieren und konfigurieren Sie Komponenten für beständigen Chat Server für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="975bf-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="975bf-109">Der Server für beständigen Chat steht in lync Server 2013 Enterprise Edition als separater Pool zur Verfügung (nicht mit den Enterprise Edition-Front-End-Servern).</span><span class="sxs-lookup"><span data-stu-id="975bf-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="975bf-110">Der Server für beständigen Chat erfordert einen SQL Server-Back-End-Server in Ihrem Enterprise Edition-Pool, um den Chatroom-Inhalt und andere relevante Metadaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="975bf-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="975bf-111">Wir empfehlen, dass Sie die **PersistentChatStore** auf einem dedizierten SQL Server-Back-End-Server installieren, obwohl abstimmen lync Server 2013-Back-End-Server und **PersistentChatStore** auf derselben SQL Server-Instanz unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="975bf-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="975bf-112">Der Server für beständigen Chat kann auch mit lync Server 2013 Standard Edition bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="975bf-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="975bf-113">In diesem Fall befindet sich der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Computer, und der **PersistentChatStore** -Back-End-Server kann auf der lokalen SQL Server Express-Instanz bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="975bf-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="975bf-114">Ausführliche Informationen zu unterstützten Colocation-Konfigurationen finden Sie unter unterstützte Server setzungen [in lync Server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="975bf-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="975bf-115">Wir unterstützen keine höhere Verfügbarkeit für die Standard&nbsp;Edition für beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="975bf-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="975bf-116">Leistung und Skalierung sind limitiert.</span><span class="sxs-lookup"><span data-stu-id="975bf-116">Performance and scale will be limited.</span></span> <span data-ttu-id="975bf-117">Darüber hinaus unterstützen wir nur den neuen Server&nbsp;für beständigen Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="975bf-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="975bf-118">Wir unterstützen nicht das Upgrade von lync Server 2010, Gruppen-Chat Server auf eine&nbsp;lync Server 2013&nbsp;persistent Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="975bf-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="975bf-119">Wenn Ihre Organisation Compliance-Unterstützung erfordert, können Sie den beständigen Chat Server-Kompatibilitätsdienst auf dem Front-End-Server für beständigen Chat Server installieren.</span><span class="sxs-lookup"><span data-stu-id="975bf-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="975bf-120">Für die Compliance ist eine separate Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="975bf-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="975bf-121">Für jede Topologie ist mindestens ein Server mit lync Server 2013 und ein Server mit installierter SQL Server-Datenbanksoftware erforderlich.</span><span class="sxs-lookup"><span data-stu-id="975bf-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="975bf-122">Verwenden Sie den Topologie-Generator, um ihrer lync Server 2013-Bereitstellung beständigen Chat Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="975bf-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="975bf-123">Mithilfe des Topologie-Generators können Sie einen oder mehrere beständige Chat Server Pools hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="975bf-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="975bf-124">Befolgen Sie dieselben Bereitstellungsanweisungen für die Bereitstellung mehrerer beständiger Chat Server Pools, wie Sie dies für jeden Pool tun würden.</span><span class="sxs-lookup"><span data-stu-id="975bf-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="975bf-125">Ausführliche Informationen finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="975bf-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="975bf-126">Details zu verfügbaren Topologien sowie zu den technischen und Softwareanforderungen für die Installation von persistent Chat Server finden Sie unter Planen des beständigen [Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [Funktionsweise des beständigen Chat Servers in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation sowie [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="975bf-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="975bf-127">Details zum Abrufen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Datei speichern finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="975bf-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="975bf-128">Ein einzelner beständiger Chat Server-Front-End-Server kann 20.000-aktive Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="975bf-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="975bf-129">Sie können einen Server Pool für beständigen Chat mit bis zu vier aktiven Front-End-Servern mit insgesamt 80.000 gleichzeitigen Benutzern unterstützen.</span><span class="sxs-lookup"><span data-stu-id="975bf-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="975bf-130">Der Server für beständigen Chat wird auch auf einem virtuellen Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="975bf-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="975bf-131">Der virtuelle Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, wenn er den Spezifikationen des physikalischen Servers entspricht.</span><span class="sxs-lookup"><span data-stu-id="975bf-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="975bf-132">Der Server für beständigen Chat muss auf einem NTFS-Dateisystem installiert sein, um die Dateisystemsicherheit zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="975bf-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="975bf-133">FAT32 ist kein unterstütztes Dateisystem für beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="975bf-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="975bf-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="975bf-134">In This Section</span></span>

  - [<span data-ttu-id="975bf-135">Funktionsweise des beständigen Chat Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="975bf-136">Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="975bf-137">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="975bf-138">Einrichten der Systeme und Infrastruktur für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="975bf-139">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="975bf-140">Installieren des Servers für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="975bf-141">Hinzufügen eines Administrators für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="975bf-142">Konfigurieren des Servers für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="975bf-143">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="975bf-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="975bf-144">Problembehandlung bei der Konfiguration des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="975bf-145">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="975bf-146">Ausführen eines Failovers bzw. Failbacks für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="975bf-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

