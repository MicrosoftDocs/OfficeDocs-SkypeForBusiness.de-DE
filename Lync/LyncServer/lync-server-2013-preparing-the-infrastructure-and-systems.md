---
title: 'Lync Server 2013: Vorbereiten der Infrastruktur und Systeme'
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
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="43904-102">Vorbereiten der Infrastruktur und Systeme für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43904-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43904-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="43904-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="43904-104">Die Bereitstellung von lync Server 2013 erfordert die Verwendung des Topologie-Generators zum Definieren und Veröffentlichen des Topologie-Designs.</span><span class="sxs-lookup"><span data-stu-id="43904-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="43904-105">Um die für Ihre Topologie erforderlichen Komponenten zu identifizieren, verwenden Sie den Topologie-Generator zum Erstellen und Speichern eines Topologie-Designs.</span><span class="sxs-lookup"><span data-stu-id="43904-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="43904-106">Bevor Sie Ihre Topologie im Topologie-Generator veröffentlichen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="43904-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="43904-107">Erwerben und installieren Sie die Hardware für jede Komponente im Topologie-Design, das Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten ( IIS) und ggf. Reverse Proxy Server), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver).</span><span class="sxs-lookup"><span data-stu-id="43904-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="43904-108">Details zum Definieren einer Topologie, die die für die Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="43904-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="43904-109">Details zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="43904-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="43904-110">Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="43904-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="43904-111">Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43904-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="43904-112">Einrichten von Active Directory-Domänendiensten</span><span class="sxs-lookup"><span data-stu-id="43904-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="43904-113">Um die Topologie zu veröffentlichen und zu aktivieren, müssen Sie die internen Server durch Computerkonten in AD DS darstellen.</span><span class="sxs-lookup"><span data-stu-id="43904-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="43904-114">Dies erfolgt durch beitreten der Computer zu AD DS.</span><span class="sxs-lookup"><span data-stu-id="43904-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="43904-115">Details zum Vorbereiten von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="43904-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="43904-116">Erstellen Sie eine Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="43904-116">Create a file share.</span></span> <span data-ttu-id="43904-117">Standard Edition-Server können die Dateifreigabe für die erforderliche Datei hosten, während die Dateifreigabe in einer Unternehmensbereitstellung nicht auf dem Front-End-Server gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="43904-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="43904-118">Die Berechtigungen und Gruppenmitgliedschaften, die für die Bereitstellung und Festlegung der Zugriffssteuerungsliste (ACL) für den Ordner und die Freigabe erforderlich sind, müssen für die erfolgreiche Ausführung des Topologie-Generators ordnungsgemäß festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="43904-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="43904-119">Stellen Sie sicher, dass die Person, auf der der Topology Builder ausgeführt wird, über die folgenden Berechtigungen und Gruppenmitgliedschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="43904-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="43904-120">Mitglied von lokalen Administratoren</span><span class="sxs-lookup"><span data-stu-id="43904-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="43904-121">Mitglied von Domänenbenutzern</span><span class="sxs-lookup"><span data-stu-id="43904-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="43904-122">Vollzugriff auf Freigabe und Ordner im Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="43904-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="43904-123">Für Enterprise Edition installieren und konfigurieren Sie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43904-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="43904-124">Damit das SQL Server-Setup erfolgreich ausgeführt werden kann, muss der auf SQL Server basierende Server online sein, und die Person, die die Topologie veröffentlicht, ist ein lokaler Administrator auf dem SQL Server und muss ein Mitglied der SQL Server sysadmin-Gruppe auf der SQL Server-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="43904-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="43904-125">Nachdem Sie alle Vorbereitungsaufgaben abgeschlossen haben, wie in diesem Thema beschrieben, aber vor dem Veröffentlichen der Topologie, müssen Sie auch die anderen Vorbereitungsaufgaben ausführen, einschließlich der Installation der Windows-Betriebssysteme und anderer erforderlicher Software, einrichten IIS und Konfigurieren von DNS.</span><span class="sxs-lookup"><span data-stu-id="43904-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="43904-126">Details zu diesen Aufgaben finden Sie unter [System Anforderungen für Server mit lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Konfigurieren von IIS für lync Server 2013](lync-server-2013-configure-iis.md)und [Vorbereiten der Infrastruktur und Systeme für lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="43904-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="43904-127">Darüber hinaus sollten Sie sich mit den Anforderungen der Clients und Clients vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="43904-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="43904-128">Ausführliche Informationen finden Sie unter [Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="43904-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="43904-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="43904-129">In This Section</span></span>

  - [<span data-ttu-id="43904-130">Hardwaresetup für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43904-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="43904-131">Softwaresetup für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43904-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="43904-132">Vorbereiten der Active Directory-Domänendienste für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43904-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="43904-133">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43904-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="43904-134">Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="43904-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="43904-135">Installieren von Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="43904-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

