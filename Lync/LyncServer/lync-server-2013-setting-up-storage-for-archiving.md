---
title: 'Lync Server 2013: Einrichten von Speicher für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6728c02e9aa73faceaa8b3e681a5cf9cc4c700cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="f721e-102">Einrichten von Speicher für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f721e-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f721e-103">_**Letztes Änderungsdatum des Themas:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f721e-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f721e-104">Der Archivierungsspeicher für lync Server 2013 umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f721e-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="f721e-105">\*\*\*\* Zum Speichern von Chat Inhalten sind Datenspeicher erforderlich.   </span><span class="sxs-lookup"><span data-stu-id="f721e-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="f721e-106">\*\*\*\*   Dateispeicher Dateispeicher ist erforderlich, um Konferenzdaten Speicher und Dateispeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f721e-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="f721e-107">Einrichten von Datenspeicher</span><span class="sxs-lookup"><span data-stu-id="f721e-107">Setting Up Data Storage</span></span>

<span data-ttu-id="f721e-108">Die Anforderungen für das Einrichten von Datenspeicher für die Archivierung in lync Server 2013 hängen davon ab, wie Archivierungsdaten gespeichert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="f721e-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="f721e-109">Integrieren Sie die lync Server 2013-Archivierung in Ihre Exchange-Bereitstellung, um Archivierungsdaten mithilfe des Exchange-Speichers zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f721e-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="f721e-110">Einrichten separater SQL Server-Datenbankserver zum Speichern von Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="f721e-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="f721e-111">Einrichten des Exchange-Speichers zum Archivieren von Daten</span><span class="sxs-lookup"><span data-stu-id="f721e-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="f721e-112">Das Einrichten von Exchange für die Speicherung von Archivierungsdaten setzt voraus, dass Ihre Exchange-Bereitstellung Exchange 2013 ausführt.</span><span class="sxs-lookup"><span data-stu-id="f721e-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="f721e-113">Darüber hinaus müssen sich Benutzerpostfächer auf dem Exchange 2013-Server befinden, und ihre Postfächer müssen in-situ-Speicher platziert werden.</span><span class="sxs-lookup"><span data-stu-id="f721e-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="f721e-114">Weitere Informationen zum Konfigurieren von Exchange 2013 finden Sie in der Exchange-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f721e-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="f721e-115">Einrichten von SQL Server-Datenbankservern zum Speichern von Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="f721e-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="f721e-116">Die Archivierung in lync Server 2013 erfordert, dass die archivierten Daten von der SQL Server-Datenbanksoftware gespeichert werden, es sei denn, Sie integrieren Ihre Bereitstellung in Exchange.</span><span class="sxs-lookup"><span data-stu-id="f721e-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="f721e-117">Für SQL Server-Archivierungsdatenbanken müssen Sie SQL Server auf dem Computer installieren, auf dem die Archivierungsdatenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f721e-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="f721e-118">Sie können dieselbe SQL-Instanz verwenden, die Sie für die Back-End-Datenbank eines Front-End-Pools verwenden.</span><span class="sxs-lookup"><span data-stu-id="f721e-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="f721e-119">Um eine optimale Leistung zu erzielen, sollten Sie die Archivierungsdatenbank auf einem Computer bereitstellen, der vom zentralen Verwaltungsspeicher getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="f721e-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="f721e-120">Ausführliche Informationen zu den abstimmen-Komponenten von lync Server 2013 finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="f721e-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f721e-121">Auf jedem Datenbankserver muss eine unterstützte Version von SQL Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f721e-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="f721e-122">Details zu den unterstützten Versionen finden Sie unter [Technische Voraussetzungen für die Archivierung in lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f721e-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="f721e-123">Sie müssen die SQL Server-Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="f721e-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="f721e-124">Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f721e-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="f721e-125">Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="f721e-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="f721e-126">Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span><span class="sxs-lookup"><span data-stu-id="f721e-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f721e-127">Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, die die Archivierungsdatenbank enthält, damit der standardmäßige Archivierungs-SQL Server-Wartungsauftrag auf der Grundlage der geplanten Basis ausgeführt werden kann. Steuerung des SQL Server-Agent-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f721e-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="f721e-128">Einrichten von Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="f721e-128">Setting Up File Storage</span></span>

<span data-ttu-id="f721e-129">Bei der Archivierung wird die von Ihnen festgelegte lync Server 2013-Dateifreigabe verwendet, wenn Sie Ihren Front-End-Pool oder Standard Edition-Server einrichten.</span><span class="sxs-lookup"><span data-stu-id="f721e-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="f721e-130">Sie können die für die Archivierung verwendete Dateifreigabe nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f721e-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="f721e-131">Ausführliche Informationen zu unterstützten Dateispeichersystemen finden Sie unter unter [Stützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="f721e-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

