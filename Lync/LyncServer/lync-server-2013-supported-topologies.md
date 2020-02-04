---
title: 'Lync Server 2013: Unterstützte Topologien'
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
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="501e3-102">Unterstützte Topologien in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501e3-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="501e3-103">_**Letztes Änderungsdatum des Themas:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="501e3-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="501e3-104">Lync Server 2013 unterstützt die Bereitstellung von Websites in einer Organisation und die Integration von lokalen Bereitstellungen mit lync Online-Bereitstellungen, die als hybridbereitstellung bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="501e3-105">In einer hybridbereitstellung sind einige Benutzer lokal verwaltet, und einige Benutzer sind online verwaltet.</span><span class="sxs-lookup"><span data-stu-id="501e3-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="501e3-106">Bei lokalen Bereitstellungen unterstützt lync Server 2013 die Bereitstellung von einem oder mehreren Websites, die skaliert werden können, um die Anforderungen an die Hochverfügbarkeit und den Standort zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="501e3-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="501e3-107">Sie können diese Websites und ihre Komponenten so strukturieren, dass Sie den Zugriffs-und Widerstands Anforderungen Ihrer Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="501e3-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="501e3-108">Eine lokale lync Server 2013-Bereitstellung umfasst die folgenden:</span><span class="sxs-lookup"><span data-stu-id="501e3-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="501e3-109">Ihre Bereitstellung muss mindestens einen zentralen Standort (auch als Rechenzentrum bezeichnet) umfassen.</span><span class="sxs-lookup"><span data-stu-id="501e3-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="501e3-110">Jeder zentrale Standort muss mindestens einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="501e3-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="501e3-111">Diese bestehen aus folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="501e3-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="501e3-112">Enterprise Edition-Front-End-Pool, der aus einem oder mehreren Front-End-Servern (in der Regel mindestens zwei Front-End-Servern für Skalierbarkeit) und einem separaten Back-End-Server besteht.</span><span class="sxs-lookup"><span data-stu-id="501e3-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="501e3-113">Ein Front-End-Pool kann maximal zwölf Front-End-Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="501e3-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="501e3-114">Der Lastenausgleich ist für mehrere Front-End-Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="501e3-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="501e3-115">Für SIP-Datenverkehr empfehlen wir den DNS-Lastenausgleich, aber auch der Hardwarelastenausgleich wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="501e3-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="501e3-116">Wenn Sie den DNS-Lastenausgleich für den SIP-Datenverkehr verwenden, benötigen Sie weiterhin ein Hardware-Lastenausgleichsmodul für HTTP-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="501e3-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="501e3-117">Wir empfehlen die SQL Server-Spiegelung für eine höhere Verfügbarkeit von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="501e3-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="501e3-118">Die Back-End-Datenbank erfordert eine separate Instanz, Sie können jedoch die Archivierungsdatenbank, die Überwachungsdatenbank, die Datenbank für beständigen Chat und die Datenbank für beständigen Chat collocate.</span><span class="sxs-lookup"><span data-stu-id="501e3-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="501e3-119">Lync Server 2013 unterstützt die Verwendung eines freigegebenen Clusters für die Dateifreigaben in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="501e3-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="501e3-120">Details zu den Datenbankspeicher Anforderungen finden Sie unter [Unterstützung der Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="501e3-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="501e3-121">Ausführliche Informationen zu den Dateispeicheranforderungen finden Sie unter [Unterstützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="501e3-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="501e3-122">Wenn Sie lync Server-Datenbanken collocate, empfehlen wir dringend, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="501e3-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="501e3-123">Zum Überprüfen von Failoverfunktionen empfiehlt es sich, alle Failover-Szenarien zu testen.</span><span class="sxs-lookup"><span data-stu-id="501e3-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="501e3-124">Standard Edition-Server mit einer kombinierten SQL Server Express-Datenbank</span><span class="sxs-lookup"><span data-stu-id="501e3-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="501e3-125">Ihre Bereitstellung kann auch eine oder mehrere Verzweigungs Websites aufweisen, die einem zentralen Standort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="501e3-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="501e3-126">In diesem Abschnitt werden die Websites und Komponenten einer lync Server 2013-Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="501e3-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="501e3-127">Details zur Website-, Topologie-und Komponentenplanung von lync Server 2013 finden Sie unter [Topologie-Grundlagen, die Sie vor dem Planen der lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) -und Referenz Topologien [in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="501e3-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="501e3-128">Details zur Integration von Komponenten vorheriger Versionen finden Sie unter [Unterstützte Migrationspfade und Koexistenz Szenarien in lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="501e3-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501e3-129">Gestreckte Pools werden für die Serverrollen Front End, Edge, Mediation und Director nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="501e3-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="501e3-130">Zentrale Standort Topologien und-Komponenten (lokal)</span><span class="sxs-lookup"><span data-stu-id="501e3-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="501e3-131">Obwohl eine zentrale Standorttopologie einen Front-End-Pool oder einen Standard Edition-Server enthalten muss, kann jede zentrale Website auch Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="501e3-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="501e3-132">Mehrere Front-End-Pools, die sich in der gleichen Domäne oder in verschiedenen Domänen befinden können.</span><span class="sxs-lookup"><span data-stu-id="501e3-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="501e3-133">Allerdings müssen sich alle Front-End-Server in einem Front-End-Pool und der Back-End-Server für diesen Pool in der gleichen Domäne befinden.</span><span class="sxs-lookup"><span data-stu-id="501e3-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="501e3-134">Mehrere Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="501e3-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="501e3-135">Office Web Apps Server, der mit Office Web Applications in lync Server 2013 verwendet wird, um die Freigabe und das Rendern von Microsoft PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="501e3-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="501e3-136">Edgeserver oder Edge-Pool in Ihrem Umkreisnetzwerk, wenn Sie möchten, dass Ihre Bereitstellung Föderationspartner, öffentliche Chat Verbindungen, ein Extensible Messaging and Presence Protocol (XMPP)-Gateway, Remotebenutzerzugriff, Teilnahme anonymer Benutzer in Besprechungen unterstützt oder Exchange Unified Messaging (um).</span><span class="sxs-lookup"><span data-stu-id="501e3-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="501e3-137">Sie können keine andere Serverrolle mit einem Edgeserver collocate.</span><span class="sxs-lookup"><span data-stu-id="501e3-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="501e3-138">Es wird empfohlen, den DNS-Lastenausgleich zu finden, wobei der Hardwarelastenausgleich ebenfalls unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="501e3-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="501e3-139">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="501e3-140">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="501e3-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="501e3-141">Ausführliche Informationen zu Lastenausgleichsanforderungen und-Support finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="501e3-142">Vermittlungs Server oder-Pool, wenn Sie Enterprise-VoIP oder Einwahlkonferenzen in einem Front-End-Pool am zentralen Standort unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="501e3-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="501e3-143">Je nachdem, wie Sie den Enterprise-VoIP-Support bereitstellen, können Sie den Vermittlungsserver in einem Front-End-Pool (Standard) collocate oder einen eigenständigen Vermittlungsserver oder-Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="501e3-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="501e3-144">Sie können DNS-, Hardware-oder Anwendungslastenausgleich verwenden (falls zutreffend), um den Datenverkehr vom Gateway-Peer eines Mediations Server-Pools zu verteilen, einschließlich eines PSTN-Gateways, einer IP-PBX-oder SIP-Trunk-Sitzung Border Control (SBC). Details zum Planen der entsprechenden Mediation Server-Topologie finden Sie unter [Bereitstellungsrichtlinien für Mediation Server in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="501e3-145">Server für beständigen Chat, wenn Sie möchten, dass Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen können, die im Laufe der Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="501e3-146">Zur Bereitstellung von mehr Kapazität und höherer Zuverlässigkeit kann Ihre Topologie mehrere Computer umfassen, auf denen der beständige Chat Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="501e3-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="501e3-147">Sie können keinen beständigen Chat Server mit anderen Serverrollen in einem Enterprise-Pool collocate.</span><span class="sxs-lookup"><span data-stu-id="501e3-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="501e3-148">Sie können den Server für beständigen Chat jedoch auf einem Standard Edition-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="501e3-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="501e3-149">Beständiger Chat erfordert eine Datenbank und, wenn Sie die beständige Chat-Compliance implementieren, eine Datenbank für beständigen Chat, aber die Datenbankenkönnen mit der Archivierungsdatenbank, der Überwachungsdatenbank oder auf dem Back-End-Server einer Enterprise-Edition zusammengestellt werden. Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="501e3-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="501e3-150">Weitere Informationen zum Planen der entsprechenden Server Topologie für beständigen Chat finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="501e3-151">Überwachung, wenn Sie die Datensammlung für die Audio/Video Quality of Experience (QoE) und die Anrufdetailaufzeichnung (CDR) für Enterprise-VoIP-und A/V-Konferenzen in Ihrer Bereitstellung unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="501e3-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="501e3-152">Optional können Sie den Microsoft System Center Operations Manager (vormals Microsoft Operations Manager) installieren, der mithilfe der Überwachung von CDR-und QoE-Daten nahezu in Echtzeit Warnungen generiert, die den Status der Anruf Zuverlässigkeit und Medienqualität anzeigen.</span><span class="sxs-lookup"><span data-stu-id="501e3-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="501e3-153">Die Überwachung wird bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="501e3-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="501e3-154">Für die Überwachung ist eine Datenbank erforderlich, aber die Datenbank kann mit der Archivierungsdatenbank, der persistent Chat-Datenbank, der beständigen Chat-Kompatibilitätsdatenbank oder auf dem Back-End-Server eines Enterprise Edition-Front-End-Pools zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="501e3-155">Archivierung, wenn Sie Chatnachrichten und Besprechungsinhalte (aus Kompatibilitätsgründen) in Ihrer Bereitstellung archivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="501e3-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="501e3-156">Die Archivierung erfolgt bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="501e3-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="501e3-157">Der Archivierungsspeicher erfordert entweder die Bereitstellung einer Archivierungsdatenbank oder die Integration in den Exchange 2013-Speicher.</span><span class="sxs-lookup"><span data-stu-id="501e3-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="501e3-158">Wenn Sie beides verwenden, das als *Gemischter Modus*bezeichnet wird, wird Exchange 2013-Speicher zum Speichern von Archivdaten für Benutzer verwendet, die sich in Exchange 2013 befinden, und die Archivierungsdatenbank wird verwendet, um Daten für alle anderen Benutzer in Ihrer Bereitstellung zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="501e3-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="501e3-159">Wenn Sie eine Archivierungsdatenbank benötigen, kann die Datenbank in der Überwachungsdatenbank, in der Datenbank für beständigen Chat, in der Kompatibilitätsdatenbank für beständigen Chat oder auf dem Back-End-Server eines Front-End-Pools zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="501e3-160">Details zum Planen der entsprechenden Archivierungs Topologie finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="501e3-161">Director-oder Director-Pool, wenn Sie die Widerstandsfähigkeit und Umleitung von lync Server 2013-Benutzeranforderungen an den Home-Pool des Benutzers erleichtern möchten, der entweder ein Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server sein kann.</span><span class="sxs-lookup"><span data-stu-id="501e3-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="501e3-162">Wir empfehlen, dass Sie einen Director-oder Director-Pool in jedem zentralen Standort bereitstellen, der den Zugriff durch externe Benutzer unterstützt, und an jedem zentralen Standort, an dem Sie ein oder mehrere Front-End-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="501e3-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="501e3-163">Jeder Director-Pool kann maximal zehn Directors enthalten.</span><span class="sxs-lookup"><span data-stu-id="501e3-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="501e3-164">Ein Director kann nicht mit einer anderen Serverrolle kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="501e3-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="501e3-165">Details zum Planen der entsprechenden Director-Topologie finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="501e3-166">Reverse Proxy, bei dem es sich nicht um eine lync Server 2013-Komponente handelt, aber erforderlich ist, wenn Sie die Freigabe von Webinhalten für verbundene Benutzer unterstützen oder Mobilitäts Datenverkehr unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="501e3-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="501e3-167">Sie können keinen Reverse-Proxy Server mit einer beliebigen lync Server 2013-Serverrolle collocate, aber Sie können Reverse-Proxy-Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverse-Proxy Server in Ihrer Organisation konfigurieren, der für andere verwendet wird. Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="501e3-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="501e3-168">Details zu Reverse-Proxyservern finden Sie unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501e3-169">In lync Server 2013 werden A/V-Konferenzen,-Überwachung und-Archivierung auf Front-End-Servern ausgeführt und sind keine separaten Server Rollen mehr.</span><span class="sxs-lookup"><span data-stu-id="501e3-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="501e3-170">Alle Front-End-Pools und Standard Edition-Server, die Sie an einem zentralen Standort bereitstellen, geben eine der folgenden Optionen frei, die Sie für die zentrale Website bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="501e3-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="501e3-171">Director-oder Director-Pool</span><span class="sxs-lookup"><span data-stu-id="501e3-171">Director or Director pool</span></span>

  - <span data-ttu-id="501e3-172">Eigenständiger Vermittlungs Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="501e3-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="501e3-173">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="501e3-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="501e3-174">Edgeserver oder Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="501e3-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="501e3-175">Server oder Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="501e3-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="501e3-176">Überwachung</span><span class="sxs-lookup"><span data-stu-id="501e3-176">Monitoring</span></span>

  - <span data-ttu-id="501e3-177">Archiving</span><span class="sxs-lookup"><span data-stu-id="501e3-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501e3-178">Wenn Sie die Integration von Exchange 2013 Unified Messaging unterstützen möchten, kann ein Exchange um-Server mit ihrer lync Server 2013-Bereitstellung implementiert werden, aber es handelt sich nicht um eine Komponente der lync Server 2013-Website.</span><span class="sxs-lookup"><span data-stu-id="501e3-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="501e3-179">Mehrere zentrale Websites können auch eine der folgenden Freigaben freigeben, die Sie auf einer zentralen Website bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="501e3-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="501e3-180">Eigenständiger Vermittlungs Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="501e3-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="501e3-181">Edgeserver oder Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="501e3-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="501e3-182">Server oder Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="501e3-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="501e3-183">Archiving</span><span class="sxs-lookup"><span data-stu-id="501e3-183">Archiving</span></span>

  - <span data-ttu-id="501e3-184">Überwachung</span><span class="sxs-lookup"><span data-stu-id="501e3-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501e3-185">Ein Exchange um-Server kann mit ihrer lync Server 2013-Bereitstellung implementiert und von mehreren zentralen Standorten freigegeben werden, ist aber keine Komponente der lync Server 2013-Website.</span><span class="sxs-lookup"><span data-stu-id="501e3-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="501e3-186">Details zu den Serverrollen und Funktionen von lync Server 2013 finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="501e3-187">Eine Zusammenfassung der Unterstützung von lync Server 2013 Server-Unterstützung finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="501e3-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="501e3-188">Zusätzlich zu den zuvor in diesem Abschnitt beschriebenen Serverrollen und Funktionen enthält lync Server 2013 zusätzliche Komponenten und Optionen, die einige oder alle der folgenden Elemente enthalten können:</span><span class="sxs-lookup"><span data-stu-id="501e3-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="501e3-189">Firewalls</span><span class="sxs-lookup"><span data-stu-id="501e3-189">Firewalls</span></span>

  - <span data-ttu-id="501e3-190">PSTN-Gateways (bei Bereitstellung von Enterprise-VoIP)</span><span class="sxs-lookup"><span data-stu-id="501e3-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="501e3-191">Exchange um-Server</span><span class="sxs-lookup"><span data-stu-id="501e3-191">Exchange UM Server</span></span>

  - <span data-ttu-id="501e3-192">DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="501e3-192">DNS load balancing</span></span>

  - <span data-ttu-id="501e3-193">Hardwaregeräte zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="501e3-193">Hardware load balancers</span></span>

  - <span data-ttu-id="501e3-194">SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="501e3-194">SQL Server databases</span></span>

  - <span data-ttu-id="501e3-195">Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="501e3-195">File shares</span></span>

<span data-ttu-id="501e3-196">Ausführliche Informationen zu allen lync Server 2013-Features,-Komponenten und-Optionen finden Sie in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="501e3-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="501e3-197">Topologien und Komponenten von Verzweigungs Websites (lokal)</span><span class="sxs-lookup"><span data-stu-id="501e3-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="501e3-198">Eine Verzweigungs Website ist einem zentralen Standort zugeordnet, und jede überlebensfähige Verzweigungs-Appliance an einer Zweigstelle ist einem Enterprise Edition-Front-End-Pool oder einem Standard Edition-Server auf dem zugehörigen zentralen Standort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="501e3-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="501e3-199">Zweigstellen Websites sind für den größten Teil ihrer Funktionalität vom zentralen Standort abhängig, sodass Komponenten an einer Zweigstelle nur die folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="501e3-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="501e3-200">Eine Survivable Branch-Appliance, die ein PSTN-Gateway (Public Switched Telephone Network) mit einigen lync-Server Funktionen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="501e3-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="501e3-201">Ein Vermittlungsserver kann mit der Instanz der Registrierungsstelle auf der Survivable Branch-Appliance zusammengestellt werden, und Sie können einen eigenständigen Vermittlungsserver oder einen Pool von Vermittlungsservern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="501e3-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="501e3-202">Ein Survival-Branch-Server, bei dem es sich um einen Server mit Windows Server handelt, auf dem die lync Server 2013-Registrierungs-und Mediationsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="501e3-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="501e3-203">Ein eigenständiges PSTN-Gateway (nicht Bestandteil der Survivable Branch-Appliance) und ein eigenständiger Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="501e3-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="501e3-204">Die Anforderungen für überlebensfähige Zweigstellenserver sind identisch mit den Anforderungen für eine beliebige lync Server 2013-Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="501e3-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

