---
title: 'Lync Server 2013: Einrichten des Speichers für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab7e22d4ff0e34d903fa0306d971705c5455b2f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521782"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="cb939-102">Einrichten des Speichers für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb939-102">Setting up storage for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb939-103">_**Letztes Änderungsstand des Themas:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="cb939-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="cb939-104">Der Archivierungsspeicher für lync Server 2013 umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb939-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="cb939-105">**Datenspeicherung**     Datenspeicher ist erforderlich, um Chatinhalte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cb939-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="cb939-106">**Dateispeicher**     Dateispeicher ist erforderlich, um die Inhaltsdaten Speicherung und den Dateispeicher für Konferenzen (Besprechungen) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cb939-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="cb939-107">Einrichten des Datenspeichers</span><span class="sxs-lookup"><span data-stu-id="cb939-107">Setting Up Data Storage</span></span>

<span data-ttu-id="cb939-108">Voraussetzungen für das Einrichten des Datenspeichers für die Archivierung in lync Server 2013 hängen davon ab, wie Sie Archivierungsdaten speichern möchten:</span><span class="sxs-lookup"><span data-stu-id="cb939-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="cb939-109">Integrieren Sie lync Server 2013 Archivierung in Ihre Exchange-Bereitstellung, um Archivierungsdaten mithilfe des Exchange-Speichers zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cb939-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="cb939-110">Richten Sie separate SQL Server-Datenbankserver zum Speichern von Archivierungsdaten ein.</span><span class="sxs-lookup"><span data-stu-id="cb939-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="cb939-111">Einrichten des Exchange-Speichers für Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="cb939-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="cb939-112">Das Einrichten von Exchange für die Speicherung von Archivierungsdaten erfordert, dass Ihre Exchange-Bereitstellung Exchange 2013 ausführt.</span><span class="sxs-lookup"><span data-stu-id="cb939-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="cb939-113">Darüber hinaus müssen Benutzerpostfächer auf dem Exchange 2013-Server verwaltet werden, und ihre Postfächer müssen in In-Place Aufbewahrungsbereich verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cb939-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="cb939-114">Ausführliche Informationen zum Konfigurieren von Exchange 2013 finden Sie in der Exchange-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cb939-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="cb939-115">Einrichten von SQL Server Datenbankservern für die Speicherung von Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="cb939-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="cb939-116">Für die Archivierung in lync Server 2013 müssen die archivierten Daten von der SQL Server-Datenbanksoftware gespeichert werden, es sei denn, Sie integrieren Ihre Bereitstellung in Exchange.</span><span class="sxs-lookup"><span data-stu-id="cb939-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="cb939-117">Für SQL Server Archivierungsdatenbanken müssen Sie SQL Server auf dem Computer installieren, auf dem die Archivierungsdatenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cb939-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="cb939-118">Sie können dieselbe SQL-Instanz verwenden, die Sie für die Back-End-Datenbank eines Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb939-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="cb939-119">Um eine optimale Leistung zu erzielen, sollten Sie die Archivierungsdatenbank auf einem Computer bereitstellen, der vom zentralen Verwaltungsspeicher getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="cb939-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="cb939-120">Ausführliche Informationen zu abstimmen lync Server 2013 Komponenten finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md) Zusammenstellungen in lync Server 2013 in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cb939-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cb939-121">Auf jedem Datenbankserver muss eine unterstützte Version von SQL Server installiert sein.</span><span class="sxs-lookup"><span data-stu-id="cb939-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="cb939-122">Ausführliche Informationen zu den unterstützten Versionen finden Sie unter [Technical Requirements for Archiving in lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cb939-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="cb939-123">Sie müssen die SQL Server Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb939-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="cb939-124">Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Administratorrechte und-Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb939-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="cb939-125">Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="cb939-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="cb939-126">Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .</span><span class="sxs-lookup"><span data-stu-id="cb939-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb939-127">Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, die das Archivierungsdatenbank aufweist, damit der standardmäßige Archivierungs SQL Server-Wartungsauftrag unter der Kontrolle des SQL Server Agent-Diensts planmäßig ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb939-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="cb939-128">Einrichten des Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="cb939-128">Setting Up File Storage</span></span>

<span data-ttu-id="cb939-129">Bei der Archivierung wird die lync Server 2013 Dateifreigabe verwendet, die Sie beim Einrichten Ihrer Front-End-Pool oder Standard Edition-Server angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="cb939-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="cb939-130">Die für die Archivierung verwendete Dateifreigabe kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb939-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="cb939-131">Ausführliche Informationen zu unterstützten Dateispeichersystemen finden Sie unter [File Storage Support in lync Server 2013](lync-server-2013-file-storage-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cb939-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

