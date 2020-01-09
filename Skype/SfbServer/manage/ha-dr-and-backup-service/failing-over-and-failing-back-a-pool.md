---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991800"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="3eae8-103">Fehler beim Failover und Zurücksetzen eines Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3eae8-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="3eae8-104">Führen Sie die folgenden Verfahren aus, wenn ein einzelner Front-End-Pool fehlerhaft ist und ein Failover durchgeführt werden muss, oder wenn der Pool, in dem der Notfall aufgetreten ist, wieder online ist und Sie Ihre Bereitstellung auf normalen Arbeitsstatus wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="3eae8-105">Sie erfahren außerdem, wie Sie den für Skype for Business Federation oder XMPP Federation verwendeten Edge-Pool für Failover und Failback zurücksetzen oder den Edge-Pool ändern, der einem Front-End-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="3eae8-106">Failover eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="3eae8-107">Zurücksetzen eines Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="3eae8-108">Failover des für den Skype for Business Server-Verbund verwendeten Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="3eae8-109">Failover des für die XMPP-Föderation verwendeten Edge-Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3eae8-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="3eae8-110">Zurücksetzen des Edge-Pools, der für Skype for Business Server Federation oder XMPP Federation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="3eae8-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="3eae8-111">Ändern des Edge-Pools, der einem Front-End-Pool zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="3eae8-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="3eae8-112">Failover eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-112">Fail over a Front End pool</span></span>

<span data-ttu-id="3eae8-113">In diesem Verfahren enthält Datacenter1 pool1, und pool1 ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="3eae8-114">Sie haben einen Failover zu Pool2 befindet sich in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="3eae8-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="3eae8-115">Der größte Teil der Arbeit für das Pool-Failover umfasst einen Failover des zentralen Verwaltungsspeichers, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="3eae8-116">Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn die Benutzer des Pools fehlerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="3eae8-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="3eae8-117">Wenn ein Front-End-Pool fehlschlägt, der Edge-Pool an dieser Website jedoch weiterhin ausgeführt wird, müssen Sie wissen, ob der Edge-Pool den fehlerhaften Pool als nächsten Hop-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="3eae8-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="3eae8-118">Wenn dies der Fall ist, müssen Sie den Edge-Pool so ändern, dass ein anderer Front-End-Pool verwendet wird, bevor der fehlerhafte Front-End-Pool fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="3eae8-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="3eae8-119">Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge-Pool am gleichen Standort wie der Edge-Pool oder auf einer anderen Website verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="3eae8-120">**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools auf derselben Website ein**</span><span class="sxs-lookup"><span data-stu-id="3eae8-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="3eae8-121">Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den zu ändernden Edge-Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="3eae8-122">Klicken Sie auf **Nächster Hop**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-122">Click **Next Hop**.</span></span> <span data-ttu-id="3eae8-123">Wählen Sie in der Liste **Nächster Hop-Pool:** den Pool aus, der nun als nächster Hop-Pool fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="3eae8-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="3eae8-124">Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="3eae8-125">**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools an einer anderen Website ein**</span><span class="sxs-lookup"><span data-stu-id="3eae8-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="3eae8-126">Öffnen Sie ein Skype for Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="3eae8-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="3eae8-127">**So führen Sie einen Failover eines Pools in einem Notfall durch**</span><span class="sxs-lookup"><span data-stu-id="3eae8-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="3eae8-128">Ermitteln Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="3eae8-129">Die Ergebnisse dieses Cmdlets zeigen, in welchem Pool zurzeit der zentrale Verwaltungs Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="3eae8-130">Im weiteren Verlauf dieses Verfahrens wird dieser Pool als "CMS\_-Pool" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3eae8-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="3eae8-131">Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu\_finden, die im CMS-Pool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="3eae8-132">Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.</span><span class="sxs-lookup"><span data-stu-id="3eae8-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="3eae8-133">Lassen Sie\_den Backup-Pool zum Backup-Pool werden.</span><span class="sxs-lookup"><span data-stu-id="3eae8-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="3eae8-134">Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3eae8-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="3eae8-135">Dieses Cmdlet sollte anzeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS\_-Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="3eae8-136">Wenn Sie leer sind, steht der zentrale Verwaltungs Server nicht zur Verfügung, und Sie müssen einen Failover durchführen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="3eae8-137">Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher auf pool1 ausgeführt wurde (also der Pool, bei dem ein Fehler aufgetreten ist), müssen Sie vor dem Failover des Pools einen Failover für den zentralen Verwaltungs Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="3eae8-138">Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit Skype for Business Server gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="3eae8-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="3eae8-139">Wenn Sie keinen Failover für den zentralen Verwaltungs Server benötigen, fahren Sie mit Schritt 7 dieses Verfahrens fort.</span><span class="sxs-lookup"><span data-stu-id="3eae8-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="3eae8-140">Gehen Sie wie folgt vor, um einen Failover des zentralen Verwaltungsspeichers in einem Pool mit Skype for Business Server auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3eae8-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="3eae8-141">Überprüfen Sie zunächst, welcher Back-End\_-Server im Sicherungs Pool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="3eae8-142">Wenn der primäre Back-End-Server\_im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3eae8-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="3eae8-143">Wenn der Spiegelungs-Back-End\_-Server im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3eae8-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="3eae8-144">Überprüfen Sie, ob der Failover des zentralen Verwaltungsservers abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="3eae8-145">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3eae8-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3eae8-146">Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3eae8-147">Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3eae8-148">Überprüfen Sie, ob alle Replikate den Wert true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="3eae8-149">Fahren Sie mit Schritt 7 in diesem Verfahren fort.</span><span class="sxs-lookup"><span data-stu-id="3eae8-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="3eae8-150">Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-\_Server des Sicherungs Pools.</span><span class="sxs-lookup"><span data-stu-id="3eae8-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3eae8-151">Führen Sie zunächst den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="3eae8-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="3eae8-152">Führen Sie den nächsten Befehl auf einem der Front-End-Server\_des Sicherungs Pools aus, um den Wechsel des zentralen Verwaltungsspeichers zu erzwingen:</span><span class="sxs-lookup"><span data-stu-id="3eae8-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="3eae8-153">Überprüfen Sie, ob die Verschiebung abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="3eae8-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3eae8-154">Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3eae8-155">Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3eae8-156">Überprüfen Sie, ob alle Replikate den Wert true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="3eae8-157">Installieren Sie den zentralen Verwaltungs Server Dienst auf den restlichen Front-End-Servern im\_Sicherungs Pool.</span><span class="sxs-lookup"><span data-stu-id="3eae8-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="3eae8-158">Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme derjenigen, die Sie beim Erzwingen des zentralen Verwaltungsspeichers weiter oben in diesem Verfahren verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="3eae8-159">Führen Sie einen Failover der Benutzer von pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem Skype for Business Server-Verwaltungsshell-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="3eae8-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="3eae8-160">Da die Schritte, die in den vorherigen Abschnitten dieses Verfahrens zur Überprüfung des Status des zentralen Verwaltungsspeichers durchgeführt wurden, nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="3eae8-161">In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="3eae8-162">Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool auf dieser Website ändern, um einen anderen Pool als nächsten Hop zu verwenden, bevor Sie einen Failover für den Pool durchführen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="3eae8-163">Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="3eae8-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="3eae8-164">Zurücksetzen eines Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-164">Fail back a pool</span></span>

<span data-ttu-id="3eae8-165">Nachdem der Pool, der das Desaster erlebt hat, wieder online ist (also pool1 in diesem Beispiel), führen Sie die folgenden Schritte aus, um die Bereitstellung auf normalen Arbeitsstatus wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="3eae8-166">Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="3eae8-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="3eae8-167">Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="3eae8-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="3eae8-168">Führen Sie einen Failback für die Benutzer durch, die sich ursprünglich in pool1 begeben haben, und Sie haben ein Failover auf Pool2 durchgeführt, indem Sie das folgende Cmdlet eingegeben haben:</span><span class="sxs-lookup"><span data-stu-id="3eae8-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="3eae8-169">Es sind keine weiteren Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3eae8-169">No other steps are necessary.</span></span> <span data-ttu-id="3eae8-170">Wenn Sie einen Fehler über den zentralen Verwaltungs Server ausgeführt haben, können Sie ihn in Pool2 belassen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="3eae8-171">Failover des für den Skype for Business Server-Verbund verwendeten Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="3eae8-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="3eae8-172">Wenn der Edge-Pool, in dem Sie die Skype for Business Server-Föderation konfiguriert haben, ausfällt, müssen Sie die Föderation so ändern, dass ein anderer Edge-Pool für den Verbund verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="3eae8-173">Öffnen Sie auf einem Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="3eae8-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="3eae8-174">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edge-Server oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="3eae8-175">Wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="3eae8-176">Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3eae8-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-177">Click **OK**.</span></span>

3.  <span data-ttu-id="3eae8-178">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edge-Server oder den Edgeserver-Pool, den Sie jetzt für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3eae8-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="3eae8-179">Wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="3eae8-180">Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3eae8-181">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-181">Click **OK**.</span></span>

5.  <span data-ttu-id="3eae8-182">Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="3eae8-183">Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="3eae8-184">Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="3eae8-185">Öffnen Sie auf dem Edgeserver den Assistenten für die Bereitstellung von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3eae8-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="3eae8-186">Klicken Sie auf **Skype for Business Server-System installieren oder aktualisieren**, und klicken Sie dann auf **Setup oder Entfernen von Skype for Business Server-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="3eae8-187">Klicken Sie **erneut auf Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="3eae8-188">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-188">Click **Next**.</span></span> <span data-ttu-id="3eae8-189">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3eae8-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3eae8-190">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="3eae8-191">Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="3eae8-192">Wenn die Website mit dem fehlerhaften Edge-Pool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um einen Edge-Pool in einer noch ausgeführten Remotewebsite zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3eae8-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="3eae8-193">Failover des für die XMPP-Föderation verwendeten Edge-Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3eae8-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="3eae8-194">In Ihrer Organisation gibt es einen Edge-Pool, der als Pool für XMPP-Föderationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="3eae8-195">Wenn dieser Pool ausfällt, müssen Sie die XMPP-Föderation nicht verwenden, um einen anderen Edge-Pool zu verwenden, bevor die XMPP-Föderation wieder funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="3eae8-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="3eae8-196">Wenn Sie Edge-Pools zum ersten Mal installieren und die XMPP-Föderation aktivieren, können Sie den Disaster Recovery-Prozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP Federation einrichten, und nicht nur eine.</span><span class="sxs-lookup"><span data-stu-id="3eae8-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="3eae8-197">Jeder dieser SRV-Einträge muss einen anderen Prioritäts Satz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="3eae8-198">Der gesamte XMPP-Verbunddatenverkehr durchläuft den Pool mit dem SRV-Eintrag mit der höchsten Priorität.</span><span class="sxs-lookup"><span data-stu-id="3eae8-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="3eae8-199">In der folgenden Vorgehensweise ist EdgePool1 der Pool, in dem die XMPP-Föderation ursprünglich gehostet wurde, und EdgePool2 ist der Pool, der nun XMPP-Föderation hostet.</span><span class="sxs-lookup"><span data-stu-id="3eae8-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="3eae8-200">So führen Sie einen Failover des für die XMPP-Föderation verwendeten Edge-Pools aus</span><span class="sxs-lookup"><span data-stu-id="3eae8-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="3eae8-201">Wenn Sie noch keinen anderen Edge-Pool bereitgestellt haben (außer dem, der zurzeit nicht vorhanden ist), stellen Sie diesen Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="3eae8-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="3eae8-202">Führen Sie auf jedem Edgeserver des neuen Edge-Pools, in dem nun XMPP Federation (EdgePool2) gehostet wird, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="3eae8-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="3eae8-203">Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route auf EdgePool2 zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="3eae8-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="3eae8-204">In diesem Beispiel ist site2 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeserver in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="3eae8-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="3eae8-205">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="3eae8-206">Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="3eae8-207">Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="3eae8-208">Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="3eae8-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="3eae8-209">Starten Sie die Dienste auf allen Edgeserver im Edge-Pool, die nun die XMPP-Föderation hosten:</span><span class="sxs-lookup"><span data-stu-id="3eae8-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="3eae8-210">Zurücksetzen des Edge-Pools, der für Skype for Business Server Federation oder XMPP Federation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="3eae8-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="3eae8-211">Nachdem ein ausgefallener Edge-Pool, der zum Hosten der Föderation verwendet wurde, wieder online geschaltet wurde, verwenden Sie dieses Verfahren zum Zurücksetzen der Skype for Business Server-Föderations Route und/oder der XMPP-Föderations Route, um diesen wiederhergestellten Edge-Pool erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3eae8-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="3eae8-212">Starten Sie in dem jetzt wieder verfügbaren Edge-Pool die Edge-Dienste.</span><span class="sxs-lookup"><span data-stu-id="3eae8-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="3eae8-213">Wenn Sie die Skype for Business Server-Föderations Route für die Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="3eae8-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3eae8-214">Öffnen Sie auf einem Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="3eae8-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="3eae8-215">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3eae8-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="3eae8-216">Wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3eae8-217">Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3eae8-218">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="3eae8-219">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edge-Server oder den Edgeserver-Pool, den Sie erneut für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3eae8-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="3eae8-220">Wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3eae8-221">Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3eae8-222">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="3eae8-223">Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="3eae8-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="3eae8-224">Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="3eae8-225">Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="3eae8-226">Öffnen Sie auf dem Edgeserver den Assistenten für die Bereitstellung von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3eae8-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="3eae8-227">Klicken Sie auf **Skype for Business Server-System installieren oder aktualisieren**, und klicken Sie dann auf **Setup oder Entfernen von Skype for Business Server-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="3eae8-228">Klicken Sie **erneut auf Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="3eae8-229">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-229">Click **Next**.</span></span> <span data-ttu-id="3eae8-230">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3eae8-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3eae8-231">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="3eae8-232">Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="3eae8-233">Gehen Sie wie folgt vor, wenn Sie die XMPP-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:</span><span class="sxs-lookup"><span data-stu-id="3eae8-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3eae8-234">Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route an den Edge-Pool zu verweisen, der nun XMPP-Föderation hostet (in diesem Beispiel EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="3eae8-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="3eae8-235">In diesem Beispiel ist site1 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeserver in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="3eae8-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="3eae8-236">Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="3eae8-237">Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="3eae8-238">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="3eae8-239">Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="3eae8-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="3eae8-240">Wenn die Front-End-Pools weiterhin auf der Website mit dem fehlerhaften Edge-Pool ausgeführt wurden und wiederhergestellt wurden, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um die Edge-Pools auf der lokalen Website erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3eae8-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="3eae8-241">Wenn der Front-End-Pool am gleichen Standort wie der fehlerhafte Edge-Pool ebenfalls fehlgeschlagen ist, können Sie jetzt Invoke – CsPoolFailback verwenden, um den Front-End-Pool zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="3eae8-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="3eae8-242">Ändern des Edge-Pools, der einem Front-End-Pool zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="3eae8-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="3eae8-243">Wenn ein Edge-Pool ausfällt, der Front-End-Pool am gleichen Standort aber noch ausgeführt wird, müssen Sie den Front-End-Pool so einrichten, dass ein Edge-Pool an einer anderen Website verwendet wird, bis der fehlerhafte Edge-Pool wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3eae8-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="3eae8-244">Navigieren Sie im Topologie-Generator zu dem Namen des Front-End-Pools, den Sie ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="3eae8-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="3eae8-245">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="3eae8-246">Verwenden Sie im Abschnitt **Zuordnungen** unter **Edge-Pool zuordnen (für Medienkomponenten)** das Dropdownfeld, um den Edge-Pool auszuwählen, dem Sie diesen Front-End-Pool zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="3eae8-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="3eae8-247">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eae8-247">Click **OK**.</span></span>
