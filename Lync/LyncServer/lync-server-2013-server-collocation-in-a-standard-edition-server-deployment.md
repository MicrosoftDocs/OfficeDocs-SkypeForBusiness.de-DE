---
title: Lync Server 2013 Server-nebeneinander in einer Standard Edition-Server-Bereitstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1122605aabea32d86fbacd1f23675fcdef687539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="a5294-102">Server Zusammenstellung in einer Standard Edition-Server-Bereitstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5294-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5294-103">_**Letztes Änderungsstand des Themas:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="a5294-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="a5294-104">In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013 Standard Edition-Server-Bereitstellung collocate können.</span><span class="sxs-lookup"><span data-stu-id="a5294-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="a5294-105">Serverrollen</span><span class="sxs-lookup"><span data-stu-id="a5294-105">Server Roles</span></span>

<span data-ttu-id="a5294-106">In lync Server 2013 werden A/V-Konferenzdienst, Vermittlungsdienst, Überwachung und Archivierung auf dem Standard Edition-Server zusammengefasst, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5294-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="a5294-107">Sie können den Vermittlungsdienst auf verschiedenen Servern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a5294-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="a5294-108">Sie können einen vertrauenswürdigen Andwendungsserver mit einem Standard Edition-Server verbinden.</span><span class="sxs-lookup"><span data-stu-id="a5294-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="a5294-109">Die folgenden Serverrollen müssen jede auf einem separaten Computer bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="a5294-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="a5294-110">Director</span><span class="sxs-lookup"><span data-stu-id="a5294-110">Director</span></span>

  - <span data-ttu-id="a5294-111">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="a5294-111">Edge Server</span></span>

  - <span data-ttu-id="a5294-112">Vermittlungsserver (sofern nicht gemeinsam mit dem Standard Edition-Server ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="a5294-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="a5294-113">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="a5294-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a5294-114">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="a5294-114">Databases</span></span>

<span data-ttu-id="a5294-115">Die SQL Server Express-Back-End-Datenbank wird standardmäßig mit dem Standard Edition-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="a5294-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="a5294-116">Sie kann nicht auf einen separaten Computer verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="a5294-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="a5294-117">Mit einer Ausnahme können Sie andere Datenbanken im Standard Edition-Server nicht collocate.</span><span class="sxs-lookup"><span data-stu-id="a5294-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="a5294-118">Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen, können Sie die Datenbank für beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat auf demselben Standard Edition-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="a5294-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="a5294-119">Sie können jede der folgenden Datenbanken mit einem einzigen Datenbankserver verbinden:</span><span class="sxs-lookup"><span data-stu-id="a5294-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="a5294-120">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="a5294-120">Monitoring database</span></span>

  - <span data-ttu-id="a5294-121">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="a5294-121">Archiving database</span></span>

  - <span data-ttu-id="a5294-122">Eine Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="a5294-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="a5294-123">Sie können diese Datenbanken einzeln oder alle in einer einzigen SQL-Instanz verbinden oder für jede eine separate SQL-Instanz verwenden, wobei folgende Beschränkungen gelten:</span><span class="sxs-lookup"><span data-stu-id="a5294-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="a5294-124">Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank (für einen Enterprise Edition-Front-End-Pool), eine einzige Überwachungsdatenbank, eine einzige Archivierungsdatenbank, eine einzige Datenbank für beständigen Chat und eine einzige Kompatibilitätsdatenbank für beständigen Chat enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5294-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="a5294-125">Der Datenbankserver kann nicht mehrere Enterprise Edition-Front-End-Pool, einen Server, auf dem die Archivierung durchführen wird, eine Überwachung, eine einzelne Datenbank für beständigen Chat und eine einzelne Datenbank für beständigen Chat, aber eine der beiden unterstützen. unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5294-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="a5294-126">Die gemeinsame Ausführung einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5294-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5294-127">In lync Server 2013 haben Sie die Möglichkeit, Überwachungs-und Archivierungsspeicher mit Exchange 2013 Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="a5294-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="a5294-128">Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie der Exchange-Speicher bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a5294-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a5294-129">Die gemeinsame Ausführung von Datenbanken wird zwar unterstützt, die Datenbanken können jedoch schnell wachsen.</span><span class="sxs-lookup"><span data-stu-id="a5294-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="a5294-130">Wenn Sie beispielsweise in Erwägung ziehen, die Archivierungsdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann.</span><span class="sxs-lookup"><span data-stu-id="a5294-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="a5294-131">Aus diesem Grund wird nicht empfohlen, mehrere Datenbanken abstimmen, insbesondere die Datenbank für Archivierungsdatenbank, beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat mit der Back-End-Datenbank eines Enterprise-Pool.</span><span class="sxs-lookup"><span data-stu-id="a5294-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="a5294-132">Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="a5294-132">File Shares</span></span>

<span data-ttu-id="a5294-133">Die Dateifreigabe kann ein separater Server sein oder mit dem gleichen Server wie die folgenden Komponenten (einzeln oder alle) verbunden werden:</span><span class="sxs-lookup"><span data-stu-id="a5294-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="a5294-134">Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="a5294-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="a5294-135">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="a5294-135">Archiving database</span></span>

  - <span data-ttu-id="a5294-136">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="a5294-136">Monitoring database</span></span>

  - <span data-ttu-id="a5294-137">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a5294-137">Persistent Chat database</span></span>

  - <span data-ttu-id="a5294-138">Kompatibilitätsdatenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a5294-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="a5294-139">Eine einzige Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (alle am gleichen Standort) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5294-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5294-140">In lync Server 2013 verwenden Überwachung und Archivierung die lync Server Dateifreigabe als Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="a5294-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="a5294-141">Weitere Komponenten</span><span class="sxs-lookup"><span data-stu-id="a5294-141">Other Components</span></span>

<span data-ttu-id="a5294-142">Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber in Ihrer Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5294-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="a5294-143">Sie können jedoch Reverse-Proxy Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5294-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="a5294-144">Sie können keine Exchange um Komponente oder SharePoint-Komponente mit einer lync Server 2013 Rolle collocate.</span><span class="sxs-lookup"><span data-stu-id="a5294-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

