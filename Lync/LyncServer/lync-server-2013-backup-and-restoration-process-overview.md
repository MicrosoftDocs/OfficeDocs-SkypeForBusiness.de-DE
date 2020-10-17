---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94cebbc9a11e1857bed419c97f52f065326b1772
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504872"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="9a816-102">Sicherungs-und Wiederherstellungsprozess – Übersicht für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a816-102">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a816-103">_**Letztes Änderungsstand des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="9a816-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="9a816-104">Dieser Abschnitt enthält eine Übersicht darüber, wie der Sicherungs-und Wiederherstellungsprozess für lync Server 2013 funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9a816-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="9a816-105">Sie können unabhängig vom Standort für alle Standard Edition-Server und Enterprise Edition-Server dasselbe Verfahren anwenden.</span><span class="sxs-lookup"><span data-stu-id="9a816-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="9a816-106">Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9a816-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="9a816-107">Sie erstellen auf einem eigenständigen Computer, der nicht Teil eines Pools ist, einen Sicherungsspeicherort als freigegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="9a816-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="9a816-108">Auf den Speicherort der Sicherung wird in  **$Backup** verwiesen.</span><span class="sxs-lookup"><span data-stu-id="9a816-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="9a816-109">Auf einer regulären, geplanten Basis sichern Sie alle lync Server Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md) beschrieben werden, indem Sie die Verfahren unter [sichern lync Server 2013](lync-server-2013-backing-up-lync-server.md) der zentrale Verwaltungsspeicher enthält alle Server Einstellungen und-Konfigurationen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a816-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="9a816-110">Bei jedem Ausführen einer nachfolgenden Sicherung erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, auf den **$Backup** verweist.</span><span class="sxs-lookup"><span data-stu-id="9a816-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="9a816-111">Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9a816-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="9a816-112">Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den von **$Backup** verwiesen wird, auf neue oder saubere Computer.</span><span class="sxs-lookup"><span data-stu-id="9a816-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9a816-p103">Mit diesem Wiederherstellungsprozess werden Daten nicht auf einem Server im aktuellen Zustand wiederhergestellt. Der Prozess erfordert einen bereinigten oder neuen Server.</span><span class="sxs-lookup"><span data-stu-id="9a816-p103">This restoration process does not restore data onto an existing server state. That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="9a816-115">Damit Ihre Benutzer-und Konferenz Informationen zum Fehlerfall wiederhergestellt werden können, können Sie eine Notfall Wiederherstellungs Topologie mit paarweise gepaarten Front-End-Pools implementieren, wie in [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a816-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="9a816-116">Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfigurationen (Dynamic Host Configuration Protocol), Domänennamen, Computer-FQDNs (vollqualifizierte Domänennamen), Dateispeicherpfade usw. müssen zum Zeitpunkt der Wiederherstellung dieselben wie zum Zeitpunkt der Sicherung sein.</span><span class="sxs-lookup"><span data-stu-id="9a816-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="9a816-117">Wenn ein Server mit lync Server fehlschlägt, umfasst die Wiederherstellung die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="9a816-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="9a816-118">Installieren Sie das Betriebssystem auf einem neuen oder bereinigten Computer mit demselben FQDN wie der ausgefallene Computer.</span><span class="sxs-lookup"><span data-stu-id="9a816-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="9a816-119">Installieren Sie die Zertifikate neu.</span><span class="sxs-lookup"><span data-stu-id="9a816-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="9a816-120">Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9a816-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="9a816-121">Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren und Zugriffssteuerungslisten (ACLs) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9a816-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="9a816-122">Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="9a816-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a816-123">Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird durch Ausführen von Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="9a816-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="9a816-124">Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.</span><span class="sxs-lookup"><span data-stu-id="9a816-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

