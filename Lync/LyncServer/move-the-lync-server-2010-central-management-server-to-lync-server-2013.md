---
title: Verschieben des zentralen Verwaltungsservers mit lync Server 2010 auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="f063e-102">Verschieben des zentralen Verwaltungsservers mit lync Server 2010 auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f063e-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f063e-103">_**Letztes Änderungsdatum des Themas:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="f063e-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="f063e-104">Nachdem Sie die Migration von lync Server 2010 zu lync Server 2013 durchlaufen haben, müssen Sie den zentralen Verwaltungsserver von lync Server 2010 auf den lync Server 2013-Front-End-Server oder-Pool verschieben, bevor Sie den Legacy-lync Server 2010-Server entfernen können.</span><span class="sxs-lookup"><span data-stu-id="f063e-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="f063e-105">Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f063e-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="f063e-106">Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs.</span><span class="sxs-lookup"><span data-stu-id="f063e-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="f063e-107">Die lokale Datenbank erhält Replikat Updates über den lync Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f063e-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="f063e-108">Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="f063e-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="f063e-109">Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="f063e-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="f063e-110">Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und Konfigurieren von lync Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.</span><span class="sxs-lookup"><span data-stu-id="f063e-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="f063e-111">Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die zentralen Verwaltungsserver Datenbanken vom ursprünglichen Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="f063e-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="f063e-112">Informationen zum Entfernen der zentralen Verwaltungs Server-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f063e-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="f063e-113">Sie verwenden das Windows PowerShell **-Cmdlet Move-CsManagementServer** in der lync Server-Verwaltungsshell, um die Datenbank aus der lync Server 2010 SQL Server-Datenbank in die lync Server 2013 SQL Server-Datenbank zu verschieben und dann den SCP so zu aktualisieren, dass er auf den Standort des zentralen Verwaltungsservers von lync Server 2013 verweist.</span><span class="sxs-lookup"><span data-stu-id="f063e-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="f063e-114">Vorbereiten der lync Server 2013-Front-End-Server vor dem Verschieben des zentralen Verwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="f063e-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="f063e-115">Führen Sie die Verfahren in diesem Abschnitt aus, um die lync Server 2013-Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungs Server für lync Server 2010 verschieben.</span><span class="sxs-lookup"><span data-stu-id="f063e-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="f063e-116">Vorbereiten eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="f063e-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="f063e-117">Klicken Sie im Front-End-Pool von lync Server 2013 Enterprise Edition, in dem Sie den zentralen Verwaltungs Server umsiedeln möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="f063e-118">Sie müssen auch über die SQL Server-Datenbank sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank verfügen, in der Sie den zentralen Verwaltungsspeicher installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f063e-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="f063e-119">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f063e-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="f063e-120">Zum Erstellen des neuen zentralen Verwaltungsspeichers in der lync Server 2013 SQL Server-Datenbank geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="f063e-121">Vergewissern Sie sich, dass der Status des **lync Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="f063e-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="f063e-122">Vorbereiten eines Standard Edition-Front-End-Servers</span><span class="sxs-lookup"><span data-stu-id="f063e-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="f063e-123">Auf dem lync Server 2013 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver verschieben möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="f063e-124">Öffnen Sie den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f063e-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="f063e-125">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="f063e-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="f063e-126">Auf der Seite **Ausführungsbefehle** wird SQL Server Express als zentraler Verwaltungs Server installiert.</span><span class="sxs-lookup"><span data-stu-id="f063e-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="f063e-127">Es werden erforderliche Firewallregeln erstellt.</span><span class="sxs-lookup"><span data-stu-id="f063e-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="f063e-128">Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f063e-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f063e-129">Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="f063e-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="f063e-130">Dies ist auf die Installation von SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="f063e-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="f063e-131">Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="f063e-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="f063e-132">Zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem lync Server 2013 Standard Edition-Front-End-Server geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="f063e-133">Vergewissern Sie sich, dass der Status des **lync Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="f063e-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="f063e-134">So verschieben Sie den lync Server 2010 Central-Verwaltungs Server nach lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f063e-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="f063e-135">Auf dem lync Server 2013-Server, der der zentrale Verwaltungsserver sein soll: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="f063e-136">Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.</span><span class="sxs-lookup"><span data-stu-id="f063e-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="f063e-137">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f063e-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="f063e-138">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f063e-139">Wenn <CODE>Enable-CsTopology</CODE> dies nicht der Fall ist, beheben Sie das Problem, das verhindert, dass der Befehl abgeschlossen wird, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f063e-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="f063e-140">Wenn <STRONG>enable-CsTopology</STRONG> nicht erfolgreich ist, schlägt die Verschiebung fehl, und Sie verlässt Ihre Topologie möglicherweise in einem Zustand, in dem kein zentraler Verwaltungsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="f063e-141">Geben Sie auf dem lync Server 2013-Front-End-Server oder-Front-End-Pool in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="f063e-142">In der lync Server-Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte des aktuellen Zustands und des vorgeschlagenen Zustands angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f063e-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="f063e-143">Lesen Sie die Informationen sorgfältig durch, und bestätigen Sie, dass dies die beabsichtigte Quelle und das Ziel ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="f063e-144">Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Verschiebung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f063e-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="f063e-145">Überprüfen Sie alle Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="f063e-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="f063e-146">Öffnen Sie auf dem lync Server 2013-Server den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f063e-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="f063e-147">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f063e-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="f063e-148">Öffnen Sie auf dem lync Server 2010-Server den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f063e-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="f063e-149">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f063e-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="f063e-150">Starten Sie den lync Server 2013-Server neu.</span><span class="sxs-lookup"><span data-stu-id="f063e-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="f063e-151">Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft für den Zugriff auf die zentrale Verwaltungs Server-Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f063e-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="f063e-152">Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher erfolgt, geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f063e-153">Die Replikation kann einige Zeit dauern, bis alle aktuellen Replikate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f063e-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="f063e-154">So entfernen Sie nach einem Umzug lync Server 2010 Central Management Store-Dateien</span><span class="sxs-lookup"><span data-stu-id="f063e-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="f063e-155">Auf dem lync Server 2010-Server: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="f063e-156">Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.</span><span class="sxs-lookup"><span data-stu-id="f063e-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="f063e-157">Öffnen der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f063e-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f063e-158">Gehen Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist.</span><span class="sxs-lookup"><span data-stu-id="f063e-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="f063e-159">Wenn Sie die Dateien vor dem Abschließen der Replikation entfernen, werden Sie den Replikationsprozess unterbrechen und den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand belässt.</span><span class="sxs-lookup"><span data-stu-id="f063e-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="f063e-160">Verwenden Sie das Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> , um den Replikationsstatus zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f063e-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="f063e-161">Wenn Sie die zentralen Verwaltungsspeicher-Datenbankdateien vom lync Server 2010 Central-Verwaltungs Server entfernen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f063e-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="f063e-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f063e-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="f063e-163">Hierbei handelt \<es sich bei dem\> FQDN von SQL Server entweder um den lync Server 2010-Back-End-Server in einer Enterprise Edition-Bereitstellung oder um den FQDN des Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="f063e-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

