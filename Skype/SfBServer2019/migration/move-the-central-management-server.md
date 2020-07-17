---
title: Migrieren des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie die Migration auf Skype for Business Server 2019 durchführen, müssen Sie den zentralen Verwaltungsserver in den Skype for Business Server 2019 Front-End-Server oder Pool verschieben, bevor Sie den Legacy Server entfernen können.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752467"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="9b8f0-103">Migrieren des Legacy-zentralen Verwaltungsservers zu Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9b8f0-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="9b8f0-104">Nachdem Sie die Migration auf Skype for Business Server 2019 durchführen und bevor Sie den Legacy Server entfernen können, müssen Sie den zentralen Verwaltungsserver in den Skype for Business Server 2019 Front-End-Server oder Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="9b8f0-105">Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Lese-/Schreibzugriff-Kopie der Datenbank von der Front-End-Server gespeichert wird, die den zentralen Verwaltungsserver enthält.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="9b8f0-106">Jeder Computer in der Topologie, einschließlich der Front-End-Server, die den zentralen Verwaltungs Server enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server Datenbank (standardmäßig RTCLOCAL), die während des Setups und der Bereitstellung auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="9b8f0-107">Die lokale Datenbank erhält Replikat Aktualisierungen über den Skype for Business Server Replikat Replikationsdienst-Agent, der auf allen Computern als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="9b8f0-108">Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="9b8f0-109">Auf den Speicherort der Master Datenbank wird in Active Directory-Domänendienste von einem Dienststeuerungspunkt (Service Control Points, SCP) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="9b8f0-110">Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und konfigurieren Skype for Business Server verwenden den SCP zum Auffinden des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="9b8f0-111">Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken des zentralen Verwaltungsservers aus dem ursprünglichen Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="9b8f0-112">Informationen zum Entfernen der Datenbanken des zentralen Verwaltungsservers finden Sie unter [Entfernen der SQL Server Datenbank für ein Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9b8f0-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="9b8f0-113">Verwenden Sie das Windows PowerShell **-Cmdlet CsManagementServer** in der Skype for Business Server Verwaltungsshell, um die Datenbank aus der Legacy Installations SQL Server Datenbank in die Skype for Business Server 2019 SQL Server Datenbank zu übertragen, und aktualisieren Sie dann den SCP so, dass er auf den Skype for Business Server 2019-Standort des zentralen Verwaltungsservers verweist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="9b8f0-114">Verwenden Sie die Verfahren in diesem Abschnitt, um die Skype for Business Server 2019-Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungs Server migrieren.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="9b8f0-115">So bereiten Sie eine Enterprise Edition-Front-End-Pool vor</span><span class="sxs-lookup"><span data-stu-id="9b8f0-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="9b8f0-116">Melden Sie sich im Skype for Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungs Server verschieben möchten, an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="9b8f0-117">Sie müssen auch SQL Server Datenbank-sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank haben, in der Sie den zentralen Verwaltungsspeicher installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="9b8f0-118">Öffnen Sie die Skype for Business Server Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="9b8f0-119">Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers in der Skype for Business Server 2019 SQL Server-Datenbank in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="9b8f0-120">Stellen Sie sicher, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="9b8f0-121">So bereiten Sie eine Standard Edition vor Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="9b8f0-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="9b8f0-122">Melden Sie sich auf der Skype for Business Server 2019 Standard Edition-Front-End-Server, in der Sie den zentralen Verwaltungs Server verschieben möchten, an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="9b8f0-123">Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="9b8f0-124">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="9b8f0-125">Auf der Seite **Befehle werden ausgeführt** wird SQL Server Express als zentraler Verwaltungs Server installiert.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="9b8f0-126">Die erforderlichen Firewallregeln werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="9b8f0-127">Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b8f0-128">Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="9b8f0-129">Dies ist auf die Installation von SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="9b8f0-130">Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="9b8f0-131">Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="9b8f0-132">Stellen Sie sicher, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="9b8f0-133">So migrieren Sie das Legacy installiert den zentralen Verwaltungs Server in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9b8f0-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="9b8f0-134">Melden Sie sich auf dem Skype for Business Server 2019-Server, der als zentraler Verwaltungsserver verwendet wird, an dem Computer an, auf dem die Skype for Business Server Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="9b8f0-135">Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="9b8f0-136">Öffnen Sie Skype for Business Server Management Shell (als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="9b8f0-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="9b8f0-137">Geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="9b8f0-138">Wenn `Enable-CsTopology` nicht erfolgreich ist, lösen Sie das Problem, dass der Befehl nicht abgeschlossen ist, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="9b8f0-139">Wenn **enable-CsTopology** nicht erfolgreich ist, tritt bei der Migration ein Fehler auf, und Ihre Topologie kann in einem Zustand bleiben, in dem kein zentraler Verwaltungsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="9b8f0-140">Geben Sie im Skype for Business Server 2019 Front-End-Server oder Front-End-Pool in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="9b8f0-141">In Skype for Business Server Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und Dienstverbindungspunkte des aktuellen Status und des Status vorgeschlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="9b8f0-142">Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quelle und das Ziel ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="9b8f0-143">Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Bewegung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="9b8f0-144">Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="9b8f0-145">Öffnen Sie auf dem Server mit Skype for Business Server 2019 den Skype for Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="9b8f0-146">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="9b8f0-147">Öffnen Sie auf dem Legacy Installationsserver den Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="9b8f0-148">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="9b8f0-149">Starten Sie den Skype for Business Server 2019-Server neu.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="9b8f0-150">Dies ist aufgrund einer Gruppen Mitgliedschaftsänderung für den Zugriff auf die Datenbank des zentralen Verwaltungsservers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="9b8f0-151">Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher ausgeführt wird, geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="9b8f0-152">Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="9b8f0-153">So entfernen Sie nach einer Migration ältere Installationsdateien für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="9b8f0-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="9b8f0-154">Melden Sie sich auf dem Legacy Installationsserver an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="9b8f0-155">Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="9b8f0-156">Öffnen Skype for Business Server Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9b8f0-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9b8f0-157">Fahren Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="9b8f0-158">Wenn Sie die Dateien vor der Fertigstellung der Replikation entfernen, unterbrechen Sie den Replikationsprozess und lassen den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand wieder.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="9b8f0-159">Verwenden Sie das Cmdlet **Get-CsManagementStoreReplicationStatus** , um den Replikationsstatus zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="9b8f0-160">Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers aus dem Legacy-Installations zentralen Verwaltungs Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="9b8f0-161">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="9b8f0-162">Dabei _\<FQDN of SQL Server\>_ handelt es sich um den Legacy-Installations-Back-End-Server in einer Enterprise Edition-Bereitstellung oder den FQDN des Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

