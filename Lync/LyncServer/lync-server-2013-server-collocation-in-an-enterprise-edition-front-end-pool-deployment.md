---
title: Lync Server 2013 Server-Zusammenstellungen in einer Enterprise Edition-Front-End-Pool Bereitstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510282"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="b485d-102">Server Zusammenstellungen in einer Enterprise Edition-Front-End-Pool Bereitstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b485d-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b485d-103">_**Letztes Änderungsstand des Themas:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b485d-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b485d-104">In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013 Front-End-Pool-Bereitstellung collocate können.</span><span class="sxs-lookup"><span data-stu-id="b485d-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="b485d-105">Serverrollen</span><span class="sxs-lookup"><span data-stu-id="b485d-105">Server Roles</span></span>

<span data-ttu-id="b485d-106">In lync Server 2013 werden A/V-Konferenzdienst, Vermittlungsdienst, Überwachung und Archivierung auf dem Front-End-Server zusammengefasst, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b485d-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="b485d-107">Falls Sie den Vermittlungsserver nicht mit dem Front-End-Server verbinden möchten, können Sie ihn als eigenständigen Vermittlungsserver auf einem separaten Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b485d-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="b485d-108">Sie können einen vertrauenswürdigen Anwendungsserver mit dem Front-End-Server verbinden.</span><span class="sxs-lookup"><span data-stu-id="b485d-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="b485d-109">Die folgenden Serverrollen müssen auf jeweils einem separaten Computer bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="b485d-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="b485d-110">Director</span><span class="sxs-lookup"><span data-stu-id="b485d-110">Director</span></span>

  - <span data-ttu-id="b485d-111">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b485d-111">Edge Server</span></span>

  - <span data-ttu-id="b485d-112">Vermittlungsserver (sofern nicht gemeinsam mit dem Front-End-Server ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="b485d-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="b485d-113">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="b485d-113">Office Web Apps Server</span></span>

<span data-ttu-id="b485d-114">Sie können die Serverrolle "persistent Chat" nicht mit dem Front-End-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="b485d-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="b485d-115">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="b485d-115">Databases</span></span>

<span data-ttu-id="b485d-116">Sie können jede der folgenden Datenbanken auf demselben Datenbankserver ausführen:</span><span class="sxs-lookup"><span data-stu-id="b485d-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="b485d-117">Back-End-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b485d-117">Back-end database</span></span>

  - <span data-ttu-id="b485d-118">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="b485d-118">Monitoring database</span></span>

  - <span data-ttu-id="b485d-119">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="b485d-119">Archiving database</span></span>

  - <span data-ttu-id="b485d-120">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b485d-120">Persistent Chat database</span></span>

  - <span data-ttu-id="b485d-121">Kompatibilitätsdatenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b485d-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="b485d-122">Sie können eine oder alle diese Datenbanken in einer einzigen SQL Server Instanz collocate oder eine separate Instanz von SQL Server für jede verwenden, mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="b485d-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="b485d-123">Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzelne Datenbank für beständigen Chat enthalten.</span><span class="sxs-lookup"><span data-stu-id="b485d-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="b485d-124">Der Datenbankserver kann nicht mehr als eine Front-End-Pool, eine Archivierungs Bereitstellung und eine Überwachungs Bereitstellung unterstützen, kann jedoch eines der beiden unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="b485d-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="b485d-125">Die gemeinsame Ausführung einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b485d-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b485d-126">In lync Server 2013 haben Sie die Möglichkeit, den Archivierungsspeicher mit Exchange 2013 Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="b485d-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="b485d-127">Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie der Exchange-Speicher bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b485d-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b485d-128">Die gemeinsame Ausführung von Datenbanken wird zwar unterstützt, die Datenbanken können jedoch schnell wachsen.</span><span class="sxs-lookup"><span data-stu-id="b485d-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="b485d-129">Wenn Sie beispielsweise in Erwägung ziehen, die Archivierungsdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann.</span><span class="sxs-lookup"><span data-stu-id="b485d-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="b485d-130">Aus diesem Grund wird nicht empfohlen, mehrere Datenbanken abstimmen, insbesondere die Archivierungsdatenbank, die Datenbank für beständigen Chat oder die Kompatibilitätsdatenbank für beständigen Chat mit der Back-End-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b485d-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="b485d-131">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="b485d-131">File Share</span></span>

<span data-ttu-id="b485d-132">Die Dateifreigabe kann auf einem separaten Server oder auf demselben Server wie folgende Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b485d-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="b485d-133">Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="b485d-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="b485d-134">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="b485d-134">Archiving database</span></span>

  - <span data-ttu-id="b485d-135">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="b485d-135">Monitoring database</span></span>

  - <span data-ttu-id="b485d-136">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b485d-136">Persistent Chat database</span></span>

  - <span data-ttu-id="b485d-137">Kompatibilitätsdatenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b485d-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="b485d-138">Eine einzige Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (alle am gleichen Standort) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b485d-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b485d-139">In lync Server 2013 verwenden Überwachung und Archivierung die lync Server Dateifreigabe als Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b485d-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="b485d-140">Weitere Komponenten</span><span class="sxs-lookup"><span data-stu-id="b485d-140">Other Components</span></span>

<span data-ttu-id="b485d-141">Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber in Ihrer Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="b485d-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="b485d-142">Sie können jedoch Reverse-Proxy Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b485d-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="b485d-143">Sie können keine Exchange Unified Messaging (um) Komponente oder SharePoint-Komponente mit einer SharePoint Server Rolle collocate.</span><span class="sxs-lookup"><span data-stu-id="b485d-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

