---
title: 'Lync Server 2013: Hardwaresetup'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="13e04-102">Hardwaresetup für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e04-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13e04-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="13e04-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="13e04-104">Das Einrichten der Hardware und anderer Komponenten, die für die Infrastruktur erforderlich sind, die Sie zum Implementieren Ihrer Topologie benötigen, erfordert, dass Sie vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="13e04-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="13e04-105">Installieren Sie die Hardware für jede Komponente im Topologie-Design, das Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten (IIS) und Reverse Proxy Server, je nach Bedarf), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver).</span><span class="sxs-lookup"><span data-stu-id="13e04-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="13e04-106">Vergewissern Sie sich, dass Sie die Empfehlungen für die Anzahl und Geschwindigkeit von Netzwerkadaptern befolgt haben.</span><span class="sxs-lookup"><span data-stu-id="13e04-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="13e04-107">Wenn Sie Hardwarelastenausgleichs verwenden werden, stellen Sie sicher, dass Sie über die richtigen Informationen des Anbieters verfügen, um Sie für die Verwendung mit lync Server 2013 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13e04-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="13e04-108">Wenn Sie einen Dateiserver oder einen anderen Server verwenden werden, um die von lync Server erforderliche Dateifreigabe aufzunehmen, stellen Sie sicher, dass der Server verfügbar und für die Konfiguration der Dateifreigabe bereit ist.</span><span class="sxs-lookup"><span data-stu-id="13e04-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="13e04-109">Details zum Definieren einer Topologie, die die für die Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="13e04-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="13e04-110">Details zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="13e04-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="13e04-111">Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="13e04-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="13e04-112">Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="13e04-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="13e04-113">Einrichten von Active Directory-Domänendiensten</span><span class="sxs-lookup"><span data-stu-id="13e04-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="13e04-114">Das Einrichten von AD DS umfasst das Vorbereiten von AD DS und das Definieren aller Komponenten, die in AD DS bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13e04-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="13e04-115">Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="13e04-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="13e04-116">Richten Sie die erforderlichen Berechtigungen zum Erstellen der Dateifreigabe ein.</span><span class="sxs-lookup"><span data-stu-id="13e04-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="13e04-117">Die Berechtigungen für die Verwendung von Dateifreigaben durch lync Server 2013 werden automatisch vom Topologie-Generator konfiguriert, wenn Sie Ihre Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="13e04-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="13e04-118">Das für die Veröffentlichung der Topologie verwendete Benutzerkonto muss jedoch über die vollständige Steuerung (Lesen/Schreiben/ändern) auf der Dateifreigabe verfügen, damit der Topologie-Generator die erforderlichen Berechtigungen konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="13e04-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="13e04-119">Um sicherzustellen, dass die Dateifreigabe während des Veröffentlichungsprozesses der Topologie-Builder ordnungsgemäß verwaltet werden kann, sollte der Benutzer oder die Domänengruppe, in der der Benutzer Mitglied ist, Mitglied der lokalen Gruppe Administratoren auf dem Computer sein, auf dem sich die Dateifreigabe befindet.</span><span class="sxs-lookup"><span data-stu-id="13e04-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="13e04-120">In einem Szenario mit mehreren Domänen sollte die Domäne eines Benutzers oder einer Gruppe ein Mitglied der lokalen Gruppe Administratoren auf dem Computer in Domäne B sein, in dem sich die Dateifreigabe befindet.</span><span class="sxs-lookup"><span data-stu-id="13e04-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="13e04-121">Ausführliche Informationen zum Aktualisieren von Dateifreigaben in einem DFS (Distributed File System) finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="13e04-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="13e04-122">Die Dateifreigabe für lync Server 2013, Enterprise Edition, kann nicht auf dem Front-End-Server gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="13e04-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="13e04-123">Installieren Sie das Hardware-Lastenausgleichsmodul für Webdienste, und richten Sie es ein.</span><span class="sxs-lookup"><span data-stu-id="13e04-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="13e04-124">Wenn der DNS-Lastenausgleich (Domain Name System) bereitgestellt wird, müssen Sie weiterhin Hardwarelastenausgleichs für diese Pools verwenden, jedoch nur für HTTP/HTTPS-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="13e04-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="13e04-125">Das Hardware-Lastenausgleichsmodul wird für HTTPS-Datenverkehr von Clients über Ports 443 und 80 verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e04-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="13e04-126">Obwohl Sie weiterhin Hardwarelastenausgleichs für diese Pools benötigen, werden deren Einrichtung und Verwaltung in erster Linie für den HTTP/HTTPS-Datenverkehr verwendet, den die Administratoren der Hardwarelastenausgleichs gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="13e04-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="13e04-127">Nachdem Sie alle Vorbereitungsaufgaben wie in diesem Thema beschrieben, aber vor dem Veröffentlichen der Topologie abgeschlossen haben, müssen Sie auch Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="13e04-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="13e04-128">Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e04-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="13e04-129">Konfigurieren von IIS für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e04-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="13e04-130">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e04-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="13e04-131">Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="13e04-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

