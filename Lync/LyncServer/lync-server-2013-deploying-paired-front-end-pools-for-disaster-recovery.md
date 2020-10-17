---
title: 'Lync Server 2013: Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung'
description: 'Lync Server 2013: Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4846121f301d2bc7be1af9b58f0a0fef3f88e6d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555901"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1b8ab-103">Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b8ab-103">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b8ab-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1b8ab-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1b8ab-105">Sie können die Notfall Wiederherstellungs Topologie mit gepaarten Front-End-Pools problemlos mithilfe des Topologie-Generators bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="1b8ab-106">So stellen Sie ein Paar von Front-End-Pools bereit</span><span class="sxs-lookup"><span data-stu-id="1b8ab-106">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="1b8ab-107">Wenn die Pools neu und noch nicht definiert sind, verwenden Sie den Topologie-Generator, um die Pools zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="1b8ab-108">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1b8ab-109">Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich **Zugeordneter Sicherungspool**aus.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="1b8ab-p101">Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="1b8ab-112">![36080581-DB76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-DB76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="1b8ab-112">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="1b8ab-113">Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-113">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="1b8ab-114">Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-114">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="1b8ab-115">Verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-115">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="1b8ab-p102">Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten beiden Schritte in diesem Verfahren überspringen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="1b8ab-118">Wenn die Pools jedoch bereits bereitgestellt waren, bevor Sie die Paarbeziehung definiert haben, müssen Sie die beiden folgenden abschließenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-118">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="1b8ab-119">Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1b8ab-119">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="1b8ab-120">Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-120">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="1b8ab-121">Führen Sie an einer lync Server-Verwaltungsshell Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1b8ab-121">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="1b8ab-122">Verwenden Sie die folgenden Cmdlets, um zu erzwingen, dass die Benutzer- und Konferenzdaten beider Pools miteinander synchronisiert werden:</span><span class="sxs-lookup"><span data-stu-id="1b8ab-122">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="1b8ab-123">Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="1b8ab-124">Sie können die folgenden Cmdlets verwenden, um den Status zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="1b8ab-125">Stellen Sie sicher, dass sich der Status in beide Richtungen im stationären Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-125">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="1b8ab-126">Die Option <STRONG>Automatisches Failover und Failback für VoIP</STRONG> und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die Features der VoIP-Ausfallsicherheit, die in lync Server 2010 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-126">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="1b8ab-127">Die Auswahl dieser Option bedeutet nicht, dass das in diesem Dokument beschriebene Pool Failover automatisch erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="1b8ab-128">Für das Pool-Failover und das Failback muss ein Administrator immer manuell die Failover-und Failback-Cmdlets aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1b8ab-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

