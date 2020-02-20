---
title: 'Lync Server 2013: Bereitstellen des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cbe07-102">Bereitstellen des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbe07-103">_**Letztes Änderungsstand des Themas:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="cbe07-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="cbe07-104">Lync Server 2013 ist der Server für beständigen Chat Teil der lync Server 2013-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="cbe07-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="cbe07-105">Zum Bereitstellen des Servers für beständigen Chat müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="cbe07-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="cbe07-106">Verwenden Sie den Topologie-Generator, um die Topologie und die Komponenten, die Sie bereitstellen möchten, zu definieren oder zu importieren und anschließend zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="cbe07-107">Vorbereiten der Umgebung für die Bereitstellung von Komponenten für beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="cbe07-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="cbe07-108">Installieren und konfigurieren Sie die Server Komponenten für beständigen Chat für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="cbe07-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="cbe07-109">Der Server für beständigen Chat ist mit lync Server 2013 Enterprise Edition als separater Pool verfügbar (nicht zusammen mit den Front-End-Servern der Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="cbe07-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="cbe07-110">Für den Server für beständigen Chat ist ein SQL Server Back-End-Server in Ihrem Enterprise Edition-Pool erforderlich, um den Chatroom-Inhalt und andere relevante Metadaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cbe07-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="cbe07-111">Es wird empfohlen, das **PersistentChatStore** auf einem dedizierten SQL Server Back-End-Server zu installieren, obwohl abstimmen lync Server 2013 Back-End-Server und **PersistentChatStore** in derselben SQL Server-Instanz unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe07-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="cbe07-112">Der Server für beständigen Chat kann auch mit lync Server 2013 Standard Edition bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe07-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="cbe07-113">In diesem Fall ist die **PersistentChatService** -Front-End-Server auf dem Standard Edition-Computer zusammengefasst, und der **PersistentChatStore** -Back-End-Server kann auf der lokalen SQL Server Express-Instanz bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe07-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="cbe07-114">Ausführliche Informationen zu unterstützten Colocation-Konfigurationen finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md)Zusammenstellungen in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbe07-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cbe07-115">Die hohe Verfügbarkeit für die Server&nbsp;Standard Edition für beständigen Chat wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cbe07-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="cbe07-116">Leistung und Skalierung sind eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="cbe07-116">Performance and scale will be limited.</span></span> <span data-ttu-id="cbe07-117">Darüber hinaus unterstützen wir nur neue Server&nbsp;für beständigen Chat Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="cbe07-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="cbe07-118">Wir unterstützen das Upgrade lync Server 2010, Gruppen Chat Server nicht auf eine&nbsp;lync Server 2013 persistent Chat&nbsp;Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cbe07-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="cbe07-119">Wenn Ihre Organisation Compliance-Unterstützung benötigt, können Sie den Kompatibilitätsdienst für beständigen Chat Server auf dem Server für beständigen Chat Front-End-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="cbe07-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="cbe07-120">Für die Konformität ist eine separate Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cbe07-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="cbe07-121">Für jede Topologie ist mindestens ein Server mit installierter lync Server 2013 und ein Server mit SQL Server-Datenbanksoftware erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cbe07-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="cbe07-122">Verwenden Sie den Topologie-Generator, um Ihren lync Server 2013-Bereitstellungen beständigen Chat Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="cbe07-123">Sie können mithilfe des Topologie-Generators einen oder mehrere Server Pools für beständigen Chat hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="cbe07-124">Befolgen Sie dieselben Bereitstellungsanweisungen für die Bereitstellung mehrerer Server Pools für beständigen Chat wie für jeden Pool.</span><span class="sxs-lookup"><span data-stu-id="cbe07-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="cbe07-125">Ausführliche Informationen finden Sie unter [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cbe07-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="cbe07-126">Ausführliche Informationen zu verfügbaren Topologien und den technischen und Softwareanforderungen für die Installation von persistent Chat Server finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [How persistent Chat ServerWorks in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation sowie [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cbe07-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cbe07-127">Ausführliche Informationen zum Erwerb von Zertifikaten, zum Erstellen der SQL Server Datenbank und zum Erstellen von Datei speichern finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cbe07-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="cbe07-128">Eine einzelne Server Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="cbe07-129">Sie können einen Server Pool für beständigen Chat mit bis zu 4 aktiven Front-End-Servern mit einer Gesamtzahl von 80.000 gleichzeitigen Benutzern unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="cbe07-130">Der Server für beständigen Chat wird auch auf einem virtuellen Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cbe07-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="cbe07-131">Der virtuelle Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, wenn er den Spezifikationen des physischen Servers entspricht.</span><span class="sxs-lookup"><span data-stu-id="cbe07-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cbe07-132">Der Server für beständigen Chat muss auf einem NTFS-Dateisystem installiert sein, um die Sicherheit von Dateisystemen zu Verb erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cbe07-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="cbe07-133">FAT32 ist kein unterstütztes Dateisystem für den Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cbe07-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cbe07-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cbe07-134">In This Section</span></span>

  - [<span data-ttu-id="cbe07-135">Funktionsweise von persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="cbe07-136">Prüfliste für die Bereitstellung für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="cbe07-137">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="cbe07-138">Einrichten von Systemen und Infrastruktur für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="cbe07-139">Hinzufügen von persistent Chat Server zu Ihrer Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="cbe07-140">Installieren des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="cbe07-141">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="cbe07-142">Konfigurieren des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="cbe07-143">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cbe07-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="cbe07-144">Problembehandlung für die Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="cbe07-145">Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="cbe07-146">Failover und Ausfall des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe07-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

