---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197800"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="62176-103">Stets über, ansonsten einen Pool in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="62176-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="62176-104">Gehen Sie folgendermaßen vor, wenn ein einzelner Front-End-Pool ist fehlgeschlagen und muss ein Failover oder den Pool, der ausgefallenen wieder online ist und Sie für reguläre Arbeitsstatus Ihrer Bereitstellung wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="62176-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="62176-105">Auch hier erfahren Sie, wie Sie ein Failover und Failback für den Edge-Pool für Skype für Business verbunden oder XMPP-Verbund verwendet, oder ändern Sie den Edge-Pool einen Front-End-Pool zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="62176-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="62176-106">Ausführen eines Failovers eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="62176-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="62176-107">Führen einen Sie Failback eines Pools</span><span class="sxs-lookup"><span data-stu-id="62176-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="62176-108">Ein Failover des edgepools für Skype für den Verbund Business Server</span><span class="sxs-lookup"><span data-stu-id="62176-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="62176-109">Ein Failover des edgepools für XMPP-Verbund in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="62176-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="62176-110">Failover des edgepools für Skype für Business Server- oder XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="62176-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="62176-111">Ändern des Edge-Pools einen Front-End-Pool zugeordnet</span><span class="sxs-lookup"><span data-stu-id="62176-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="62176-112">Ausführen eines Failovers eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="62176-112">Fail over a Front End pool</span></span>

<span data-ttu-id="62176-113">In diesem Verfahren Datacenter1 enthält Pool1 und Pool1 ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="62176-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="62176-114">Sie sind auf Pool2 befindet sich im Datacenter2 Failovervorgängen.</span><span class="sxs-lookup"><span data-stu-id="62176-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="62176-115">Die meisten Aufgaben für den poolfailover umfasst Failover des zentralen Verwaltungsspeichers, wenn es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="62176-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="62176-116">Dies ist wichtig, da des zentralen Verwaltungsspeichers funktionsfähig sein muss, wenn die Benutzer des Pools ein Failover ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62176-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="62176-117">Darüber hinaus muss bei ein Front-End-Pool Fehler auftreten, aber der Edge-Pool an diesem Standort weiterhin ausgeführt wird, wissen, ob der Edge-Pool den ausgefallenen Pool als nächsten hoppool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62176-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="62176-118">Wenn dies der Fall ist, müssen Sie einen anderen Front-End-Pool vor dem über den fehlerhaften Front-End-Pool verwenden, um den Edge-Pool ändern.</span><span class="sxs-lookup"><span data-stu-id="62176-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="62176-119">Ändern Sie die Einstellung der nächste Hop, hängt davon ab, ob der Rand einen Pool am selben Standort befinden wie der Edge-Pool oder einem anderen Standort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62176-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="62176-120">**Festlegen ein Edge-Pools einen nächsten hoppool am selben Standort verwenden**</span><span class="sxs-lookup"><span data-stu-id="62176-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="62176-121">Öffnen Sie den Topologie-Generator rechten Maustaste auf den Edge-Pool, der geändert werden soll, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="62176-122">Klicken Sie auf **Nächster Hop**.</span><span class="sxs-lookup"><span data-stu-id="62176-122">Click **Next Hop**.</span></span> <span data-ttu-id="62176-123">Aus der **Nächster hoppool:** , wählen Sie den Pool der jetzt als den nächsten hoppool dienen soll.</span><span class="sxs-lookup"><span data-stu-id="62176-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="62176-124">Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="62176-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="62176-125">**Festlegen ein Edge-Pools einen nächsten hoppool an einem anderen Standort verwenden**</span><span class="sxs-lookup"><span data-stu-id="62176-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="62176-126">Öffnen Sie einen Skype für Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="62176-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="62176-127">**Failover eines Pools im Notfall**</span><span class="sxs-lookup"><span data-stu-id="62176-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="62176-128">Suchen Sie nach dem Pool den Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:</span><span class="sxs-lookup"><span data-stu-id="62176-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="62176-129">Die Ergebnisse der dieses Cmdlet anzeigen, welcher Pool den zentralen Verwaltungsserver derzeit gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="62176-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="62176-130">Die restlichen Schritte dieses Verfahrens in diesem Pool wird CMS genannt\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="62176-131">Topologie-Generator verwenden, um die Version von Skype für Business Server, auf dem zentralen Verwaltungsspeicher finden\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="62176-132">Wenn es Skype für Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool Pool 1 suchen.</span><span class="sxs-lookup"><span data-stu-id="62176-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="62176-133">Lassen Sie Sicherung\_Pool den Sicherungspool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62176-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="62176-134">Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="62176-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="62176-135">Dieses Cmdlet sollte angezeigt werden, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" mit dem FQDN des CMS zeigen\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="62176-136">Wenn sie leer sind, den zentralen Verwaltungsserver ist nicht verfügbar, und Sie müssen Sie als ein Failover.</span><span class="sxs-lookup"><span data-stu-id="62176-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="62176-137">Wenn Sie der zentralen Verwaltungsspeicher nicht verfügbar ist oder des zentralen Verwaltungsspeichers auf Pool1 ausgeführt wurde (d. h., den Pool, der ein Fehler aufgetreten ist), müssen Sie den zentralen Verwaltungsserver vor dem Failover, über den Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="62176-138">Wenn Sie den zentralen Verwaltungsserver Failover, die in einem Pool mit Skype für Business Server gehostet wurde müssen, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="62176-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="62176-139">Wenn Sie nicht den zentralen Verwaltungsserver Failover müssen, fahren Sie mit Schritt 7 fortfahren.</span><span class="sxs-lookup"><span data-stu-id="62176-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="62176-140">Gehen Sie wie folgt vor, um das Failover des zentralen Verwaltungsspeichers in einem Pool mit Skype für Business Server:</span><span class="sxs-lookup"><span data-stu-id="62176-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="62176-141">Überprüfen Sie zunächst, welche Back End-Server in Sicherung\_Pool führt die Prinzipalinstanz des zentralen Verwaltungsspeichers, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="62176-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="62176-142">Wenn der primäre Back End-Server in Sicherung\_Pool ist der Prinzipal, Typ:</span><span class="sxs-lookup"><span data-stu-id="62176-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="62176-143">Wenn der Spiegel-Back-End-Server in Sicherung\_Pool ist der Prinzipal, Typ:</span><span class="sxs-lookup"><span data-stu-id="62176-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="62176-144">Überprüfen Sie, dass das Failover des zentralen Verwaltungsservers abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="62176-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="62176-145">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="62176-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="62176-146">Überprüfen Sie, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" auf die FQDN Sicherung zeigen\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="62176-147">Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="62176-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="62176-148">Überprüfen Sie, dass alle Replikate den Wert True haben.</span><span class="sxs-lookup"><span data-stu-id="62176-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="62176-149">Fahren Sie mit Schritt 7 in diesem Verfahren fort.</span><span class="sxs-lookup"><span data-stu-id="62176-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="62176-150">Installieren Sie den zentralen Verwaltungsspeicher auf der Back-End Server des\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="62176-151">Führen Sie zuerst den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="62176-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="62176-152">Führen den nächsten Befehl auf einem der Front-End-Server der Sicherung\_Pool verschieben des zentralen Verwaltungsspeichers erzwingen:</span><span class="sxs-lookup"><span data-stu-id="62176-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="62176-153">Überprüfen Sie die Verschiebung abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="62176-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="62176-154">Überprüfen Sie, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" auf die FQDN Sicherung zeigen\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="62176-155">Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="62176-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="62176-156">Überprüfen Sie, dass alle Replikate den Wert True haben.</span><span class="sxs-lookup"><span data-stu-id="62176-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="62176-157">Installieren Sie den zentralen Verwaltungsserver-Dienst auf den Rest der Front-End-Server in Sicherung\_Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="62176-158">Zu diesem Zweck führen Sie den folgenden Befehl auf allen Front-End-Servern, mit Ausnahme des, mit dem Erzwingen der zentralen Speicher weiter oben in diesem Verfahren verschieben:</span><span class="sxs-lookup"><span data-stu-id="62176-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="62176-159">Ausführen eines Failovers der Benutzer von Pool1 zu Pool2, indem Sie das folgende Cmdlet in einen Skype für Business Server-Verwaltungsshell-Fenster ausführen:</span><span class="sxs-lookup"><span data-stu-id="62176-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="62176-160">Da die Schritte in den vorherigen Teilen dieses Verfahrens zum Überprüfen des Status des zentralen Speicher nicht universelle sind, ist weiterhin eine Möglichkeit, die dieses Cmdlet schlägt fehl, da es sich bei der zentralen Verwaltungsspeicher nicht noch vollständig Failover ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="62176-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="62176-161">In diesem Fall müssen Sie beheben des zentralen Verwaltungsspeichers basierend auf Fehlermeldungen, die Sie sehen, und führen Sie dieses Cmdlet erneut aus.</span><span class="sxs-lookup"><span data-stu-id="62176-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="62176-162">Wenn Sie die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool an diesem Standort für die Verwendung von eines anderen Pools als nächsten Hop vor dem über den Pool zu ändern.</span><span class="sxs-lookup"><span data-stu-id="62176-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="62176-163">Weitere Informationen hierzu finden Sie die Verfahren am Anfang dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="62176-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="62176-164">Führen einen Sie Failback eines Pools</span><span class="sxs-lookup"><span data-stu-id="62176-164">Fail back a pool</span></span>

<span data-ttu-id="62176-165">Nachdem der Pool, der ausgefallenen wieder online ist (d. h., in diesem Beispiel Pool1), gehen Sie folgendermaßen vor Ihrer Bereitstellung in reguläre Arbeitsstatus wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="62176-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="62176-166">Beachten Sie, dass der Failback-Prozess einige Zeit in.</span><span class="sxs-lookup"><span data-stu-id="62176-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="62176-167">Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="62176-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="62176-168">Failback der Benutzer, die wurden die ursprünglich in Pool1 verwaltet und wurde Failover durchgeführt wurde Pool2 durch das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="62176-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="62176-169">Es sind keine weiteren Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62176-169">No other steps are necessary.</span></span> <span data-ttu-id="62176-170">Wenn Sie über den zentralen Verwaltungsserver ausgefallen ist, können Sie es in Pool2 lassen.</span><span class="sxs-lookup"><span data-stu-id="62176-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="62176-171">Ein Failover des edgepools für Skype für den Verbund Business Server</span><span class="sxs-lookup"><span data-stu-id="62176-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="62176-172">Wenn der Edge-Pool, in dem Sie Skype für Business Server den Verbund konfiguriert haben, ausfällt, müssen Sie den Verbund verwenden einen anderen edgepool für den Verbund für die Arbeit ändern.</span><span class="sxs-lookup"><span data-stu-id="62176-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="62176-173">Öffnen Sie auf einem Front-End-Server-Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="62176-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="62176-174">Erweitern Sie **edgepools**, und klicken Sie dann die mit der rechten Maustaste die Edge-Server oder Edge-Server-Pool, der aktuell für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="62176-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="62176-175">Wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="62176-176">**Bearbeiten von Eigenschaften** unter **Allgemein**deaktivieren Sie **aktivieren den Verbund für diesen edgepool (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="62176-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="62176-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62176-177">Click **OK**.</span></span>

3.  <span data-ttu-id="62176-178">Erweitern Sie **edgepools**, und klicken Sie dann die mit der rechten Maustaste die Edge-Server oder Pool für Edge-Server, die Sie nun für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="62176-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="62176-179">Wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="62176-180">**Eigenschaften bearbeiten** unter **Allgemein**die Option **Partnerverbund für diesen edgepool (Port 5061) aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="62176-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="62176-181">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62176-181">Click **OK**.</span></span>

5.  <span data-ttu-id="62176-182">Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, wählen Sie **Veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="62176-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="62176-183">**Veröffentlichen der Topologie**auf dazu aufgefordert werden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="62176-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="62176-184">Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="62176-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="62176-185">Öffnen Sie auf dem Edgeserver der Skype für Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="62176-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="62176-186">Klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, und klicken Sie dann auf **einrichten oder Entfernen von Skype für Business Server-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="62176-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="62176-187">Klicken Sie auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="62176-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="62176-188">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="62176-188">Click **Next**.</span></span> <span data-ttu-id="62176-189">Im Fenster Zusammenfassung anzeigen die Aktionen, wie diese ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62176-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="62176-190">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62176-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="62176-191">Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="62176-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="62176-192">Wenn die Website mit der ausgefallene edgepool Front-End-Server, der noch ausgeführt werden enthält, müssen Sie aktualisieren die Webkonferenzdienst und A / V-Konferenzdienst auf diesen Front-End-Pools verwenden ein Edge-Pools in einer site also weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="62176-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="62176-193">Ein Failover des edgepools für XMPP-Verbund in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="62176-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="62176-194">In Ihrer Organisation müssen Sie ein Edge-Pool als den Pool für XMPP-Verbund zu verwendenden vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62176-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="62176-195">Wenn dieser Pool ausfällt, müssen Sie ein Failover XMPP-Verbund auf einen anderen edgepool verwenden, bevor XMPP-Verbund erneut arbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="62176-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="62176-196">Wenn Sie zuerst installieren von Edge-Pools und XMPP-Partnerverbund aktivieren, können Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP-Verbund, statt nur einem Einrichten der Wiederherstellung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="62176-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="62176-197">Jedem dieser SRV-Datensätze muss eine andere Priorität festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="62176-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="62176-198">Alle XMPP-Verbund-Datenverkehr wird über den Pool mit der SRV-Eintrag mit der höchsten Priorität.</span><span class="sxs-lookup"><span data-stu-id="62176-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="62176-199">In der folgenden Prozedur EdgePool1 den Pool der XMPP-Verbund ursprünglich gehostet wird, und EdgePool2 ist der Pool, der XMPP-Verbund jetzt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="62176-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="62176-200">Failover des edgepools für XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="62176-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="62176-201">Wenn Sie noch nicht bereitgestellt (außer derjenigen, die derzeit ausgefallen ist), einen anderen edgepool diesen Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="62176-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="62176-202">Führen Sie auf jedem Edgeserver im neuen edgepool, der nun der XMPP-Verbund (EdgePool2) gehostet wird das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="62176-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="62176-203">Führen Sie die XMPP-partnerverbundroute auf EdgePool2 zu verweisen, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="62176-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="62176-204">In diesem Beispiel Site2 ist die Website mit der Edge-Pool, der nun die XMPP-partnerverbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="62176-205">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Verbund auf EdgeServer2.contoso.com verweist.</span><span class="sxs-lookup"><span data-stu-id="62176-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="62176-206">Wenn Sie bereits einen DNS-SRV-Eintrag für XMPP-Verbund keinen der in der Edge-Pool dem XMPP-Verbund jetzt gehostet wird, aufgelöst wird, müssen Sie, wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62176-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="62176-207">Dieser SRV-Eintrag muss einen Portwert 5269 haben.</span><span class="sxs-lookup"><span data-stu-id="62176-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="62176-208">Stellen Sie sicher, dass der Edge-Pool, der XMPP-Verbund jetzt gehostet wird Port 5269 open extern ist.</span><span class="sxs-lookup"><span data-stu-id="62176-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="62176-209">Starten Sie die Dienste auf allen Edge-Servern in der Edge-Pool, der XMPP-Verbund jetzt gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="62176-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="62176-210">Failover des edgepools für Skype für Business Server- oder XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="62176-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="62176-211">Nach einer fehlerhaften Kante Pool, mit dem Host Verbund gebracht worden wieder online, die mit diesem Verfahren können Sie ein Failback der Skype für partnerverbundroute Business Server und/oder die XMPP-partnerverbundroute, um diesen wiederhergestellten edgepool erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="62176-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="62176-212">Starten Sie auf den Edge-Pool, der nun wieder verfügbar ist, die Edgedienste.</span><span class="sxs-lookup"><span data-stu-id="62176-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="62176-213">Wenn Sie ein Failback der Skype für partnerverbundroute Business Server um den wiederhergestellten Edgeserver zu verwenden möchten, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="62176-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="62176-214">Öffnen Sie auf einem Front-End-Server-Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="62176-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="62176-215">Erweitern Sie die **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder Edge-Server-Pool, der aktuell für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="62176-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="62176-216">Wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="62176-217">**Bearbeiten von Eigenschaften** unter **Allgemein**deaktivieren Sie **aktivieren den Verbund für diesen edgepool (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="62176-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="62176-218">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62176-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="62176-219">Erweitern Sie die **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den ursprünglichen Edgeserver oder edgeserverpool, den Sie erneut für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="62176-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="62176-220">Wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="62176-221">**Eigenschaften bearbeiten** unter **Allgemein**die Option **Partnerverbund für diesen edgepool (Port 5061) aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="62176-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="62176-222">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62176-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="62176-223">Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, wählen Sie **Veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="62176-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="62176-224">**Veröffentlichen der Topologie**auf dazu aufgefordert werden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="62176-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="62176-225">Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="62176-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="62176-226">Öffnen Sie auf dem Edgeserver der Skype für Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="62176-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="62176-227">Klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**und dann auf **einrichten oder Entfernen von Skype für Business Server-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="62176-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="62176-228">Klicken Sie auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="62176-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="62176-229">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="62176-229">Click **Next**.</span></span> <span data-ttu-id="62176-230">Im Fenster Zusammenfassung anzeigen die Aktionen, wie diese ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62176-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="62176-231">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62176-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="62176-232">Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="62176-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="62176-233">Wenn Sie das Failback für der XMPP-partnerverbundroute, um den wiederhergestellten Edgeserver zu verwenden möchten, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="62176-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="62176-234">Führen Sie das folgende Cmdlet aus, um die XMPP-partnerverbundroute an den Edge-Pool verweisen, von dem nun der XMPP-Verbund (in diesem Beispiel EdgeServer1) gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="62176-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="62176-235">In diesem Beispiel Site1 ist die Website mit der Edge-Pool, der nun die XMPP-partnerverbundroute gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeservers in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="62176-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="62176-236">Wenn Sie bereits einen DNS-SRV-Eintrag für XMPP-Verbund keinen der in der Edge-Pool dem XMPP-Verbund jetzt gehostet wird, aufgelöst wird, müssen Sie, wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62176-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="62176-237">Dieser SRV-Eintrag muss einen Portwert 5269 haben.</span><span class="sxs-lookup"><span data-stu-id="62176-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="62176-238">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Verbund auf EdgeServer2.contoso.com verweist.</span><span class="sxs-lookup"><span data-stu-id="62176-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="62176-239">Stellen Sie sicher, dass der Edge-Pool, der XMPP-Verbund jetzt gehostet wird Port 5269 open extern ist.</span><span class="sxs-lookup"><span data-stu-id="62176-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="62176-240">Wenn der Front-End-Pools in die Website mit der Edge-Pool, die wiederhergestellt wurde nicht erfolgreich ausgeführt wird blieb, sollten Sie aktualisieren die Webkonferenzdienst und A / V-Konferenzdienst auf diesen Front-End-pools erneut verwenden die Edge-Pools in ihrer lokalen Website.</span><span class="sxs-lookup"><span data-stu-id="62176-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="62176-241">Wenn Sie der Front-End-Pool am selben Standort wie der ausgefallene edgepool ebenfalls ausgefallen ist, können Sie jetzt Invoke – CsPoolFailback Failback für den Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="62176-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="62176-242">Ändern des Edge-Pools einen Front-End-Pool zugeordnet</span><span class="sxs-lookup"><span data-stu-id="62176-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="62176-243">Wenn Sie ein edgepool ausfällt, jedoch der Front-End-Pool am selben Standort weiterhin ausgeführt wird, müssen Sie den Front-End-Pool einen edgepool an einem anderen Standort verwenden, bis der ausgefallene edgepool wiederhergestellt wird festgelegt.</span><span class="sxs-lookup"><span data-stu-id="62176-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="62176-244">Navigieren Sie im Topologie-Generator auf den Namen des Front-End-Pools, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="62176-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="62176-245">Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62176-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="62176-246">Verwenden Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** das Dropdown-Feld den Edge-Pool wählen, dem Sie diese Front-End-Pool zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="62176-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="62176-247">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62176-247">Click **OK**.</span></span>
