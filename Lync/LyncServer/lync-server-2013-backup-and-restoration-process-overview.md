---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b01230e84c9278d5540c21d41d9af1342479e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="b6d10-102">Übersicht über den Sicherungs-und Wiederherstellungsprozess für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6d10-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6d10-103">_**Letztes Änderungsdatum des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="b6d10-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="b6d10-104">Dieser Abschnitt enthält eine Übersicht über die Funktionsweise des Sicherungs-und Wiederherstellungsprozesses für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6d10-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="b6d10-105">Sie verwenden das gleiche Verfahren für alle Standard Edition-Server und Enterprise Edition-Server unabhängig von deren Standort.</span><span class="sxs-lookup"><span data-stu-id="b6d10-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="b6d10-106">Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b6d10-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="b6d10-107">Sie erstellen einen Sicherungsspeicherort als freigegebenen Ordner auf einem eigenständigen Computer, der nicht zu einem Pool gehört.</span><span class="sxs-lookup"><span data-stu-id="b6d10-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="b6d10-108">Auf den Speicherort der Sicherung wird in **$Backup**verwiesen.</span><span class="sxs-lookup"><span data-stu-id="b6d10-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="b6d10-109">Regelmäßig, planmäßig, sichern Sie alle lync Server-Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md) beschrieben werden, indem Sie die unter [Sichern von lync Server 2013 beschriebenen Verfahren ausführen. ](lync-server-2013-backing-up-lync-server.md)Der zentrale Verwaltungsspeicher umfasst alle Servereinstellungen und-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="b6d10-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="b6d10-110">Jedes Mal, wenn Sie eine nachfolgende Sicherung ausführen, erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, in dem Verweise **$Backup** .</span><span class="sxs-lookup"><span data-stu-id="b6d10-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="b6d10-111">Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b6d10-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="b6d10-112">Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den **$Backup** auf neue oder bereinigte Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="b6d10-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b6d10-113">Durch diesen Wiederherstellungsprozess werden keine Daten auf einem vorhandenen Serverzustand wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="b6d10-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="b6d10-114">Dieser Vorgang erfordert also, dass der Server sauber oder neu ist.</span><span class="sxs-lookup"><span data-stu-id="b6d10-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="b6d10-115">Damit Ihre Benutzer-und Konferenz Informationen bis zum Zeitpunkt des Fehlers wiederherstellbar sind, können Sie eine Disaster Recovery-Topologie mit gekoppelten Front-End-Pools implementieren, wie in [Planen für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6d10-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="b6d10-116">Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfiguration (Dynamic Host Configuration Protocol), Domänennamen, vollqualifizierte Computer Domänennamen (FQDNs), Dateispeicher Pfade usw. müssen zum Zeitpunkt der Wiederherstellung identisch sein, die Sie zum Zeitpunkt des Sichern Sie.</span><span class="sxs-lookup"><span data-stu-id="b6d10-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="b6d10-117">Wenn ein Server mit lync Server ausfällt, umfasst die Wiederherstellung die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="b6d10-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="b6d10-118">Installieren Sie das Betriebssystem auf einem neuen oder sauberen Computer mit demselben FQDN wie der fehlerhafte Computer.</span><span class="sxs-lookup"><span data-stu-id="b6d10-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="b6d10-119">Installieren Sie Zertifikate erneut.</span><span class="sxs-lookup"><span data-stu-id="b6d10-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="b6d10-120">Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b6d10-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="b6d10-121">Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren sowie Zugriffssteuerungslisten (ACLs) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b6d10-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="b6d10-122">Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="b6d10-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6d10-123">Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird mit Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="b6d10-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="b6d10-124">Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.</span><span class="sxs-lookup"><span data-stu-id="b6d10-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

