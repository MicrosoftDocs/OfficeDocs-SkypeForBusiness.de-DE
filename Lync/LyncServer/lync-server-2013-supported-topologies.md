---
title: Lync Server 2013 unterstützten Topologien
description: Lync Server 2013 unterstützten Topologien.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c19577fbda7e377e145abfd473d2cf8e6d4a1a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558021"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="31d4b-103">Unterstützte Topologien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31d4b-103">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31d4b-104">_**Letztes Änderungsstand des Themas:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="31d4b-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="31d4b-105">Lync Server 2013 unterstützt die Bereitstellung von Websites in einer Organisation und Integration von lokalen Bereitstellungen mit lync Online-Bereitstellungen, die als hybridbereitstellung bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="31d4b-105">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="31d4b-106">In einer hybridbereitstellung werden einige Benutzer lokal verwaltet, und einige Benutzer werden online verwaltet.</span><span class="sxs-lookup"><span data-stu-id="31d4b-106">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="31d4b-107">Für lokale Bereitstellungen unterstützt lync Server 2013 die Bereitstellungeines oder mehrerer Standorte, die skaliert werden können, um hohe Verfügbarkeit und Standortanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-107">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="31d4b-108">Diese Standorte und ihre Komponenten können Sie so strukturieren, dass sie den Anforderungen Ihrer Organisation hinsichtlich Zugriff und Ausfallsicherheit entsprechen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-108">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="31d4b-109">Eine lync Server 2013 lokale Bereitstellung umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="31d4b-109">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="31d4b-p103">Ihre Bereitstellung muss mindestens einen zentralen Standort aufweisen (auch als Datencenter bezeichnet). Jeder zentrale Standort muss mindestens einen Front-End-Pool der Enterprise Edition oder einen Server der Standard Edition enthalten. Diese Komponenten sind folgendermaßen zusammengesetzt:</span><span class="sxs-lookup"><span data-stu-id="31d4b-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="31d4b-113">Der Front-End-Pool der Enterprise Edition umfasst einen oder mehrere Front-End-Server (aus Gründen der Skalierbarkeit typischerweise mindestens zwei Front-End-Server) sowie einen separaten Back-End-Server.</span><span class="sxs-lookup"><span data-stu-id="31d4b-113">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="31d4b-114">Ein Front-End-Pool kann maximal zwölf Front-End-Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-114">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="31d4b-115">Für mehrere Front-End-Server ist ein Lastenausgleich erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31d4b-115">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="31d4b-116">Für SIP-Datenverkehr wird der DNS-Lastenausgleich empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d4b-116">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="31d4b-117">Auch wenn Sie den DNS-Lastenausgleich für SIP-Datenverkehr einsetzen, benötigen Sie außerdem ein Hardwaregerät zum Lastenausgleich für HTTP-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="31d4b-117">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="31d4b-118">Es wird empfohlen, SQL Server Spiegelung für eine hohe Verfügbarkeit von Datenbanken zu sichern.</span><span class="sxs-lookup"><span data-stu-id="31d4b-118">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="31d4b-119">Die Back-End-Datenbank erfordert eine separate Instanz, aber Sie können die Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat mit der Back-End-Datenbank verbinden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-119">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="31d4b-120">Lync Server 2013 unterstützt die Verwendung eines freigegebenen Clusters für die Dateifreigaben in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="31d4b-120">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="31d4b-121">Ausführliche Informationen zu den Anforderungen an den Datenbankspeicher finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="31d4b-121">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="31d4b-122">Ausführliche Informationen zu den Dateispeicheranforderungen finden Sie unter [File Storage Support in lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="31d4b-122">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="31d4b-123">Wenn Sie lync Server Datenbanken collocate, wird dringend empfohlen, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="31d4b-123">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="31d4b-124">Zum Überprüfen der Failoverfunktionen wird empfohlen, alle Failover-Szenarien zu testen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-124">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="31d4b-125">Server der Standard Edition, der eine verbundene SQL Server Express-Datenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="31d4b-125">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="31d4b-126">In Ihrer Bereitstellung können mehrere Zweigstellen einem zentralen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-126">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="31d4b-127">In diesem Abschnitt werden die Websites und Komponenten einer lync Server 2013-Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d4b-127">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="31d4b-128">Ausführliche Informationen zur Planung lync Server 2013 Standorts, der Topologie und der Komponenten finden Sie unter [Topologie Grundlagen, die Sie vor der Planung von lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) und [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation kennen müssen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-128">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="31d4b-129">Ausführliche Informationen zur Integration von Komponenten früherer Versionen finden Sie unter [Supported Migration Paths and Koexistenz Scenarios in lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="31d4b-129">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31d4b-130">Gestreckte Pools werden für die Serverrollen Front End, Edge, Mediation und Director nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d4b-130">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="31d4b-131">Topologien und Komponenten des zentralen Standorts (lokal)</span><span class="sxs-lookup"><span data-stu-id="31d4b-131">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="31d4b-132">Auch wenn die Topologie eines zentralen Standorts einen Front-End-Pool oder einen Server der Standard Edition umfassen muss, kann jeder zentrale Standort auch folgende Komponenten enthalten:</span><span class="sxs-lookup"><span data-stu-id="31d4b-132">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="31d4b-p107">Mehrere Front-End-Pools, die sich in derselben oder in verschiedenen Domänen befinden können. Alle Front-End-Server in einem Front-End-Pool und der Back-End-Server für den entsprechenden Pool müssen sich jedoch in derselben Domäne befinden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="31d4b-135">Mehrere Server der Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="31d4b-135">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="31d4b-136">Office-webapps-Server, der mit Office-Webanwendungen in lync Server 2013 verwendet wird, um die Freigabe und das Rendern von Microsoft PowerPoint Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-136">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="31d4b-137">Edgeserver oder Edgepool in Ihrem Umkreisnetzwerk, wenn Ihre Bereitstellung Verbundpartner, öffentliche Instant Messaging-Verbindungen, ein XMPP-Gateway (Extensible Messaging and Presence Protocol), Remotebenutzerzugriff, Teilnahme anonymer Benutzer an Besprechungen oder Exchange Unified Messaging (um) unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="31d4b-137">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="31d4b-138">Mit einem Edgeserver kann keine weitere Serverrolle verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-138">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="31d4b-139">Der DNS-Lastenausgleich wird nach Bedarf empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d4b-139">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="31d4b-140">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-140">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="31d4b-141">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-141">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="31d4b-142">Ausführliche Informationen zu Lastenausgleichsanforderungen und-Unterstützung finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-142">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="31d4b-143">Vermittlungsserver oder Pool, wenn Sie Enterprise-VoIP oder Einwahlkonferenzen in einer Front-End-Pool am zentralen Standort unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-143">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="31d4b-144">Je nachdem, wie Sie Enterprise-VoIP-Unterstützung bereitstellen, können Sie die Vermittlungsserver in einer Front-End-Pool (Standardeinstellung) collocate oder einen eigenständigen Vermittlungsserver oder Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-144">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="31d4b-145">Sie können DNS-, Hardware-oder Anwendungslasten Ausgleich (sofern zutreffend) verwenden, um Datenverkehr vom Gateway-Peer eines Vermittlungsserver Pools zu verteilen, einschließlich eines PSTN-Gateways, einer IP-Nebenstellenanlage oder eines SIP-Trunk-Sitzungs Rahmensteuerelements (SBC). Ausführliche Informationen zum Planen der entsprechenden Vermittlungsserver Topologie finden Sie unter [Deployment Guidelines for Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-145">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31d4b-146">Server für beständigen Chat, wenn Sie möchten, dass Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen können, die im Laufe der Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-146">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="31d4b-147">Um mehr Kapazität und höhere Zuverlässigkeit bereitzustellen, kann Ihre Topologie mehrere Computer mit persistent Chat Server umfassen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-147">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="31d4b-148">Sie können den Server für beständigen Chat nicht mit anderen Serverrollen in einem Enterprise-Pool collocate.</span><span class="sxs-lookup"><span data-stu-id="31d4b-148">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="31d4b-149">Sie können den Server für beständigen Chat jedoch auf einem Standard Edition-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="31d4b-149">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="31d4b-150">Für beständigen Chat ist eine Datenbank erforderlich, und wenn Sie die Compliance für beständigen Chat implementieren, wird eine Kompatibilitätsdatenbank für beständigen Chat benötigt, aber die Datenbankenkönnen mit dem Archivierungsdatenbank, Überwachungsdatenbank oder auf dem Back-End-Server eines Enterprise Edition-Front-End-Pool verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-150">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="31d4b-151">Ausführliche Informationen zum Planen der entsprechenden Server Topologie für beständigen Chat finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-151">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31d4b-152">Überwachung, wenn Sie die Datensammlung für die Audio/Video Quality of Experience (QoE) und die Aufzeichnung von Kommunikationsdatensätzen (CDR) für Enterprise-VoIP und A/V-Konferenzen in Ihrer Bereitstellung unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-152">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="31d4b-153">Optional können Sie Microsoft System Center Operations Manager (ehemals Microsoft Operations Manager) installieren, das die Überwachungs-KDS-und QoE-Daten verwendet, um in Echtzeit Warnungen zu generieren, die die Integrität von Anruf Zuverlässigkeit und Medienqualität anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-153">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="31d4b-154">Die Überwachung erfolgt bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="31d4b-154">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="31d4b-155">Für die Überwachung ist eine Datenbank erforderlich, die Datenbank kann jedoch mit der Archivierungsdatenbank, der Datenbank für beständigen Chat, der Kompatibilitätsdatenbank für beständigen Chat oder dem Back-End-Server eines Enterprise Edition-Front-End-Pool verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-155">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="31d4b-156">Archivierung, wenn Sie die Chatkommunikation und Besprechungsinhalte (zur Einhaltung von Bestimmungen) in Ihrer Bereitstellung archivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-156">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="31d4b-157">Die Archivierung, sofern bereitgestellt, wird mit Front-End-Servern oder einem Standard-Edition-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-157">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="31d4b-158">Der Archivierungsspeicher erfordert entweder die Bereitstellungeines Archivierungsdatenbank oder eine Integration in Exchange 2013 Speicher.</span><span class="sxs-lookup"><span data-stu-id="31d4b-158">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="31d4b-159">Wenn Sie beide verwenden, was als *Gemischter Modus*bezeichnet wird, wird Exchange 2013 Speicher verwendet, um Archivdaten für Benutzer zu speichern, die in Exchange 2013 verwaltet werden, und die Archivierungsdatenbank dient zum Archivieren von Daten für alle anderen Benutzer in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="31d4b-159">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="31d4b-160">Wenn Sie eine Archivierungsdatenbank benötigen, kann die Datenbank mit der Überwachungsdatenbank, Datenbank für beständigen Chat, Konformitätsdatenbank für beständigen Chat oder dem Back-End-Server eines Front-End-Pool verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-160">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="31d4b-161">Ausführliche Informationen zum Planen der entsprechenden Archivierungs Topologie finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-161">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31d4b-162">Director oder Directorpool, wenn Sie die Ausfallsicherheit und die Umleitung von lync Server 2013 Benutzeranforderungen an den Home-Pool des Benutzers erleichtern möchten, bei dem es sich entweder um eine Enterprise Edition-Front-End-Pool oder eine Standard Edition-Server handeln kann.</span><span class="sxs-lookup"><span data-stu-id="31d4b-162">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="31d4b-163">Es wird empfohlen, dass Sie einen Director oder Directorpool an jedem zentralen Standort bereitstellen, der den Zugriff durch externe Benutzer und an jedem zentralen Standort unterstützt, in dem Sie einen oder mehrere Front-End-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-163">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="31d4b-164">Jeder Directorpool kann maximal zehn Directors enthalten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-164">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="31d4b-165">Ein Director kann nicht mit einer anderen Serverrolle verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="31d4b-165">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="31d4b-166">Ausführliche Informationen zum Planen der entsprechenden Director-Topologie finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-166">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31d4b-167">Reverseproxy, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer unterstützen oder Mobilitäts Datenverkehr unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="31d4b-167">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="31d4b-168">Es ist nicht möglich, einen Reverseproxy-Server mit einer lync Server 2013 Serverrolle collocate, aber Sie können die Unterstützung für Reverse-Proxys für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d4b-168">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="31d4b-169">Ausführliche Informationen zu Reverse-Proxyservern finden Sie unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-169">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31d4b-170">In lync Server 2013 werden A/V-Konferenzen,-Überwachung und-Archivierung auf Front-End-Servern ausgeführt und sind keine separaten Server Rollen mehr.</span><span class="sxs-lookup"><span data-stu-id="31d4b-170">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="31d4b-171">Alle am zentralen Standort bereitgestellten Front-End-Pools und Server der Standard Edition nutzen folgende Komponenten gemeinsam, wenn Sie diese für den zentralen Standort bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="31d4b-171">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="31d4b-172">Director oder Director-Pool</span><span class="sxs-lookup"><span data-stu-id="31d4b-172">Director or Director pool</span></span>

  - <span data-ttu-id="31d4b-173">Eigenständiger Vermittlungsserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="31d4b-173">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="31d4b-174">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="31d4b-174">Office Web Apps Server</span></span>

  - <span data-ttu-id="31d4b-175">Edgeserver oder Edgepool</span><span class="sxs-lookup"><span data-stu-id="31d4b-175">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="31d4b-176">Server für beständigen Chat oder Pool</span><span class="sxs-lookup"><span data-stu-id="31d4b-176">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="31d4b-177">Überwachung</span><span class="sxs-lookup"><span data-stu-id="31d4b-177">Monitoring</span></span>

  - <span data-ttu-id="31d4b-178">Archivierung</span><span class="sxs-lookup"><span data-stu-id="31d4b-178">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31d4b-179">Ein Exchange um Server kann mit ihrer lync Server 2013-Bereitstellung implementiert werden, wenn Sie die Integration von Exchange 2013 Unified Messaging unterstützen möchten, aber es handelt sich nicht um eine Komponente des lync Server 2013-Standorts.</span><span class="sxs-lookup"><span data-stu-id="31d4b-179">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="31d4b-180">Mehrere zentrale Standorte können außerdem folgende Komponenten gemeinsam nutzen, die Sie an einem zentralen Standort bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="31d4b-180">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="31d4b-181">Eigenständiger Vermittlungsserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="31d4b-181">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="31d4b-182">Edgeserver oder Edgepool</span><span class="sxs-lookup"><span data-stu-id="31d4b-182">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="31d4b-183">Server für beständigen Chat oder Pool</span><span class="sxs-lookup"><span data-stu-id="31d4b-183">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="31d4b-184">Archivierung</span><span class="sxs-lookup"><span data-stu-id="31d4b-184">Archiving</span></span>

  - <span data-ttu-id="31d4b-185">Überwachung</span><span class="sxs-lookup"><span data-stu-id="31d4b-185">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31d4b-186">Ein Exchange um Server kann mit ihrer lync Server 2013-Bereitstellung implementiert und von mehreren zentralen Standorten gemeinsam genutzt werden, aber es handelt sich nicht um eine Komponente des lync Server 2013-Standorts.</span><span class="sxs-lookup"><span data-stu-id="31d4b-186">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="31d4b-187">Ausführliche Informationen zu lync Server 2013 Serverrollen und-Funktionen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-187">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="31d4b-188">Eine Zusammenfassung der unterstützten lync Server 2013 Server-Zusammenstellungs Unterstützung finden Sie unter [Supported Server recolocation in lync Server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="31d4b-188">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="31d4b-189">Zusätzlich zu den zuvor in diesem Abschnitt beschriebenen Serverrollen und Funktionen verfügt lync Server 2013 über zusätzliche Komponenten und Optionen, die einige oder alle der folgenden Elemente enthalten können:</span><span class="sxs-lookup"><span data-stu-id="31d4b-189">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="31d4b-190">Firewalls</span><span class="sxs-lookup"><span data-stu-id="31d4b-190">Firewalls</span></span>

  - <span data-ttu-id="31d4b-191">PSTN-Gateways (bei Bereitstellung von Enterprise-VoIP)</span><span class="sxs-lookup"><span data-stu-id="31d4b-191">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="31d4b-192">Exchange um Server</span><span class="sxs-lookup"><span data-stu-id="31d4b-192">Exchange UM Server</span></span>

  - <span data-ttu-id="31d4b-193">DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="31d4b-193">DNS load balancing</span></span>

  - <span data-ttu-id="31d4b-194">Hardwaregeräte zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="31d4b-194">Hardware load balancers</span></span>

  - <span data-ttu-id="31d4b-195">SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="31d4b-195">SQL Server databases</span></span>

  - <span data-ttu-id="31d4b-196">Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="31d4b-196">File shares</span></span>

<span data-ttu-id="31d4b-197">Ausführliche Informationen zu allen lync Server 2013-Features,-Komponenten und-Optionen finden Sie in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31d4b-197">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="31d4b-198">Topologien und Komponenten von Zweigstellen (lokal)</span><span class="sxs-lookup"><span data-stu-id="31d4b-198">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="31d4b-p115">Eine Zweigstelle ist einem zentralen Standort zugeordnet, und jede Survivable Branch Appliance an einem Zweigstellenstandort ist einem Front-End-Pool der Enterprise Edition oder einem Server der Standard Edition am entsprechenden zentralen Standort zugeordnet. Der Großteil der Funktionalität an Zweigstellenstandorten ist vom zentralen Standort abhängig, daher umfassen Zweigstellenstandorte nur folgende Komponenten:</span><span class="sxs-lookup"><span data-stu-id="31d4b-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="31d4b-201">Ein Survivable Branch Appliance, in dem ein PSTN-Gateway (Public Switched Telephone Network) mit einigen lync Server Funktionen kombiniert wird.</span><span class="sxs-lookup"><span data-stu-id="31d4b-201">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="31d4b-202">Ein Vermittlungsserver kann mit der Instanz der Registrierungsstelle auf dem Survivable Branch Appliance zusammengestellt werden, und Sie können eine eigenständige Vermittlungsserver oder einen Pool von Vermittlungsservern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="31d4b-202">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="31d4b-203">Ein Survivable Branch Server, bei dem es sich um einen Server mit Windows Server handelt, auf dem lync Server 2013 Registrierungsstelle und Vermittlungsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="31d4b-203">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="31d4b-204">Ein eigenständiges PSTN-Gateway (kein Bestandteil der Survivable Branch Appliance) und einen eigenständigen Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="31d4b-204">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="31d4b-205">Die Anforderungen für Survivable Branch Server entsprechen den Anforderungen für alle lync Server 2013 Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="31d4b-205">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

