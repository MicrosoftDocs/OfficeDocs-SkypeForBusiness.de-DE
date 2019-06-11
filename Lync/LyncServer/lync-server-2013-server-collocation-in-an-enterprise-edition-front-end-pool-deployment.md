---
title: 'Lync Server 2013: Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="6c195-102">Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c195-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c195-103">_**Letztes Änderungsdatum des Themas:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="6c195-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="6c195-104">In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013-collocate bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="6c195-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="6c195-105">Server Rollen</span><span class="sxs-lookup"><span data-stu-id="6c195-105">Server Roles</span></span>

<span data-ttu-id="6c195-106">In lync Server 2013 sind A/V-Konferenzdienst, Mediationsdienst, Überwachung und Archivierung auf dem Front-End-Server verfügbar, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6c195-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="6c195-107">Wenn Sie den Vermittlungsserver nicht mit dem Front-End-Server collocate möchten, können Sie ihn als eigenständigen Vermittlungsserver auf einem separaten Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6c195-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="6c195-108">Sie können einen vertrauenswürdigen Anwendungsserver mit dem Front-End-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="6c195-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="6c195-109">Die folgenden Serverrollen müssen jeweils auf einem separaten Computer bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="6c195-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="6c195-110">Director</span><span class="sxs-lookup"><span data-stu-id="6c195-110">Director</span></span>

  - <span data-ttu-id="6c195-111">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6c195-111">Edge Server</span></span>

  - <span data-ttu-id="6c195-112">Vermittlungsserver (falls nicht mit dem Front-End-Server)</span><span class="sxs-lookup"><span data-stu-id="6c195-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="6c195-113">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="6c195-113">Office Web Apps Server</span></span>

<span data-ttu-id="6c195-114">Sie können die Serverfunktion "beständiger Chat" nicht mit dem Front-End-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="6c195-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="6c195-115">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="6c195-115">Databases</span></span>

<span data-ttu-id="6c195-116">Sie können jede der folgenden Datenbanken auf demselben Datenbankserver collocate:</span><span class="sxs-lookup"><span data-stu-id="6c195-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="6c195-117">Back-End-Datenbank</span><span class="sxs-lookup"><span data-stu-id="6c195-117">Back-end database</span></span>

  - <span data-ttu-id="6c195-118">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="6c195-118">Monitoring database</span></span>

  - <span data-ttu-id="6c195-119">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="6c195-119">Archiving database</span></span>

  - <span data-ttu-id="6c195-120">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6c195-120">Persistent Chat database</span></span>

  - <span data-ttu-id="6c195-121">Kompatibilitätsdatenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6c195-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="6c195-122">Sie können jede oder alle dieser Datenbanken in einer einzelnen Instanz von SQL Server collocate oder eine separate Instanz von SQL Server für jeden verwenden, wobei die folgenden Einschränkungen gelten:</span><span class="sxs-lookup"><span data-stu-id="6c195-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="6c195-123">Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne persistent Chat-Datenbank und eine einzelne Datenbank für beständigen Chat enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c195-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="6c195-124">Der Datenbankserver kann nicht mehr als einen Front-End-Pool, eine Archivierungs Bereitstellung und eine Überwachungs Bereitstellung unterstützen, aber er kann jeweils eine davon unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c195-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="6c195-125">Sie können eine Dateifreigabe für die Datenbanken collocate, wie weiter unten in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c195-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c195-126">In lync Server 2013 haben Sie die Möglichkeit, den Archivierungsspeicher mit Exchange 2013-Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="6c195-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="6c195-127">Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie dem Exchange-Speicher bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6c195-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c195-128">Obwohl die Daten Bank Zusammenstellung unterstützt wird, kann die Größe der Datenbanken schnell zunehmen.</span><span class="sxs-lookup"><span data-stu-id="6c195-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="6c195-129">Wenn Sie beispielsweise die Archivierungsdatenbank mit anderen Datenbanken abstimmen, beachten Sie Folgendes: Wenn Sie die Nachrichten von mehr als wenigen Benutzern archivieren, kann der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß werden.</span><span class="sxs-lookup"><span data-stu-id="6c195-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="6c195-130">Aus diesem Grund empfehlen wir nicht, abstimmen mehrere Datenbanken, insbesondere die Archivierungsdatenbank, die persistente Chat-Datenbank, oder die beständige Chat-Kompatibilitätsdatenbank mit der Back-End-Datenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c195-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="6c195-131">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="6c195-131">File Share</span></span>

<span data-ttu-id="6c195-132">Die Dateifreigabe kann ein separater Server sein oder sich auf dem gleichen Server wie die folgenden befinden:</span><span class="sxs-lookup"><span data-stu-id="6c195-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="6c195-133">Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="6c195-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="6c195-134">Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="6c195-134">Archiving database</span></span>

  - <span data-ttu-id="6c195-135">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="6c195-135">Monitoring database</span></span>

  - <span data-ttu-id="6c195-136">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6c195-136">Persistent Chat database</span></span>

  - <span data-ttu-id="6c195-137">Kompatibilitätsdatenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6c195-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="6c195-138">Eine einzelne Dateifreigabe kann für mehrere Front-End-Pools, Standard Edition-Server (alle auf der gleichen Website), verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c195-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c195-139">In lync Server 2013 verwenden die Überwachung und Archivierung die lync Server-Dateifreigabe als Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="6c195-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="6c195-140">Andere Komponenten</span><span class="sxs-lookup"><span data-stu-id="6c195-140">Other Components</span></span>

<span data-ttu-id="6c195-141">Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013-Komponente handelt, aber für Ihre Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="6c195-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="6c195-142">Sie können jedoch eine Reverse-Proxy-Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverse-Proxy Server in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c195-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="6c195-143">Sie können keine Exchange Unified Messaging (um)-Komponente oder SharePoint-Komponente mit einer SharePoint Server-Rolle collocate.</span><span class="sxs-lookup"><span data-stu-id="6c195-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

