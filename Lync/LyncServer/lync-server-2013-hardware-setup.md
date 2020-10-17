---
title: 'Lync Server 2013: Hardware-Setup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528342"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="8a66d-102">Hardware Setup für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a66d-102">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a66d-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8a66d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8a66d-104">Zum Einrichten der Hardware und anderer Komponenten, die für die Infrastruktur erforderlich sind, die Sie zur Implementierung Ihrer Topologie benötigen, müssen Sie vor dem Veröffentlichen der Topologie im Topologie-Generator folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a66d-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="8a66d-105">Installieren Sie die Hardware für jede Komponente im Topologie-Design, die Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server, auf denen lync Server 2013, Datenbankserver, Server mit Internet Information Services (IIS) und Reverse-Proxyservern, je nach Bedarf), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a66d-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="8a66d-106">Überprüfen Sie, ob Sie die Empfehlungen für die Anzahl und die Geschwindigkeit von Netzwerkadaptern befolgt haben.</span><span class="sxs-lookup"><span data-stu-id="8a66d-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="8a66d-107">Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, stellen Sie sicher, dass Sie über die richtigen Informationen vom Anbieter verfügen, um Sie für die Verwendung mit lync Server 2013 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a66d-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="8a66d-108">Wenn Sie einen Dateiserver oder einen anderen Server verwenden, um die für lync Server erforderliche Dateifreigabe zu beherbergen, stellen Sie sicher, dass der Server verfügbar und für die Konfiguration der Dateifreigabe bereit ist.</span><span class="sxs-lookup"><span data-stu-id="8a66d-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="8a66d-109">Ausführliche Informationen zum Definieren einer Topologie, die die für Ihre Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="8a66d-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="8a66d-110">Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8a66d-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="8a66d-111">Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8a66d-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="8a66d-112">Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8a66d-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="8a66d-113">Einrichten Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="8a66d-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="8a66d-114">Die Einrichtung der Active Directory-Domänendienste (AD DS) umfasst die AD DS-Vorbereitung und das Definieren aller Komponenten, die Sie in AD DS bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8a66d-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="8a66d-115">Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8a66d-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8a66d-116">Richten Sie die erforderlichen Berechtigungen zum Erstellen der Dateifreigabe ein.</span><span class="sxs-lookup"><span data-stu-id="8a66d-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="8a66d-117">Berechtigungen für die Verwendung von Dateifreigaben durch lync Server 2013 werden beim Veröffentlichen Ihrer Topologie automatisch vom Topologie-Generator konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8a66d-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="8a66d-118">Das zum Veröffentlichen der Topologie verwendete Benutzerkonto muss jedoch über Vollzugriff auf die Dateifreigabe verfügen (Lesen/Schreiben/ändern), damit der Topologie-Generator die erforderlichen Berechtigungen konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="8a66d-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="8a66d-119">Um sicherzustellen, dass die Dateifreigabe während des Veröffentlichungsprozesses des Topologie-Generators ordnungsgemäß verwaltet werden kann, sollte der Benutzer oder die Domänengruppe, zu der der Benutzer gehört, Mitglied der lokalen Gruppe Administratoren auf dem Computer sein, auf dem sich die Dateifreigabe befindet.</span><span class="sxs-lookup"><span data-stu-id="8a66d-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="8a66d-120">In einem Szenario mit mehreren Domänen sollte ein Benutzer oder eine Gruppe aus Domäne A Mitglied der lokalen Administratorgruppe auf dem Computer in Domäne B sein, auf dem die Dateifreigabe platziert wird.</span><span class="sxs-lookup"><span data-stu-id="8a66d-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="8a66d-121">Ausführliche Informationen zum Aktualisieren mithilfe von Dateifreigaben in einem verteilten Datei System (DFS) finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="8a66d-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8a66d-122">Die Dateifreigabe für lync Server 2013 Enterprise Edition kann sich nicht auf dem Front-End-Server befinden.</span><span class="sxs-lookup"><span data-stu-id="8a66d-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="8a66d-123">Installieren und Einrichten des Hardwaregerät zum Lastenausgleich für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="8a66d-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="8a66d-124">Auch wenn Sie einen DNS-Lastenausgleich (Domain Name System) konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTP/HTTPS-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="8a66d-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="8a66d-125">Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a66d-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="8a66d-126">Wenngleich Sie weiterhin Hardwaregeräte zum Lastenausgleich für diese Pools benötigen, erfolgt ihre Einrichtung und Verwaltung hauptsächlich für HTTP/HTTPS-Datenverkehr – so wie es Administratoren von Hardwaregeräten zum Lastenausgleich gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="8a66d-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="8a66d-127">Nachdem Sie alle vorbereitenden Aufgaben durchgeführt haben, jedoch vor der Veröffentlichung der Topologie, müssen Sie zusätzlich die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a66d-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="8a66d-128">Installieren von Betriebssystemen und erforderlicher Software auf Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a66d-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="8a66d-129">Konfigurieren von IIS für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a66d-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="8a66d-130">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a66d-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="8a66d-131">Konfigurieren von DNS-Einträgen in lync Server 2013 für eine Front-End-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="8a66d-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

