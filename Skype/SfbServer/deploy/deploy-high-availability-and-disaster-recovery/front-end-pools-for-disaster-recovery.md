---
title: Bereitstellen Sie kombinierte Front-End-Pools für Disaster Recovery in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Sie können Front-End-Poolpaare verwenden, um Schutz durch Notfallwiederherstellung bereitzustellen. Dies ist jedoch nicht erforderlich.
ms.openlocfilehash: 028e0b4966a15b81b3e6e5627e63261207835f1f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225539"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="a8186-103">Bereitstellen Sie kombinierte Front-End-Pools für Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a8186-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="a8186-104">Sie können Front-End-Poolpaare verwenden, um Schutz durch Notfallwiederherstellung bereitzustellen. Dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a8186-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="a8186-105">Sie können die notfallwiederherstellungstopologie eines Paars Front-End-Pools des Topologie-Generators auf einfache Weise bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a8186-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="a8186-106">So stellen Sie ein Front-End-Poolpaar bereit</span><span class="sxs-lookup"><span data-stu-id="a8186-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="a8186-107">Wenn die Pools neu und noch nicht definiert sind, verwenden Sie zum Erstellen der Pools Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="a8186-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="a8186-108">Klicken Sie im Topologie-Generator Maustaste auf eine der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a8186-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a8186-109">Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich die Option **Zugeordneter Sicherungspool** aus.</span><span class="sxs-lookup"><span data-stu-id="a8186-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="a8186-p101">Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.</span><span class="sxs-lookup"><span data-stu-id="a8186-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="a8186-112">Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8186-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="a8186-113">Wenn Sie die Details zu diesem Pool anzeigen, erscheint der zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**. </span><span class="sxs-lookup"><span data-stu-id="a8186-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="a8186-114">Verwenden Sie zum Veröffentlichen der Topologie Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="a8186-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="a8186-p102">Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Die letzten beiden Schritte in diesem Verfahren können Sie überspringen.</span><span class="sxs-lookup"><span data-stu-id="a8186-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="a8186-117">Wenn die Pools jedoch bereits bereitgestellt waren, bevor Sie die Paarbeziehung definiert haben, müssen Sie die beiden folgenden abschließenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a8186-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="a8186-118">Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a8186-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="a8186-119">Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a8186-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="a8186-120">Führen Sie aus einer Skype für Business Server-Verwaltungsshell an der Eingabeaufforderung folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="a8186-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="a8186-121">Verwenden Sie die folgenden Cmdlets, um zu erzwingen, dass die Benutzer- und Konferenzdaten beider Pools miteinander synchronisiert werden:</span><span class="sxs-lookup"><span data-stu-id="a8186-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="a8186-p103">Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu überprüfen. Stellen Sie sicher, dass der Status für beide Richtungen stabil ist.</span><span class="sxs-lookup"><span data-stu-id="a8186-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="a8186-125">Die Option **Automatisches Failover und Failback für VoIP** und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die VoIP-ausfallsicherheit-Funktionen, die in Lync Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="a8186-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="a8186-126">Durch Auswählen dieser Option impliziert nicht, dass die in diesem Dokument beschriebenen poolfailover automatisch erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a8186-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="a8186-127">Failover und Failback müssen immer ein Administrator manuell die Cmdlets Failover und Failback jeweils aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a8186-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8186-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8186-128">See also</span></span>

[<span data-ttu-id="a8186-129">Front-End-Pool Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a8186-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
