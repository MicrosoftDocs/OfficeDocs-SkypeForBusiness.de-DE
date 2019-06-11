---
title: 'Lync Server 2013: Komponenten und Topologien für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434fd8216689b42e664b5b421101470ad984bf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="351c3-102">Komponenten und Topologien für die Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351c3-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351c3-103">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="351c3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="351c3-104">Wenn Sie lync Server 2013-Chat-und Konferenzinhalte archivieren möchten, können Sie die Archivierung in lync Server implementieren.</span><span class="sxs-lookup"><span data-stu-id="351c3-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="351c3-105">Archivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="351c3-105">Archiving Components</span></span>

<span data-ttu-id="351c3-106">Das Archivierungsfeature umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="351c3-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="351c3-107">**Archivierungs-Agents**.</span><span class="sxs-lookup"><span data-stu-id="351c3-107">**Archiving agents**.</span></span> <span data-ttu-id="351c3-108">Archivierungs-Agents (auch bekannt als Unified Data Collection Agents) werden auf jedem Front-End-Pool und Standard Edition-Server automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="351c3-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="351c3-109">Obwohl Archivierungs-Agents automatisch aktiviert werden, werden keine Nachrichten erfasst, bis die Archivierung aktiviert und entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="351c3-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="351c3-110">**Archivierungsdatenspeicher**.</span><span class="sxs-lookup"><span data-stu-id="351c3-110">**Archiving data storage**.</span></span> <span data-ttu-id="351c3-111">Bei der Datenspeicherung für lync Server 2013 kann es sich um eine der folgenden Optionen handeln:</span><span class="sxs-lookup"><span data-stu-id="351c3-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="351c3-112">Exchange 2013-Speicher.</span><span class="sxs-lookup"><span data-stu-id="351c3-112">Exchange 2013 storage.</span></span> <span data-ttu-id="351c3-113">Wenn Sie die Microsoft Exchange-Integrations Option aktivieren, verwenden Benutzerpostfächer, die sich auf dem Exchange 2013-Server befinden, den Exchange 2013-Speicher für archivierte Daten, jedoch nur, wenn die Postfächer in-situ-Speicher abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="351c3-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="351c3-114">SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="351c3-114">SQL Server storage.</span></span> <span data-ttu-id="351c3-115">Wenn Sie Benutzer in Ihrer Bereitstellung haben, die sich in lync Server 2013 befinden, können Sie Archivierungsdatenbanken einrichten, die eine unterstützte Version von SQL Server ausführen, um die Archivierung für diese Benutzer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="351c3-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="351c3-116">Die Archivierung erfordert auch Dateispeicher, doch die Archivierung verwendet denselben Dateispeicher wie die Front-End-Server oder den Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="351c3-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="351c3-117">Eine Liste der Hardware-und Softwareanforderungen für die Archivierung finden Sie unter unter [stützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) und [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="351c3-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="351c3-118">Unterstützte Topologien</span><span class="sxs-lookup"><span data-stu-id="351c3-118">Supported Topologies</span></span>

<span data-ttu-id="351c3-119">Sie können die Archivierung in jedem Pool mit Benutzern bereitstellen, für die Archivierungsunterstützung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="351c3-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="351c3-120">Die Archivierung wird auf Front-End-Servern in Enterprise Edition-Pools und auf Standard Edition-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="351c3-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="351c3-121">Archivierungsdaten Speicher können wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="351c3-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="351c3-122">In Exchange 2013-Speicher integriert</span><span class="sxs-lookup"><span data-stu-id="351c3-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="351c3-123">Bereitstellung mithilfe separater SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="351c3-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="351c3-124">Wenn Ihre Exchange 2013-Bereitstellung nicht alle Benutzer in ihrer lync Server-Bereitstellung umfasst, müssen Sie die Microsoft Exchange-Integration für die Benutzer verwenden, deren Postfächer auf Exchange 2013-Servern zu Hause sind, und Sie müssen getrennte SQL Server-Datenbanken für alle anderen bereitstellen. Lync-Benutzer, die für die Archivierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="351c3-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="351c3-125">Unterstützte Anordnung</span><span class="sxs-lookup"><span data-stu-id="351c3-125">Supported Collocation</span></span>

<span data-ttu-id="351c3-126">Lync Server 2013 unterstützt eine Vielzahl von Szenarien für die Zusammenfassung, wodurch Sie Flexibilität beim Speichern von Hardwarekosten haben, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie über eine kleine Organisation verfügen) oder einzelne Komponenten auf verschiedenen Servern ausführen (wenn Sie über eine größere Organisation, die Skalierbarkeit und Leistung benötigt).</span><span class="sxs-lookup"><span data-stu-id="351c3-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="351c3-127">Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.</span><span class="sxs-lookup"><span data-stu-id="351c3-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="351c3-128">Die Archivierung wird auf den Front-End-Servern eines Pools oder von Standard Edition-Servern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="351c3-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="351c3-129">Details zu den Komponenten, die sich dort befinden können, finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="351c3-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="351c3-130">Wenn Sie separate SQL Server-Datenbanken für die Archivierung verwenden, können Sie die Archivierungsdatenbank mit einer der folgenden collocate, anstatt Sie mit dem Exchange 2013-Speicher zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="351c3-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="351c3-131">Überwachungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="351c3-131">Monitoring database</span></span>

  - <span data-ttu-id="351c3-132">Back-End-Datenbank eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="351c3-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="351c3-p108">Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="351c3-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="351c3-136">Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder beider Datenbanken collocate, können Sie entweder eine einzelne SQL-Instanz für eine oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate SQL-Instanz verwenden, mit den folgenden Einschränkung</span><span class="sxs-lookup"><span data-stu-id="351c3-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="351c3-137">Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank, eine einzige Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="351c3-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="351c3-138">Ausführliche Informationen zur Anordnung aller Serverrollen und Datenbanken finden Sie unter unterstützte Server [in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="351c3-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

