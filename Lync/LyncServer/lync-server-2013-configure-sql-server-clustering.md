---
title: 'Lync Server 2013: Konfigurieren von SQL Server Clustering'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb7db93813bdc7ed06398ce73d00f51ce5a60fe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="775b1-102">Konfigurieren von SQL Server Clustering für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775b1-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="775b1-103">_**Letztes Änderungsstand des Themas:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="775b1-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="775b1-104">Microsoft lync Server 2013 unterstützt Clustering für SQL Server 2012 und SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="775b1-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="775b1-105">Ausführliche Informationen zu den unterstützten Funktionen finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="775b1-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="775b1-106">Sie sollten den SQL Server Cluster einrichten und konfigurieren, bevor Sie die Enterprise Edition-Front-End-Server und die Back-End-Datenbank installieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="775b1-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="775b1-107">Bewährte Methoden und Setupanweisungen für die Failover-Clusterunterstützung in SQL Server 2012 finden <https://technet.microsoft.com/library/hh231721.aspx>Sie unter.</span><span class="sxs-lookup"><span data-stu-id="775b1-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="775b1-108">Informationen zur Failover-Clusterunterstützung in SQL Server 2008 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="775b1-108">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="775b1-109">Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="775b1-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="775b1-110">SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="775b1-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="775b1-111">Für die Installation und Bereitstellung der Datenbanken auf dem SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe "sysadmin" für den SQL Server-basierten Server sein, auf dem die Datenbankdateien installiert werden.</span><span class="sxs-lookup"><span data-stu-id="775b1-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="775b1-112">Wenn Sie kein Mitglied der SQL Server-Gruppe "sysadmin" sind, müssen Sie anfordern, dieser Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="775b1-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="775b1-113">Wenn Sie nicht zur Gruppe "sysadmin" hinzugefügt werden können, stellen Sie Ihrem SQL Server-Datenbankadministrator das Skript zur Konfiguration und Bereitstellung der Datenbanken bereit.</span><span class="sxs-lookup"><span data-stu-id="775b1-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="775b1-114">Ausführliche Informationen zu den richtigen Benutzerrechten und-Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="775b1-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="775b1-115">So konfigurieren Sie das SQL Server-Clustering</span><span class="sxs-lookup"><span data-stu-id="775b1-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="775b1-116">Nachdem Sie die Installation und Konfiguration von SQL Server Clustering abgeschlossen haben, definieren Sie den SQL Server Speicher im Topologie-Generator mithilfe des virtuellen Clusternamens SQL Server Instanz (wie im Setup für SQL Server Clustering konfiguriert) und der Instanz Name der SQL Server Datenbank.</span><span class="sxs-lookup"><span data-stu-id="775b1-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="775b1-117">Anders als bei einem einzelnen SQL Server-basierten Server verwenden Sie für einen geclusterten SQL Server-basierten Server den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des virtuellen Knotens.</span><span class="sxs-lookup"><span data-stu-id="775b1-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="775b1-118">Die einzelnen Windows Server-Clusterknoten müssen nicht für den Topologie-Generator konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="775b1-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="775b1-119">Sie verwenden ausschließlich den virtuellen SQL Server-Clusternamen.</span><span class="sxs-lookup"><span data-stu-id="775b1-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="775b1-120">Wenn Sie den Topologie-Generator zum Bereitstellen Ihrer Datenbanken verwenden, müssen Sie Mitglied der SQL Server sysadmin-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="775b1-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="775b1-121">Wenn Sie Mitglied der SQL Server sysadmin-Gruppe sind, aber keine Rechte in der Domäne haben (beispielsweise eine SQL Server-Datenbankadministrator Rolle), haben Sie die Berechtigung zum Erstellen der Datenbanken, aber nicht zum Lesen der erforderlichen Informationen in lync Server.</span><span class="sxs-lookup"><span data-stu-id="775b1-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="775b1-122">Ausführliche Informationen zu den Benutzerrechten und-Berechtigungen, die für die Bereitstellung von lync Server erforderlich sind, finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="775b1-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="775b1-p108">Stellen Sie mithilfe von SQL Server Management Studio sicher, dass die Standardordner für Datenbank und Protokolldateien den richtigen Datenträgerfreigaben im SQL Server-Cluster zugeordnet sind. Dieses Verfahren ist erforderlich, wenn Sie Datenbanken mit dem Topologie-Generator erstellen.</span><span class="sxs-lookup"><span data-stu-id="775b1-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="775b1-125">Wenn Sie SQL Server Management Studio nicht installiert haben, können Sie die Installation nachholen, indem Sie die SQL Server-Installation erneut ausführen und das Verwaltungstool als zusätzliche Funktion für die vorhandene SQL Server-Bereitstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="775b1-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="775b1-126">Installieren Sie die Datenbanken für den SQL Server basierten Server entweder mithilfe des Topologie-Generators oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="775b1-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="775b1-127">Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="775b1-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="775b1-128">Informationen zum Verwenden von Windows PowerShell-Cmdlets finden Sie unter [Database Installation using lync Server-Verwaltungsshell in lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="775b1-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="775b1-129">So erstellen Sie Datenbanken mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="775b1-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="775b1-130">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="775b1-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="775b1-131">Im folgenden Verfahren wird davon ausgegangen, dass Sie Ihre Topologie im Topologie-Generator definiert und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="775b1-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="775b1-132">Ausführliche Informationen zum Definieren Ihrer Topologie finden Sie unter<A href="lync-server-2013-defining-and-configuring-the-topology.md">definieren und Konfigurieren der Topologie in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="775b1-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="775b1-133">Um mit dem Topologie-Generator die Topologie zu veröffentlichen und die Datenbank zu konfigurieren, müssen Sie als ein Benutzer mit den geeigneten Benutzerrechten und Gruppenmitgliedschaften angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="775b1-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="775b1-134">Ausführliche Informationen zu den erforderlichen Rechten und Gruppenmitgliedschaften finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="775b1-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="775b1-135">Klicken Sie beim Veröffentlichen der Topologie im Topologie-Generator auf der Seite **Datenbankenerstellen** auf **erweitert**.</span><span class="sxs-lookup"><span data-stu-id="775b1-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="775b1-p111">Auf der Seite **Speicherort für Datenbankdateien auswählen** stehen zwei Optionen zur Verfügung, mit denen festgelegt wird, wie Datenbankdateien im SQL Server-Cluster bereitgestellt werden. Wählen Sie eine der beiden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="775b1-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="775b1-138">**Ermitteln Sie automatisch den Speicherort der Datenbankdatei.**</span><span class="sxs-lookup"><span data-stu-id="775b1-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="775b1-139">Diese Option verwendet einen Algorithmus zur Festlegung der Speicherorte für Datenbankprotokoll und Datendateien, basierend auf der Laufwerkkonfiguration auf dem SQL Server-basierten Server.</span><span class="sxs-lookup"><span data-stu-id="775b1-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="775b1-140">Die Dateien werden so verteilt, dass eine optimale Leistung erzielt wird.</span><span class="sxs-lookup"><span data-stu-id="775b1-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="775b1-141">Standardpfade der SQL Server-Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="775b1-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="775b1-142">Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den SQL Server-Instanzeneinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="775b1-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="775b1-143">Nach Bereitstellung der Datenbankdateien auf dem SQL Server-basierten Server kann der SQL Server-Datenbankadministrator die Dateien an einen anderen Speicherort verschieben, um gemäß den jeweiligen SQL Server-Konfigurationsanforderungen die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="775b1-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="775b1-144">Schließen Sie die Veröffentlichung der Topologie ab, und stellen Sie sicher, dass während des Vorgangs keine Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="775b1-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

