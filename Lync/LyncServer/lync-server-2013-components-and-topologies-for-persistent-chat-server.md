---
title: 'Lync Server 2013: Komponenten und Topologien für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9ab539b652fc1d6ae82883df1f8875a0257614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="aea71-102">Komponenten und Topologien für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aea71-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aea71-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="aea71-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="aea71-104">Der Server für beständigen Chat unterstützt Konfigurationen mit einem einzelnen Server und Konfigurationen mit mehreren Servern.</span><span class="sxs-lookup"><span data-stu-id="aea71-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="aea71-105">Der Server für beständigen Chat kann auch auf einem lync Server 2013 Standard Edition-Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="aea71-106">Diese Konfigurationen bestehen aus den folgenden Server Komponenten und Topologien für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="aea71-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="aea71-107">Server Komponenten für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="aea71-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="aea71-108">Für die Installation der neuesten Version des Servers für beständigen Chat sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="aea71-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="aea71-109">Mindestens ein Computer, auf dem der Server für beständigen Chat läuft und die folgenden Dienste bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="aea71-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="aea71-110">Beständiger Chat Dienst</span><span class="sxs-lookup"><span data-stu-id="aea71-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="aea71-111">Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="aea71-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aea71-112">In lync Server 2013 ist der beständige Chat Webdienste für das Hochladen/Herunterladen von Dateien&nbsp;nun mit lync Server 2013 Front-End-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="aea71-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="aea71-113">Die Webdienste für den beständigen Chat für die chatroomverwaltung wird&nbsp;auch mit lync Server 2013 Front-End-Server zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="aea71-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="aea71-114">Server (mehrere Server, wenn die Spiegelung verwendet wird), die die SQL Server-Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat hosten, in der Chatroom-Inhalte,-Räume und-Kategorien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aea71-115">In der Back-End-Datenbank werden Chatverlaufs Daten gespeichert, einschließlich Informationen zu Kategorien und beständigen Chatrooms, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="aea71-116">Wenn die Kompatibilität aktiviert wurde, werden (mehrere Server, wenn die Spiegelung verwendet wird) die SQL Server-Back-End-Datenbank zum Hosten der Kompatibilitätsdatenbank für beständigen Chat, in der kompatibilitätsereignisse und Chat Inhalte für die Zwecke der Compliance gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="aea71-117">Verwenden Sie die lync Server-Systemsteuerung auf dem Computer, um den Server für beständigen Chat von einem separaten Computer aus zu verwalten (beispielsweise eine Verwaltungskonsole).</span><span class="sxs-lookup"><span data-stu-id="aea71-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="aea71-118">Dieser Computer muss dann in einer Active Directory-Domänendienste Domäne bereitgestellt werden, wobei mindestens ein globaler Katalogserver im Gesamtstrukturstamm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aea71-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="aea71-119">Ausführliche Informationen zu Hardware-und Softwareanforderungen für den Server für beständigen Chat finden Sie unter [Technische Anforderungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md)sowie [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="aea71-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="aea71-120">Unterstützte Zusammenstellungen</span><span class="sxs-lookup"><span data-stu-id="aea71-120">Supported Collocation</span></span>

<span data-ttu-id="aea71-121">Lync Server 2013 unterstützt eine Vielzahl von Zusammenstellungs Szenarien, die Ihnen die Flexibilität bieten, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie eine kleine Organisation haben) oder einzelne Komponenten auf unterschiedlichen Servern ausführen (wenn Sie über einen größere Organisation, die Skalierbarkeit und Leistung benötigt).</span><span class="sxs-lookup"><span data-stu-id="aea71-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="aea71-122">Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.</span><span class="sxs-lookup"><span data-stu-id="aea71-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="aea71-123">Der Kompatibilitätsdienst für beständigen Chat, falls die Kompatibilität aktiviert ist, wird mit dem lync Server 2013 Front-End-Server zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="aea71-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="aea71-124">Der Server für beständigen Chat kann im Standard Edition-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="aea71-125">Der Server für den Back-End-Server für beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat können auf dem Standard Edition-Server auf dem lokalen SQL Server Express Back-End-Server zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="aea71-126">Ausführliche Informationen zu den Komponenten, die dort zusammengefasst werden können, finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md) Zusammenstellungen in lync Server 2013 in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="aea71-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="aea71-127">Für lync Server 2013 Enterprise Edition können persistent Chat Server nicht auf dem Enterprise Edition-Server zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="aea71-128">Die SQL Server Datenbank für den Server für beständigen Chat kann mit der Datenbank des Back-End-Servers eines Enterprise Edition-Front-End-Pool zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="aea71-129">Die SQL Server-Datenbank für die Compliance für beständigen Chat kann auch mit der Back-End-Server-Datenbank eines Enterprise Edition-Pools zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="aea71-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aea71-130">Der Server, der die Datenbank für beständigen Chat hostet, kann andere Datenbanken hosten.</span><span class="sxs-lookup"><span data-stu-id="aea71-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="aea71-131">Wenn Sie jedoch die Datenbank für beständigen Chat mit anderen Datenbanken abstimmen, sollten Sie beachten, dass der von der Datenbank für beständigen Chat benötigte Speicherplatz sehr groß sein kann, wenn Sie die Nachrichten von mehreren Benutzern speichern.</span><span class="sxs-lookup"><span data-stu-id="aea71-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="aea71-132">Aus diesem Grund wird die abstimmen der Datenbank für beständigen Chat nicht mit der Back-End-Datenbank empfohlen.</span><span class="sxs-lookup"><span data-stu-id="aea71-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="aea71-133">Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank collocate, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken verwenden, oder Sie können eine separate Instanz von SQL Server für jede Datenbank verwenden, wobei die folgende Einschränkung gilt:</span><span class="sxs-lookup"><span data-stu-id="aea71-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="aea71-134">Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank und eine einzelne Datenbank für beständigen Chat enthalten.</span><span class="sxs-lookup"><span data-stu-id="aea71-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="aea71-135">Ausführliche Informationen zur gemeinsamen Nutzung aller Serverrollen und Datenbanken finden Sie unter [Supported Server Colocation in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="aea71-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="aea71-136">Server Topologien für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="aea71-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="aea71-137">Der Server für beständigen Chat unterstützt die folgenden Topologien:</span><span class="sxs-lookup"><span data-stu-id="aea71-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="aea71-138">Lync Server 2013 Server für den beständigen Server für die Enterprise Edition Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="aea71-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="aea71-139">Lync Server 2013 Server für beständigen Chat auf mehreren Servern Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="aea71-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="aea71-140">Lync Server 2013 Standard Edition-Server mit SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="aea71-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="aea71-141">Lync Server 2013 Standard Edition-Server-und beständiger Chat Server auf einem separaten Server mit Standard Edition-Server als nächster Hop-Server.</span><span class="sxs-lookup"><span data-stu-id="aea71-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="aea71-142">Sie können den Server für beständigen Chat mit dem Topologie-Generator zu ihrer lync Server 2013-Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aea71-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="aea71-143">Sie können Ihrer Topologie einen einzelnen Server oder einen Serverpool für beständigen Chat mit mehreren Servern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aea71-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aea71-144">Nachdem Sie einen Serverpool für beständigen Chat mit einem einzelnen Server mithilfe des Topologie-Generators erstellt haben, können Sie dem Pool keine weiteren Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aea71-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="aea71-145">Einzelservertopologie</span><span class="sxs-lookup"><span data-stu-id="aea71-145">Single-Server Topology</span></span>

<span data-ttu-id="aea71-146">Die minimale Konfiguration und die einfachste Bereitstellung für den Server für beständigen Chat ist ein einzelner Server für beständigen Chat Front-End-Server Topologie.</span><span class="sxs-lookup"><span data-stu-id="aea71-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="aea71-147">Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der Server für beständigen Chat ausgeführt wird (optional wird der Kompatibilitätsdienst ausgeführt, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server Datenbank hostet, als auch die erforderliche Kompatibilität, die SQL Server Datenbank zum Speichern des Compliance-Daten.</span><span class="sxs-lookup"><span data-stu-id="aea71-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aea71-148">Sie können keinem Serverpool für beständigen Chat, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aea71-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="aea71-149">Daher sollten Sie auch dann, wenn Sie nur einen einzigen Server haben, die Multiserver-Pool-Topologie verwenden, da Sie dann später weitere Server hinzufügen können, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aea71-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="aea71-150">Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen Server für beständigen Chat Front-End-Server mit Compliance.</span><span class="sxs-lookup"><span data-stu-id="aea71-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="aea71-151">**Einzelner dauerhafter Chatserver**</span><span class="sxs-lookup"><span data-stu-id="aea71-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="aea71-152">![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")</span><span class="sxs-lookup"><span data-stu-id="aea71-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="aea71-153">Topologie mit mehreren Servern</span><span class="sxs-lookup"><span data-stu-id="aea71-153">Multiple-Server Topology</span></span>

<span data-ttu-id="aea71-154">Um eine höhere Kapazität und Zuverlässigkeit zu bieten, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aea71-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="aea71-155">Die Topologie mit mehreren Servern kann bis zu vier aktive Computer mit persistent Chat Server umfassen (Hochverfügbarkeit und Notfall Wiederherstellungs Konfigurationen ermöglichen bis zu acht, aber nur vier können aktiv sein und die restlichen vier im Standbymodus).</span><span class="sxs-lookup"><span data-stu-id="aea71-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="aea71-156">Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem Serverpool für beständigen Chat mit 4 Servern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="aea71-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="aea71-157">Eine Topologie mit mehreren Servern ist identisch mit der Einzelservertopologie, mit dem Unterschied, dass mehrere Server den Server für beständigen Chat hosten und höher skalieren können.</span><span class="sxs-lookup"><span data-stu-id="aea71-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="aea71-158">Mehrere Computer mit persistent Chat Server sollten sich in derselben Active Directory-Domänendienste Domäne wie lync Server und dem Kompatibilitätsdienst befinden.</span><span class="sxs-lookup"><span data-stu-id="aea71-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="aea71-159">Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank läuft.</span><span class="sxs-lookup"><span data-stu-id="aea71-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="aea71-160">**Mehrere dauerhafte Chatserver**</span><span class="sxs-lookup"><span data-stu-id="aea71-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="aea71-161">![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")</span><span class="sxs-lookup"><span data-stu-id="aea71-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="aea71-162">Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="aea71-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="aea71-163">In einem Serverpool kommunizieren die Dienste für beständigen Chat und teilen Daten.</span><span class="sxs-lookup"><span data-stu-id="aea71-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="aea71-164">So ist beispielsweise der Chatverlauf, der ursprünglich für einen beständigen Chatdienst bereitgestellt wurde, in jedem persistent Chat-Dienst im System verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aea71-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="aea71-165">Auf eine Datei, die über einen beständigen Chatdienst hochgeladen wird, kann jeder beständige Chatdienst zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aea71-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="aea71-166">Benutzer können mit verschiedenen Front-End-Servern für beständigen Chat Server verbunden werden und können miteinander chatten und kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="aea71-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="aea71-167">Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird vom beständigen Chat Dienst verwendet, um zwischen sich selbst oder zu administrativen Zwecken zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="aea71-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

