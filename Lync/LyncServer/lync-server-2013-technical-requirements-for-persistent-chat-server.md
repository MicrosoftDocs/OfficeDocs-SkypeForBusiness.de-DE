---
title: 'Lync Server 2013: Technische Voraussetzungen für beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="a84a3-102">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a84a3-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a84a3-103">_**Letztes Änderungsdatum des Themas:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="a84a3-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="a84a3-104">Jeder Computer, der den Server für beständigen Chat hostet, muss Zugriff auf eine vorhandene lync Server 2013-Topologie mit den folgenden Komponenten haben:</span><span class="sxs-lookup"><span data-stu-id="a84a3-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="a84a3-105">**Lync Server 2013, Front-End-Server.**  Der Front-End-Server ist die Grundlage für das SIP-Routing (Session Initiation Protocol), mit dem die Kommunikation zwischen Computern, auf denen der beständige Chat Server ausgeführt wird, und der Funktion für beständigen Chat ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="a84a3-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="a84a3-106">Bevor Sie mit der Bereitstellung des beständigen Chat Servers beginnen, überprüfen Sie die Bereitstellung von lync Server 2013, Standard Edition oder einem lync Server-Front-End-Pool und allen anderen internen Computern, auf denen lync Server ausgeführt wird, je nach Bedarf für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="a84a3-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="a84a3-107">In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die persistenten Chat-Daten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a84a3-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="a84a3-108">Server Anforderungen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a84a3-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="a84a3-109">Details zur empfohlenen Hardware für die Bereitstellung von lync Server und die neueste Version des beständigen Chat Servers finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="a84a3-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a84a3-110">Details zur Unterstützung des Betriebssystems Server und Tools für lync Server und beständiger Chat Server finden Sie unter Unterstützung von [Server-und Tools-Betriebssystem in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="a84a3-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a84a3-111">Details zu zusätzlicher Software, die für die Bereitstellung von persistent Chat Server erforderlich ist, finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a84a3-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="a84a3-112">Voraussetzungen für beständige Chat Server Software</span><span class="sxs-lookup"><span data-stu-id="a84a3-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84a3-113">Software</span><span class="sxs-lookup"><span data-stu-id="a84a3-113">Software</span></span></th>
<th><span data-ttu-id="a84a3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a84a3-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84a3-115">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="a84a3-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="a84a3-116">Wird vom beständigen Chat Server und dem beständigen Chat-Kompatibilitätsdienst verwendet, falls bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a84a3-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="a84a3-117">Datenbankanforderungen für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="a84a3-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="a84a3-118">Der Server für beständigen Chat verwendet die Datenbank für beständigen Chat, um Chat Verlaufs-, Konfigurations-und Benutzer Bereitstellungsdaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a84a3-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="a84a3-119">Optional wird die Compliance-Datenbank für beständigen Chat verwendet, um Kompatibilitätsdaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a84a3-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a84a3-120">Die persistent Chat-Datenbank (MGC) und die Compliance-Datenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL-Servern befinden.</span><span class="sxs-lookup"><span data-stu-id="a84a3-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="a84a3-121">Beim Vorbereiten einer Datenbankserverplattform müssen Sie sich vergewissern, dass jeder Computer die Hardwareanforderungen erfüllt, bevor Sie die erforderliche Software installieren.</span><span class="sxs-lookup"><span data-stu-id="a84a3-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="a84a3-122">Die Server Plattform für die persistenten Chat-Datenbankserver erfordert dieselbe Hardware wie der lync Server-Back-End-Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="a84a3-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="a84a3-123">Ausführliche Informationen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="a84a3-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a84a3-124">Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:</span><span class="sxs-lookup"><span data-stu-id="a84a3-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="a84a3-125">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a84a3-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="a84a3-126">Informationen zum Installieren von Microsoft SQL Server 2012 finden Sie unter "Installieren von SQL Server 2012" unter [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span><span class="sxs-lookup"><span data-stu-id="a84a3-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="a84a3-127">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a84a3-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="a84a3-128">Informationen zum Installieren von Microsoft SQL Server 2008 R2 finden Sie unter "SQL Server-Installation (SQL Server 2008 R2)" unter [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span><span class="sxs-lookup"><span data-stu-id="a84a3-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="a84a3-129">Zertifikatanforderungen für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="a84a3-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="a84a3-130">Details zum Abrufen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Datei speichern finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a84a3-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

