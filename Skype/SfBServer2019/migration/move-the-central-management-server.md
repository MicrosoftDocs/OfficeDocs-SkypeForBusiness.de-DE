---
title: Verschieben des zentralen Verwaltungsservers
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Skype für Business Server 2019, müssen Sie den zentralen Verwaltungsserver an der Skype für Business Server 2019 Front-End-Server oder Pool verschieben, bevor Sie dem-Legacyserver entfernen können.
ms.openlocfilehash: 805b5c506fdda11bdc24144a0622e674e8ef281b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030525"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a395a-103">Verschieben der Vorversion zentralen Verwaltungsserver in Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a395a-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="a395a-104">Nach der Migration zu Skype für Business Server 2019 und bevor Sie dem-Legacyserver entfernen können, müssen Sie den zentralen Verwaltungsserver in der Skype für Business Server 2019 Front-End-Server oder Pool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a395a-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="a395a-105">Den zentralen Verwaltungsserver ist ein einzelnes Master/mehreren Replikat System, auf dem wird die Lese-Schreib-Kopie der Datenbank vom Front-End-Server gespeichert, der den zentralen Verwaltungsserver enthält.</span><span class="sxs-lookup"><span data-stu-id="a395a-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="a395a-106">Auf jedem Computer in der Topologie, einschließlich der Front-End-Server, der den zentralen Verwaltungsserver enthält ist eine schreibgeschützte Kopie der zentralen Speicherdaten in SQL Server-Datenbank (namens RTCLOCAL standardmäßig) auf dem Computer während des Setups installiert und Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a395a-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="a395a-107">Die lokale Datenbank empfängt Replikat Updates über die Skype für Business Server Replikat Replikations-Agent, der als Dienst auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a395a-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="a395a-108">Der Name der aktuellen Datenbank auf den zentralen Verwaltungsserver und dem lokalen Replikat ist XDS, die der Dateien xds.mdf und xds.ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="a395a-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="a395a-109">Einen Dienststeuerungspunkt (SCP) in Active Directory Domain Services verweist auf der Speicherort der master-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a395a-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="a395a-110">Alle Tools, die verwenden den zentralen Verwaltungsserver Skype für Business Server konfigurieren und verwalten, mithilfe des zentralen Verwaltungsspeichers Suchen des Dienstverbindungspunkts.</span><span class="sxs-lookup"><span data-stu-id="a395a-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="a395a-111">Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken zentralen Verwaltungsserver vom ursprünglichen Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="a395a-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="a395a-112">Informationen zum Entfernen von der zentralen Verwaltungsserver-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a395a-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="a395a-113">Sie verwenden das Windows PowerShell-Cmdlet **Move-CsManagementServer** in der Skype für Business Server-Verwaltungsshell zum Verschieben der Datenbank aus der Vorversion installieren SQL Server-Datenbank die Skype für Business Server 2019 SQL Server-Datenbank, und aktualisieren Sie die SCP So zeigen Sie auf die Skype für Business Server 2019 zentraler Verwaltungsserver Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a395a-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="a395a-114">Verwenden Sie die Verfahren in diesem Abschnitt, um die Skype für Business Server 2019 Front-End-Server vorbereiten, bevor Sie den zentralen Verwaltungsserver verschieben.</span><span class="sxs-lookup"><span data-stu-id="a395a-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="a395a-115">So bereiten Sie einen Enterprise Edition-Front-End-Pool vor</span><span class="sxs-lookup"><span data-stu-id="a395a-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="a395a-116">Klicken Sie auf die Skype für Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungsserver verschieben möchten, melden Sie sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell installiert ist, als Mitglied der \*\*"RTCUniversalServerAdmins" \*\*Gruppe.</span><span class="sxs-lookup"><span data-stu-id="a395a-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a395a-117">Auch benötigen SQL Server-Datenbank Sysadmin Benutzerrechte und-Berechtigungen für die Datenbank Sie, wo Sie den zentralen Verwaltungsspeicher installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a395a-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="a395a-118">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="a395a-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a395a-119">Geben Sie Folgendes ein, um den neuen zentralen Verwaltungsspeicher in der Skype für Business Server 2019 SQL Server-Datenbank in der Skype für Business Server-Verwaltungsshell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a395a-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
  ```

4. <span data-ttu-id="a395a-120">Vergewissern Sie sich, dass der Status der **Skype für Business Server Front-End** -Dienst **gestartet**wird.</span><span class="sxs-lookup"><span data-stu-id="a395a-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="a395a-121">So bereiten Sie einen Standard Edition-Front-End-Server vor</span><span class="sxs-lookup"><span data-stu-id="a395a-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="a395a-122">Melden Sie auf der Skype für Business Server 2019 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver verschieben möchten sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell installiert ist, als Mitglied der \*\*"RTCUniversalServerAdmins" \*\*Gruppe.</span><span class="sxs-lookup"><span data-stu-id="a395a-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="a395a-123">Öffnen Sie die Skype für Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="a395a-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="a395a-124">Klicken Sie in der Skype für Business Server-Bereitstellungs-Assistenten **Vorbereiten des ersten Standard Edition-Servers**auf.</span><span class="sxs-lookup"><span data-stu-id="a395a-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="a395a-125">Auf der Seite **Befehle ausführen** ist SQL Server Express als den zentralen Verwaltungsserver installiert.</span><span class="sxs-lookup"><span data-stu-id="a395a-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="a395a-126">Erforderlichen Firewallregeln erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a395a-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="a395a-127">Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a395a-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a395a-128">Die ursprüngliche Installation kann einige Zeit ohne sichtbar Aktualisierung zum Befehl Ausgabe im Fenster Zusammenfassung dauern.</span><span class="sxs-lookup"><span data-stu-id="a395a-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="a395a-129">Dies ist aufgrund der Installation von SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a395a-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="a395a-130">Wenn Sie die Installation der Datenbank überwachen möchten, verwenden Sie zum Überwachen der Einrichtung Task-Manager.</span><span class="sxs-lookup"><span data-stu-id="a395a-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="a395a-131">Geben Sie Folgendes ein, um den neuen zentralen Verwaltungsspeicher auf die Skype für Business Server 2019 Standard Edition-Front-End-Server in der Skype für Business Server-Verwaltungsshell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a395a-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
  ```

6. <span data-ttu-id="a395a-132">Vergewissern Sie sich, dass der Status der **Skype für Business Server Front-End** -Dienst **gestartet**wird.</span><span class="sxs-lookup"><span data-stu-id="a395a-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a395a-133">So verschieben Sie die Vorversion installiert zentralen Verwaltungsserver in Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a395a-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="a395a-134">Melden Sie sich die Skype für Business Server 2019-Server, die den zentralen Verwaltungsserver werden, auf dem Computer, auf dem der Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe **RTCUniversalServerAdmins installiert ist** an.</span><span class="sxs-lookup"><span data-stu-id="a395a-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a395a-135">Sie müssen auch die SQL Server-Datenbank Benutzer Administratorrechte und-Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a395a-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a395a-136">Öffnen Sie Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="a395a-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a395a-137">Geben Sie in der Skype für Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a395a-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Enable-CsTopology
  ```

    > [!CAUTION]
    > <span data-ttu-id="a395a-138">Wenn `Enable-CsTopology` ist nicht erfolgreich, lösen Sie das Problem verhindert, dass des Befehls abschließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a395a-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="a395a-139">Wenn die **Enable-CsTopology** ist nicht erfolgreich, die Verschiebung schlägt fehl und Ihrer Topologie kann in einem Zustand belassen, in denen keine zentralen Verwaltungsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a395a-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="a395a-140">Geben Sie auf der Skype für Business Server 2019 Front-End-Server oder Front-End-Pool, in der Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="a395a-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Move-CsManagementServer
  ```

5. <span data-ttu-id="a395a-141">Skype für Business Server-Verwaltungsshell zeigt den Servern, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte aktueller Status und den Zustand vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="a395a-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="a395a-142">Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quell-als auch ist.</span><span class="sxs-lookup"><span data-stu-id="a395a-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="a395a-143">Geben Sie **Y** , um den Vorgang fortzusetzen oder **N** , um die Verschiebung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a395a-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="a395a-144">Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert, und beheben Sie diese.</span><span class="sxs-lookup"><span data-stu-id="a395a-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="a395a-145">Öffnen Sie auf der Skype für Business Server 2019 Server der Skype für Business Server-Bereitstellungs-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="a395a-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="a395a-146">In Skype für Business Server-Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, klicken Sie auf **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf Fertig stellen \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="a395a-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="a395a-147">Installieren Sie Server auf der Vorgängerversion, und öffnen Sie den Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="a395a-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="a395a-148">In Skype für Business Server-Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, klicken Sie auf **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf Fertig stellen \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="a395a-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="a395a-149">Starten Sie die Skype für Business Server 2019 Server neu.</span><span class="sxs-lookup"><span data-stu-id="a395a-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="a395a-150">Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft Zugriff auf zentraler Verwaltungsserver Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a395a-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="a395a-151">Geben Sie Folgendes ein, um zu bestätigen, dass die Replikation mit dem neuen zentralen Management Store in der Skype für Business Server-Verwaltungsshell ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a395a-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Get-CsManagementStoreReplicationStatus
  ```

    > [!NOTE]
    > <span data-ttu-id="a395a-152">Die Replikation dauert etwas Zeit, um alle aktuellen Replikate aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a395a-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="a395a-153">So entfernen Sie legacy installieren zentralen Speicherdateien nach dem Verschieben</span><span class="sxs-lookup"><span data-stu-id="a395a-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="a395a-154">Klicken Sie auf der Vorgängerversion installieren Sie Server, melden Sie sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell als Mitglied der Gruppe **RTCUniversalServerAdmins** installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a395a-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a395a-155">Sie müssen auch die SQL Server-Datenbank Benutzer Administratorrechte und-Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a395a-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a395a-156">Öffnen von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="a395a-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a395a-157">Fahren Sie mit dem Entfernen der vorherigen Datenbankdateien, bis die Replikation abgeschlossen ist und stabil ist.</span><span class="sxs-lookup"><span data-stu-id="a395a-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="a395a-158">Wenn Sie die Dateien vor dem Abschluss der Replikation entfernen, Sie Unterbrechen des Replikationsprozesses und lassen Sie den zentralen Verwaltungsserver neu verschobene in einem unbekannten Zustand.</span><span class="sxs-lookup"><span data-stu-id="a395a-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="a395a-159">Verwenden Sie das **Get-CsManagementStoreReplicationStatus** -Cmdlet, um den Replikationsstatus zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="a395a-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="a395a-160">Um die Datenbankdateien des zentralen Speicher aus der Vorversion Installation zentralen Verwaltungsserver zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a395a-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
  ```

    <span data-ttu-id="a395a-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a395a-161">For example:</span></span>
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
  ```

    <span data-ttu-id="a395a-162">In dem die _ \<FQDN von SQL Server\> _ ist entweder der Vorgängerversion Back-End-Server in einer Enterprise Edition-Bereitstellung oder der FQDN des Standard Edition-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="a395a-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

