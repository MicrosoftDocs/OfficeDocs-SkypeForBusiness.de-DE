---
title: Verschieben des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder Pool von Skype for Business Server 2019 verschieben, bevor Sie den Legacy Server entfernen können.
ms.openlocfilehash: 0e13dab272a60967c0ccc676a47954b75170eeb3
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434941"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="2cd45-103">Verschieben des Legacy-zentralen Verwaltungsservers in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2cd45-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="2cd45-104">Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder Pool von Skype for Business Server 2019 verschieben, bevor Sie den Legacy Server entfernen können.</span><span class="sxs-lookup"><span data-stu-id="2cd45-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="2cd45-105">Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2cd45-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="2cd45-106">Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs.</span><span class="sxs-lookup"><span data-stu-id="2cd45-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="2cd45-107">Die lokale Datenbank erhält Replikat Updates über den Skype for Business Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2cd45-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="2cd45-108">Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="2cd45-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="2cd45-109">Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="2cd45-110">Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Skype for Business Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.</span><span class="sxs-lookup"><span data-stu-id="2cd45-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="2cd45-111">Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die zentralen Verwaltungsserver Datenbanken vom ursprünglichen Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="2cd45-112">Informationen zum Entfernen der zentralen Verwaltungs Server-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="2cd45-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="2cd45-113">Sie verwenden das Windows PowerShell **-Cmdlet Move-CsManagementServer** in der Skype for Business Server-Verwaltungsshell, um die Datenbank aus der Legacy-Installations-SQL Server-Datenbank in die Skype for Business Server 2019 SQL Server-Datenbank zu verschieben, und aktualisieren Sie dann die SCP, um auf den Standort des zentralen Verwaltungsservers von Skype for Business Server 2019 zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="2cd45-114">Führen Sie die Verfahren in diesem Abschnitt aus, um die Front-End-Server für Skype for Business Server 2019 vorzubereiten, bevor Sie den zentralen Verwaltungs Server verschieben.</span><span class="sxs-lookup"><span data-stu-id="2cd45-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="2cd45-115">Vorbereiten eines Enterprise Edition-Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="2cd45-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="2cd45-116">Melden Sie sich auf dem Skype for Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungs Server umsiedeln möchten, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied des RTCUniversalServerAdmins installiert ist. \*\* \*\*Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="2cd45-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="2cd45-117">Sie müssen auch über die SQL Server-Datenbank sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank verfügen, in der Sie den zentralen Verwaltungsspeicher installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2cd45-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="2cd45-118">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="2cd45-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="2cd45-119">Zum Erstellen des neuen zentralen Verwaltungsspeichers in der Skype for Business Server 2019 SQL Server-Datenbank geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2cd45-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="2cd45-120">Vergewissern Sie sich, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="2cd45-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="2cd45-121">Vorbereiten eines Standard Edition-Front-End-Servers</span><span class="sxs-lookup"><span data-stu-id="2cd45-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="2cd45-122">Melden Sie sich auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver umsiedeln möchten, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied des RTCUniversalServerAdmins installiert ist. \*\* \*\*Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="2cd45-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="2cd45-123">Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2cd45-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="2cd45-124">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="2cd45-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="2cd45-125">Auf der Seite **Ausführungsbefehle** wird SQL Server Express als zentraler Verwaltungs Server installiert.</span><span class="sxs-lookup"><span data-stu-id="2cd45-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="2cd45-126">Es werden erforderliche Firewallregeln erstellt.</span><span class="sxs-lookup"><span data-stu-id="2cd45-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="2cd45-127">Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2cd45-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2cd45-128">Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="2cd45-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="2cd45-129">Dies ist auf die Installation von SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="2cd45-130">Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="2cd45-131">Zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2cd45-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="2cd45-132">Vergewissern Sie sich, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.</span><span class="sxs-lookup"><span data-stu-id="2cd45-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="2cd45-133">So verschieben Sie die Legacy Installation des zentralen Verwaltungsservers in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2cd45-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="2cd45-134">Melden Sie sich auf dem Skype for Business Server 2019-Server, der der zentrale Verwaltungsserver sein soll, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2cd45-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="2cd45-135">Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="2cd45-136">Öffnen Sie die Skype for Business Server-Verwaltungsshell (als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="2cd45-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="2cd45-137">Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2cd45-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="2cd45-138">Wenn `Enable-CsTopology` dies nicht der Fall ist, beheben Sie das Problem, das verhindert, dass der Befehl abgeschlossen wird, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2cd45-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="2cd45-139">Wenn **enable-CsTopology** nicht erfolgreich ist, schlägt die Verschiebung fehl, und Sie verlässt Ihre Topologie möglicherweise in einem Zustand, in dem kein zentraler Verwaltungsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2cd45-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="2cd45-140">Geben Sie auf dem Skype for Business Server 2019-Front-End-Server oder-Front-End-Pool in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2cd45-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="2cd45-141">In der Skype for Business Server-Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte des aktuellen Zustands sowie der vorgeschlagene Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2cd45-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="2cd45-142">Lesen Sie die Informationen sorgfältig durch, und bestätigen Sie, dass dies die beabsichtigte Quelle und das Ziel ist.</span><span class="sxs-lookup"><span data-stu-id="2cd45-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="2cd45-143">Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Verschiebung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2cd45-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="2cd45-144">Überprüfen Sie alle Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="2cd45-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="2cd45-145">Öffnen Sie auf dem Skype for Business Server 2019-Server den Bereitstellungs-Assistenten für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2cd45-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="2cd45-146">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf \*\*Fertig stellen. \*\*.</span><span class="sxs-lookup"><span data-stu-id="2cd45-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="2cd45-147">Öffnen Sie auf dem Legacy Installationsserver den Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2cd45-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="2cd45-148">Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf \*\*Fertig stellen. \*\*.</span><span class="sxs-lookup"><span data-stu-id="2cd45-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="2cd45-149">Starten Sie den Skype for Business Server 2019-Server neu.</span><span class="sxs-lookup"><span data-stu-id="2cd45-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="2cd45-150">Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft für den Zugriff auf die zentrale Verwaltungs Server-Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2cd45-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="2cd45-151">Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher erfolgt, geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2cd45-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="2cd45-152">Die Replikation kann einige Zeit dauern, bis alle aktuellen Replikate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2cd45-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="2cd45-153">So entfernen Sie Legacy-Installationen von Central Management Store-Dateien nach einem Umzug</span><span class="sxs-lookup"><span data-stu-id="2cd45-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="2cd45-154">Melden Sie sich auf dem Legacy Installationsserver bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2cd45-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="2cd45-155">Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="2cd45-156">Öffnen der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="2cd45-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2cd45-157">Gehen Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist.</span><span class="sxs-lookup"><span data-stu-id="2cd45-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="2cd45-158">Wenn Sie die Dateien vor dem Abschließen der Replikation entfernen, werden Sie den Replikationsprozess unterbrechen und den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand belässt.</span><span class="sxs-lookup"><span data-stu-id="2cd45-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="2cd45-159">Verwenden Sie das Cmdlet **Get-CsManagementStoreReplicationStatus** , um den Replikationsstatus zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="2cd45-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="2cd45-160">Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers aus dem Legacy install Central-Verwaltungs Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="2cd45-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="2cd45-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2cd45-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="2cd45-162">Hierbei handelt es sich bei dem _ \<FQDN von SQL Server\> _ entweder um den Legacy-Installations-Back-End-Server in einer Enterprise Edition-Bereitstellung oder um den FQDN des Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="2cd45-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

