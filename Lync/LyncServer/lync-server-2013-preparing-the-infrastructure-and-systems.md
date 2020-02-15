---
title: 'Lync Server 2013: Vorbereiten der Infrastruktur und der Systeme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34de50135ff04c7db1b3eda2b65bdebb4ef10273
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="55677-102">Vorbereiten der Infrastruktur und der Systeme für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55677-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55677-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="55677-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="55677-104">Für die Bereitstellung von lync Server 2013 ist die Verwendung des Topologie-Generators zum Definieren und Veröffentlichen des Topologie-Designs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55677-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="55677-105">Um die für Ihre Topologie erforderlichen Komponenten zu identifizieren, erstellen und speichern Sie einen Topologie-Design mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="55677-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="55677-106">Vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="55677-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="55677-107">Erwerben und installieren Sie die Hardware für jede Komponente im Topologie-Design, die Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten ( IIS) und gegebenenfalls Reverse-Proxy Server), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (beispielsweise Dateiserver).</span><span class="sxs-lookup"><span data-stu-id="55677-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="55677-108">Ausführliche Informationen zum Definieren einer Topologie, die die für Ihre Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="55677-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="55677-109">Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="55677-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="55677-110">Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="55677-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="55677-111">Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="55677-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="55677-112">Einrichten Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="55677-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="55677-113">Zum Veröffentlichen und Aktivieren der Topologie müssen die internen Server durch Computerkonten in AD DS repräsentiert werden.</span><span class="sxs-lookup"><span data-stu-id="55677-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="55677-114">Dies wird erreicht, indem die Computer in die Active Directory-Domänendienste aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="55677-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="55677-115">Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [Vorbereiten von Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="55677-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="55677-116">Erstellen Sie eine Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="55677-116">Create a file share.</span></span> <span data-ttu-id="55677-117">Standard Edition-Server können die Dateifreigabe für die erforderliche Datei hosten, während in einer Enterprise-Bereitstellung die Dateifreigabe nicht auf dem Front-End-Server gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="55677-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="55677-118">Die Berechtigungen und Gruppenmitgliedschaften, die zur Bereitstellung und Festlegung der Zugriffssteuerungsliste für den Ordner und die Freigabe erforderlich sind, müssen für den Topologie-Generator ordnungsgemäß festgelegt werden, damit er erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="55677-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="55677-119">Sie sollten sicherstellen, dass die Person, auf der der Topologie-Generator ausgeführt wird, über die folgenden Berechtigungen und Gruppenmitgliedschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="55677-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="55677-120">Mitglied der lokalen Administratorgruppe</span><span class="sxs-lookup"><span data-stu-id="55677-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="55677-121">Mitglied der Domänenbenutzergruppe</span><span class="sxs-lookup"><span data-stu-id="55677-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="55677-122">Vollzugriff auf Freigabe und Ordner des Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="55677-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="55677-p106">Installieren Sie SQL Server für Enterprise Edition. Zur erfolgreichen SQL Server-Einrichtung muss der SQL Server-basierte Server online sein, und der Benutzer, der die Topologie veröffentlicht, muss auf der SQL Server-Instanz ein Mitglied der SQL Server-Gruppe "sysadmin" sein.</span><span class="sxs-lookup"><span data-stu-id="55677-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="55677-125">Nachdem Sie alle Vorbereitungsaufgaben wie in diesem Thema beschrieben abgeschlossen haben, aber vor der Veröffentlichung der Topologie, müssen Sie auch die anderen Vorbereitungsaufgaben ausführen, einschließlich der Installation der Windows-Betriebssysteme und anderer erforderlicher Software, einrichten IIS und Konfigurieren von DNS.</span><span class="sxs-lookup"><span data-stu-id="55677-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="55677-126">Ausführliche Informationen zu diesen Aufgaben finden Sie unter [System Anforderungen für Server mit lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Konfigurieren von IIS für lync Server 2013](lync-server-2013-configure-iis.md)und [Vorbereiten der Infrastruktur und der Systeme für lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="55677-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="55677-127">Darüber hinaus sollten Sie sich mit den Anforderungen für Clients und Clients vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="55677-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="55677-128">Ausführliche Informationen finden Sie unter [Deploying Clients and Devices in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="55677-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55677-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="55677-129">In This Section</span></span>

  - [<span data-ttu-id="55677-130">Hardware Setup für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55677-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="55677-131">Software Setup für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55677-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="55677-132">Vorbereiten der Active Directory-Domänendienste für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55677-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="55677-133">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55677-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="55677-134">Konfigurieren von DNS-Einträgen in lync Server 2013 für eine Front-End-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="55677-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="55677-135">Installieren von lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="55677-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

