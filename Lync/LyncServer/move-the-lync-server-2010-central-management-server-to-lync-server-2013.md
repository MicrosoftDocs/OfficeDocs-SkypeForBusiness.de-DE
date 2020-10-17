---
title: Legen Sie den lync Server 2010 zentralen Verwaltungs Server auf lync Server 2013
description: Legen Sie den lync Server 2010 zentralen Verwaltungs Server in lync Server 2013.
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
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571281"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="e38f7-103">Legen Sie den lync Server 2010 zentralen Verwaltungs Server auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38f7-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e38f7-104">_**Letztes Änderungsstand des Themas:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="e38f7-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="e38f7-105">Nachdem Sie von lync Server 2010 zu lync Server 2013 migriert haben, müssen Sie den lync Server 2010 zentralen Verwaltungsserver in den lync Server 2013 Front-End-Server oder-Pool verschieben, bevor Sie den Legacy lync Server 2010 Server entfernen können.</span><span class="sxs-lookup"><span data-stu-id="e38f7-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="e38f7-106">Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Lese-/Schreibzugriff-Kopie der Datenbank von der Front-End-Server gespeichert wird, die den zentralen Verwaltungsserver enthält.</span><span class="sxs-lookup"><span data-stu-id="e38f7-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="e38f7-107">Jeder Computer in der Topologie, einschließlich der Front-End-Server, die den zentralen Verwaltungs Server enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server Datenbank (standardmäßig RTCLOCAL), die während des Setups und der Bereitstellung auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e38f7-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="e38f7-108">Die lokale Datenbank erhält Replikat Aktualisierungen über den lync Server Replikat Replikationsdienst-Agent, der auf allen Computern als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e38f7-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="e38f7-109">Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="e38f7-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="e38f7-110">Auf den Speicherort der Master Datenbank wird in Active Directory-Domänendienste von einem Dienststeuerungspunkt (Service Control Points, SCP) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e38f7-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="e38f7-111">Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und konfigurieren lync Server verwenden den SCP zum Auffinden des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="e38f7-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="e38f7-112">Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken des zentralen Verwaltungsservers aus dem ursprünglichen Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="e38f7-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="e38f7-113">Informationen zum Entfernen der Datenbanken des zentralen Verwaltungsservers finden Sie unter [Entfernen der SQL Server Datenbank für ein Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e38f7-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="e38f7-114">Verwenden Sie das Windows PowerShell-Cmdlet " **CsManagementServer** " im lync Server-Verwaltungsshell, um die Datenbank aus der lync Server 2010 SQL Server-Datenbank in die lync Server 2013 SQL Server-Datenbank zu versetzen, und aktualisieren Sie dann den SCP so, dass er auf den Standort des lync Server 2013 zentralen Verwaltungsservers verweist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="e38f7-115">Vorbereiten lync Server 2013 Front-End-Server vor dem Verschieben des zentralen Verwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="e38f7-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="e38f7-116">Verwenden Sie die Verfahren in diesem Abschnitt, um die lync Server 2013-Front-End-Server vorzubereiten, bevor Sie den lync Server 2010 zentralen Verwaltungs Server migrieren.</span><span class="sxs-lookup"><span data-stu-id="e38f7-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="e38f7-117">So bereiten Sie eine Enterprise Edition-Front-End-Pool vor</span><span class="sxs-lookup"><span data-stu-id="e38f7-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="e38f7-118">Klicken Sie auf der lync Server 2013 Enterprise Edition-Front-End-Pool, an der Sie den zentralen Verwaltungs Server verschieben möchten: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e38f7-119">Sie müssen auch SQL Server Datenbank-sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank haben, in der Sie den zentralen Verwaltungsspeicher installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e38f7-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="e38f7-120">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e38f7-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="e38f7-121">Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers in der lync Server 2013 SQL Server Datenbank im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e38f7-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="e38f7-122">Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="e38f7-123">So bereiten Sie eine Standard Edition vor Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e38f7-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="e38f7-124">Auf der lync Server 2013 Standard Edition-Front-End-Server, in der Sie den zentralen Verwaltungs Server verschieben möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell installiert ist, als Mitglied der **RTCUniversalServerAdmins** -Gruppe.</span><span class="sxs-lookup"><span data-stu-id="e38f7-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="e38f7-125">Öffnen Sie denLync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e38f7-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="e38f7-126">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="e38f7-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="e38f7-127">Auf der Seite **Befehle werden ausgeführt** wird SQL Server Express als zentraler Verwaltungs Server installiert.</span><span class="sxs-lookup"><span data-stu-id="e38f7-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="e38f7-128">Die erforderlichen Firewallregeln werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="e38f7-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="e38f7-129">Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e38f7-130">Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e38f7-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="e38f7-131">Dies ist auf die Installation des SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="e38f7-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="e38f7-132">Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.</span><span class="sxs-lookup"><span data-stu-id="e38f7-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="e38f7-133">Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem lync Server 2013 Standard Edition-Front-End-Server im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e38f7-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="e38f7-134">Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="e38f7-135">So legen Sie den lync Server 2010 zentralen Verwaltungs Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38f7-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="e38f7-136">Auf dem lync Server 2013 Server, der als zentraler Verwaltungsserver verwendet wird: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e38f7-137">Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e38f7-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="e38f7-138">Öffnen Sie lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e38f7-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="e38f7-139">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e38f7-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e38f7-140">Wenn <CODE>Enable-CsTopology</CODE> nicht erfolgreich ist, lösen Sie das Problem, dass der Befehl nicht abgeschlossen ist, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e38f7-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="e38f7-141">Wenn <STRONG>enable-CsTopology</STRONG> nicht erfolgreich ist, tritt bei der Migration ein Fehler auf, und Ihre Topologie kann in einem Zustand bleiben, in dem kein zentraler Verwaltungsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="e38f7-142">Geben Sie im lync Server 2013 Front-End-Server oder Front-End-Pool im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e38f7-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="e38f7-143">Lync Server-Verwaltungsshell zeigt die Server, Dateispeicher, Datenbankspeicher und Dienstverbindungspunkte des aktuellen Status und des Status vorgeschlagen an.</span><span class="sxs-lookup"><span data-stu-id="e38f7-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="e38f7-144">Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quelle und das Ziel ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="e38f7-145">Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Bewegung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e38f7-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="e38f7-146">Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese.</span><span class="sxs-lookup"><span data-stu-id="e38f7-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="e38f7-147">Öffnen Sie auf dem lync Server 2013 Server den Assistenten für die lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e38f7-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="e38f7-148">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: lync Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e38f7-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="e38f7-149">Öffnen Sie auf dem lync Server 2010 Server den Assistenten für die lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e38f7-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="e38f7-150">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: lync Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e38f7-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="e38f7-151">Starten Sie den lync Server 2013 Server neu.</span><span class="sxs-lookup"><span data-stu-id="e38f7-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="e38f7-152">Dies ist aufgrund einer Gruppen Mitgliedschaftsänderung für den Zugriff auf die Datenbank des zentralen Verwaltungsservers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e38f7-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="e38f7-153">Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher ausgeführt wird, geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e38f7-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e38f7-154">Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e38f7-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="e38f7-155">So entfernen Sie nach einer Migration lync Server 2010 zentralen Verwaltungsspeicher Dateien</span><span class="sxs-lookup"><span data-stu-id="e38f7-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="e38f7-156">Auf dem lync Server 2010 Server: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e38f7-157">Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e38f7-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="e38f7-158">Lync Server-Verwaltungsshell öffnen</span><span class="sxs-lookup"><span data-stu-id="e38f7-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e38f7-159">Fahren Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist.</span><span class="sxs-lookup"><span data-stu-id="e38f7-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="e38f7-160">Wenn Sie die Dateien vor der Fertigstellung der Replikation entfernen, unterbrechen Sie den Replikationsprozess und lassen den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand wieder.</span><span class="sxs-lookup"><span data-stu-id="e38f7-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="e38f7-161">Verwenden Sie das Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> , um den Replikationsstatus zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="e38f7-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="e38f7-162">Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers vom lync Server 2010 zentralen Verwaltungs Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="e38f7-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="e38f7-163">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e38f7-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="e38f7-164">Hierbei \<FQDN of SQL Server\> handelt es sich entweder um den lync Server 2010 Back-End-Server in einer Enterprise Edition-Bereitstellung oder den FQDN des Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="e38f7-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

