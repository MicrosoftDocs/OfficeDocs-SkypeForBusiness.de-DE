---
title: 'Lync Server 2013: Ausführen eines Failovers für einen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c269ed7e870fa7087465b64b9773d8f5d2df9e1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="76050-102">Ausführen eines Failovers für einen Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76050-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76050-103">_**Letztes Änderungsdatum des Themas:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="76050-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="76050-104">Wenn ein einzelner Front-End-Pool ausgefallen ist und ein Failover durchgeführt werden muss, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="76050-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="76050-105">In diesem Verfahren enthält Datacenter1 pool1, und pool1 ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="76050-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="76050-106">Sie haben einen Failover zu Pool2 befindet sich in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="76050-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="76050-107">Der größte Teil der Arbeit für das Pool-Failover umfasst einen Failover des zentralen Verwaltungsspeichers, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="76050-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="76050-108">Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn die Benutzer des Pools fehlerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="76050-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="76050-109">Wenn ein Front-End-Pool fehlschlägt, der Edge-Pool an dieser Website jedoch weiterhin ausgeführt wird, müssen Sie wissen, ob der Edge-Pool den fehlerhaften Pool als nächsten Hop-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="76050-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="76050-110">Wenn dies der Fall ist, müssen Sie den Edge-Pool so ändern, dass ein anderer Front-End-Pool verwendet wird, bevor der fehlerhafte Front-End-Pool fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="76050-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="76050-111">Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge-Pool am gleichen Standort wie der Edge-Pool oder auf einer anderen Website verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76050-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="76050-112">**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools auf derselben Website ein**</span><span class="sxs-lookup"><span data-stu-id="76050-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="76050-113">Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den zu ändernden Edge-Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="76050-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="76050-114">Klicken Sie auf **Nächster Hop**.</span><span class="sxs-lookup"><span data-stu-id="76050-114">Click **Next Hop**.</span></span> <span data-ttu-id="76050-115">Wählen Sie in der Liste **Nächster Hop-Pool:** den Pool aus, der nun als nächster Hop-Pool fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="76050-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="76050-116">Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="76050-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="76050-117">**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools an einer anderen Website ein**</span><span class="sxs-lookup"><span data-stu-id="76050-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="76050-118">Öffnen Sie ein lync Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="76050-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="76050-119">**So führen Sie einen Failover eines Pools in einem Notfall durch**</span><span class="sxs-lookup"><span data-stu-id="76050-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="76050-120">Ermitteln Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:</span><span class="sxs-lookup"><span data-stu-id="76050-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="76050-121">Die Ergebnisse dieses Cmdlets zeigen, in welchem Pool zurzeit der zentrale Verwaltungs Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="76050-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="76050-122">Im weiteren Verlauf dieses Verfahrens wird dieser Pool als "CMS\_-Pool" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="76050-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="76050-123">Verwenden Sie den Topologie-Generator, um die Version von lync Server zu\_finden, die im CMS-Pool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76050-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="76050-124">Wenn Sie lync Server 2013 ausführen, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.</span><span class="sxs-lookup"><span data-stu-id="76050-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="76050-125">Lassen Sie\_den Backup-Pool zum Backup-Pool werden.</span><span class="sxs-lookup"><span data-stu-id="76050-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="76050-126">Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="76050-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="76050-127">Dieses Cmdlet sollte anzeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS\_-Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="76050-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="76050-128">Wenn Sie leer sind, steht der zentrale Verwaltungs Server nicht zur Verfügung, und Sie müssen einen Failover durchführen.</span><span class="sxs-lookup"><span data-stu-id="76050-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="76050-129">Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher auf pool1 ausgeführt wurde (also der Pool, bei dem ein Fehler aufgetreten ist), müssen Sie vor dem Failover des Pools einen Failover für den zentralen Verwaltungs Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="76050-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="76050-130">Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit lync Server 2013 gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="76050-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="76050-131">Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit lync Server 2010 gehostet wurde, verwenden Sie das Cmdlet in Schritt 6 dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="76050-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="76050-132">Wenn Sie keinen Failover für den zentralen Verwaltungs Server benötigen, fahren Sie mit Schritt 7 dieses Verfahrens fort.</span><span class="sxs-lookup"><span data-stu-id="76050-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="76050-133">Gehen Sie wie folgt vor, um einen Failover des zentralen Verwaltungsspeichers in einem Pool mit lync Server 2013 auszuführen:</span><span class="sxs-lookup"><span data-stu-id="76050-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="76050-134">Überprüfen Sie zunächst, welcher Back-End\_-Server im Sicherungs Pool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="76050-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="76050-135">Wenn der primäre Back-End-Server\_im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76050-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="76050-136">Wenn der Spiegelungs-Back-End\_-Server im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76050-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="76050-137">Überprüfen Sie, ob der Failover des zentralen Verwaltungsservers abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="76050-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="76050-138">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76050-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="76050-139">Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="76050-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="76050-140">Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="76050-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="76050-141">Überprüfen Sie, ob alle Replikate den Wert true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="76050-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="76050-142">Fahren Sie mit Schritt 7 in diesem Verfahren fort.</span><span class="sxs-lookup"><span data-stu-id="76050-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="76050-143">Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-\_Server des Sicherungs Pools.</span><span class="sxs-lookup"><span data-stu-id="76050-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="76050-144">Führen Sie zunächst den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="76050-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="76050-145">Führen Sie den nächsten Befehl auf einem der Front-End-Server\_des Sicherungs Pools aus, um den Wechsel des zentralen Verwaltungsspeichers zu erzwingen:</span><span class="sxs-lookup"><span data-stu-id="76050-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="76050-146">Überprüfen Sie, ob die Verschiebung abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="76050-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="76050-147">Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="76050-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="76050-148">Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="76050-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="76050-149">Überprüfen Sie, ob alle Replikate den Wert true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="76050-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="76050-150">Installieren Sie den zentralen Verwaltungs Server Dienst auf den restlichen Front-End-Servern im\_Sicherungs Pool.</span><span class="sxs-lookup"><span data-stu-id="76050-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="76050-151">Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme derjenigen, die Sie beim Erzwingen des zentralen Verwaltungsspeichers weiter oben in diesem Verfahren verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="76050-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="76050-152">Führen Sie einen Failover der Benutzer von pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem Fenster der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="76050-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="76050-153">Da die Schritte, die in den vorherigen Abschnitten dieses Verfahrens zur Überprüfung des Status des zentralen Verwaltungsspeichers durchgeführt wurden, nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="76050-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="76050-154">In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="76050-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="76050-155">Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool auf dieser Website ändern, um einen anderen Pool als nächsten Hop zu verwenden, bevor Sie einen Failover für den Pool durchführen.</span><span class="sxs-lookup"><span data-stu-id="76050-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="76050-156">Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="76050-156">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

