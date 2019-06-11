---
title: 'Lync Server 2013: Konfigurieren des SQL Server-Clusters'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="45228-102">Konfigurieren des SQL Server-Clusters für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45228-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45228-103">_**Letztes Änderungsdatum des Themas:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="45228-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="45228-104">Microsoft lync Server 2013 unterstützt Clustering für SQL Server 2012 und SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="45228-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="45228-105">Details zu den unterstützten Informationen finden Sie unter [Unterstützung der Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="45228-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="45228-106">Sie sollten den SQL Server-Cluster einrichten und konfigurieren, bevor Sie den Enterprise Edition-Front-End-Server und die Back-End-Datenbank installieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="45228-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="45228-107">Bewährte Methoden und Setupanweisungen für Failovercluster in SQL Server 2012 finden Sie unter <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span><span class="sxs-lookup"><span data-stu-id="45228-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="45228-108">Informationen zum Failover-Clustering in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="45228-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="45228-p103">Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45228-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45228-111">Wenn Sie die Datenbanken auf dem SQL Server-basierten Server installieren und bereitstellen möchten, müssen Sie Mitglied der SQL Server sysadmin-Gruppe für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="45228-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="45228-112">Wenn Sie kein Mitglied der SQL Server-Gruppe sysadmin sind, müssen Sie die Gruppe so lange hinzufügen, bis die Datenbankdateien bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="45228-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="45228-113">Wenn Sie nicht Mitglied der sysadmin-Gruppe werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="45228-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="45228-114">Details zu den richtigen Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="45228-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="45228-115">So konfigurieren Sie das SQL Server-Clustering</span><span class="sxs-lookup"><span data-stu-id="45228-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="45228-116">Nachdem Sie die Installation und Konfiguration des SQL Server-Clusters abgeschlossen haben, definieren Sie den SQL Server-Speicher im Topologie-Generator mithilfe des virtuellen Clusternamens der SQL Server-Instanz (wie im Setup für SQL Server-Clustering konfiguriert) und der Instanz. der Name der SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="45228-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="45228-117">Anders als ein einzelner SQL Server-basierter Server verwenden Sie den virtuellen Knoten vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für einen gruppierten SQL Server-basierten Server.</span><span class="sxs-lookup"><span data-stu-id="45228-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45228-118">Die einzelnen Windows Server-Clusterknoten müssen nicht für den Topologie-Generator konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="45228-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="45228-119">Sie verwenden nur den virtuellen SQL Server-Clusternamen.</span><span class="sxs-lookup"><span data-stu-id="45228-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="45228-120">Wenn Sie die Datenbanken mithilfe des Topologie-Generators bereitstellen, müssen Sie Mitglied der SQL Server-Gruppe sysadmin sein.</span><span class="sxs-lookup"><span data-stu-id="45228-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="45228-121">Wenn Sie ein Mitglied der SQL Server sysadmin-Gruppe sind, aber nicht über Berechtigungen in der Domäne (beispielsweise eine SQL Server-Datenbankadministrator Rolle) verfügen, verfügen Sie über die Rechte zum Erstellen der Datenbanken, aber nicht zum Lesen der erforderlichen Informationen in lync Server.</span><span class="sxs-lookup"><span data-stu-id="45228-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="45228-122">Details zu den Benutzerrechten und Berechtigungen, die für die Bereitstellung von lync Server erforderlich sind, finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="45228-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="45228-123">Stellen Sie sicher, dass die Standardeinstellungen für den Ordner "Datenbank" und "Protokolldateien" den freigegebenen Datenträgern im SQL Server-Cluster mithilfe von SQL Server Management Studio ordnungsgemäß zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="45228-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="45228-124">Dies ist ein erforderliches Verfahren, wenn Sie Datenbanken mithilfe des Topologie-Generators erstellen.</span><span class="sxs-lookup"><span data-stu-id="45228-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45228-125">Wenn Sie SQL Server Management Studio nicht installiert haben, können Sie es installieren, indem Sie die SQL Server-Installation erneut ausführen und dann das Verwaltungstool als hinzugefügtes Feature für die vorhandene SQL Server-Bereitstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="45228-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="45228-126">Installieren Sie die Datenbanken für den SQL Server-basierten Server mithilfe von Topology Builder oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="45228-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="45228-127">Gehen Sie wie folgt vor, um den Topologie-Generator zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="45228-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="45228-128">Informationen zum Verwenden von Windows PowerShell-Cmdlets finden Sie unter [Datenbankinstallation mithilfe der lync Server-Verwaltungsshell in lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="45228-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="45228-129">So erstellen Sie Datenbanken mit dem Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="45228-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="45228-130">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="45228-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="45228-131">Im folgenden Verfahren wird davon ausgegangen, dass Sie Ihre Topologie im Topologie-Generator definiert und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="45228-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="45228-132">Details zum Definieren Ihrer Topologie finden Sie unter<A href="lync-server-2013-defining-and-configuring-the-topology.md">definieren und Konfigurieren der Topologie in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="45228-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="45228-133">Wenn Sie die Topologie mithilfe des Topologie-Generators veröffentlichen und die Datenbank konfigurieren möchten, müssen Sie sich als Benutzer mit den richtigen Benutzerrechten und Gruppenmitgliedschaften anmelden.</span><span class="sxs-lookup"><span data-stu-id="45228-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="45228-134">Details zu den erforderlichen Berechtigungen und Gruppenmitgliedschaften finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="45228-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="45228-135">Klicken Sie im Topologie-Generator während der Veröffentlichung der Topologie auf der Seite **Datenbankenerstellen** auf **erweitert**.</span><span class="sxs-lookup"><span data-stu-id="45228-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="45228-136">Auf der Seite " **Speicherort der Datenbankdatei auswählen** " gibt es zwei Optionen, die bestimmen, wie die Datenbankdateien im SQL Server-Cluster bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="45228-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="45228-137">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="45228-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="45228-138">**Ermitteln Sie den Speicherort der Datenbankdatei automatisch.**</span><span class="sxs-lookup"><span data-stu-id="45228-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="45228-139">Bei dieser Auswahl wird ein Algorithmus verwendet, um das Datenbankprotokoll und die Speicherorte der Datendateien basierend auf der Laufwerkskonfiguration auf dem auf SQL Server basierenden Server zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="45228-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="45228-140">Die Dateien werden so verteilt, dass Sie versuchen, eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="45228-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="45228-141">Verwenden Sie die Standardeinstellungen für SQL Server-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="45228-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="45228-142">Wenn Sie diese Option auswählen, werden die Protokoll-und Datendateien entsprechend den SQL Server-Instanzen Einstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="45228-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="45228-143">Nach der Bereitstellung der Datenbankdateien auf dem SQL Server kann der SQL Server-Datenbankadministrator die Dateien möglicherweise verschieben, um die Leistung für Ihre speziellen SQL Server-Konfigurationsanforderungen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="45228-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="45228-144">Führen Sie die Veröffentlichung der Topologie aus, und vergewissern Sie sich, dass während des Vorgangs keine Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="45228-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

