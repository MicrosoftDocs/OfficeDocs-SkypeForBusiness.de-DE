---
title: Upgrade auf Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Zusammenfassung: Informationen Sie zum Upgrade von Lync Server 2013 zu Skype für Business Server 2015. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 5c23faeb1dca662b80855b87a93152b3e81de43d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885145"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="783f0-104">Upgrade auf Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="783f0-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="783f0-105">**Zusammenfassung:** Informationen Sie zum upgrade von Lync Server 2013 zu Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="783f0-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="783f0-106">Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="783f0-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="783f0-107">Verwenden Sie die Verfahren in diesem Dokument von Lync Server 2013 auf Skype für Business Server 2015 Aktualisieren mithilfe der Skype für Business Server-Topologie-Generator und das neue Feature In-Place Upgrade.</span><span class="sxs-lookup"><span data-stu-id="783f0-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="783f0-108">Wenn Sie von Lync Server 2010 oder Office Communications Server 2007 R2 aktualisieren möchten, finden Sie unter [Planen eines Upgrades auf Skype für Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="783f0-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="783f0-109">Compliance-Upgrades in Skype für Business Server 2015 verfügbar waren, jedoch werden in Skype für Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="783f0-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="783f0-110">Nebeneinander Koexistenz unterstützt wird, finden Sie weitere Informationen unter [Migration zu Skype für Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) .</span><span class="sxs-lookup"><span data-stu-id="783f0-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="783f0-111">Aktualisieren von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="783f0-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="783f0-112">Aktualisieren von Lync Server 2013 auf Skype für Business Server 2015 bei der Installation der erforderlichen Software, mit der Skype für Business Server-Topologie-Generator zum upgrade von Datenbanken im Pool und mithilfe der Skype für Business Server In-Place Upgrade auf jedem der Server, die dem Pool zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="783f0-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="783f0-113">Zum Durchführen eines Upgrades führen Sie die acht Schritte im vorliegenden Thema aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="783f0-114">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="783f0-114">Before you begin</span></span>

- <span data-ttu-id="783f0-115">Überprüfen Sie [Planen eines Upgrades auf Skype für Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="783f0-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="783f0-116">Überprüfen Sie die [Anforderungen für Skype für Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="783f0-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="783f0-117">[Installieren erforderlicher Komponenten für Skype für Business Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="783f0-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="783f0-118">[Skype für Business Server 2015 installieren](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="783f0-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="783f0-119">Schritt 1: Administratortools installieren und Topologie herunterladen</span><span class="sxs-lookup"><span data-stu-id="783f0-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="783f0-120">Verbinden Sie mit Computer in der Topologie, die keine Lync OCSCore oder andere Lync-Komponenten installiert sind.</span><span class="sxs-lookup"><span data-stu-id="783f0-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="783f0-121">Skype für Business Server 2015-Installationsmedium führen Sie **Setup.exe** aus **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="783f0-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="783f0-122">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="783f0-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="783f0-123">Akzeptieren Sie die Lizenzvereinbarungen.</span><span class="sxs-lookup"><span data-stu-id="783f0-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="783f0-124">Klicken Sie im Bereitstellungs-Assistenten auf **Administratortools installieren** und befolgen Sie die Schritte zur Installation.</span><span class="sxs-lookup"><span data-stu-id="783f0-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Screenshot des Bereitstellungsassistenten mit der aufgerufenen Verknüpfung „Administratortools installieren“.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="783f0-126">Öffnen Sie in der Windows-Startseite Skype für Business Server-Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="783f0-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="783f0-127">Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="783f0-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="783f0-128">Geben Sie einen Namen für die Topologie ein und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="783f0-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="783f0-129">Gehen Sie zu dem Speicherort, an dem die Topologie gespeichert ist, und erstellen Sie eine Kopie der Topologie.</span><span class="sxs-lookup"><span data-stu-id="783f0-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="783f0-130">Schritt 2: Upgrade und Veröffentlichen der Topologie mit dem Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="783f0-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="783f0-131">Bevor Sie den Upgradeprozess beginnen, müssen alle Dienste für die Pools ausgeführt werden, den, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="783f0-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="783f0-132">Die Topologieänderungen werden in der lokalen Datenbank der Server im Pool repliziert.</span><span class="sxs-lookup"><span data-stu-id="783f0-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="783f0-133">Speichern Sie vor dem Upgrade eine Kopie Ihrer Topologiedatei.</span><span class="sxs-lookup"><span data-stu-id="783f0-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="783f0-134">Nach dem upgrade Sie ist nicht möglich, um die herabzustufen Topologie. > Wenn Ihre Dienste auf den gleichen Servern werden wie Ihre Datenbanken, wie Sie den beständigen Chat-Dienst auf demselben Server wie die Datenbank für beständigen Chat ist, um diesen Schritt überspringen, und gehen Sie zu Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="783f0-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="783f0-135">Wenn Sie die Dienste angehalten haben, führen Sie das Setup der Funktion für direkte Upgrades auf jedem Server zum Aktualisieren der lokalen Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="783f0-p108">Wenn die Topologie eine gespiegelte Back-End-Datenbank hat, werden Sie feststellen, dass sowohl der Prinzipalserver als auch die gespiegelten Datenbanken angezeigt werden, **wenn Sie die Topologie mithilfe des Topologie-Generators veröffentlichen**. Stellen Sie sicher, dass sämtliche Datenbanken auf dem Prinzipalserver laufen und dass Sie beim Veröffentlichen der Topologie nur die Prinzipaldatenbank und nicht die Spiegelung auswählen, andernfalls wird nach der Veröffentlichung der Topologie eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="783f0-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="783f0-138">Wählen Sie eine der folgenden Optionen aus, aktualisieren und veröffentlichen eine neue Topologie mithilfe der Skype für Business Server 2015 Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="783f0-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="783f0-139">Nachdem Sie die Schritte vollständig ausgeführt haben und die Topologie veröffentlicht haben, für die das Upgrade ausgeführt wurde, fahren Sie mit Schritt 3 in diesem Thema fort.</span><span class="sxs-lookup"><span data-stu-id="783f0-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="783f0-140">Option 1: Upgrade eines isolierten Front-End-Pools und der zugehörigen Speicher für die Archivierung und Überwachung</span><span class="sxs-lookup"><span data-stu-id="783f0-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="783f0-141">Wenn der Pool, für den Sie ein Upgrade durchführen möchten, vom Speicher zur Archivierung und Überwachung abhängig ist, wird mithilfe der folgenden Schritte auch für den Speicher zur Archivierung und Überwachung ein Upgrade durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="783f0-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="783f0-142">Im Topologie-Generator mit der rechten Maustaste in eines Pools von Lync Server 2013, Option **auf Skype für Business Server 2015 aktualisieren**, und führen Sie die Schritte.</span><span class="sxs-lookup"><span data-stu-id="783f0-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="783f0-144">Klicken Sie im Topologie-Generator auf **Aktion** > **Topologie veröffentlichen** oder **Aktion** > **Topologie** > **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="783f0-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Screenshot des Menüs „Aktion“ mit der Option „Topologie veröffentlichen“ im Topology-Generator.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="783f0-146">Wählen Sie während der Veröffentlichung die Installation einer Datenbank im Speicher für die Archivierung und Überwachung aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="783f0-147">Option 2: Upgrade Front-End-Pool ohne zu aktualisieren, Archivierung und Überwachung von Speicher</span><span class="sxs-lookup"><span data-stu-id="783f0-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="783f0-p110">Mithilfe der folgenden Anweisungen wird die Archivierung und Überwachung für den ausgewählten Pool deaktiviert. Der Pool weist nach dem Upgrade keine Speicher für die Archivierung und Überwachung auf.</span><span class="sxs-lookup"><span data-stu-id="783f0-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="783f0-150">Wählen Sie im Topologie-Generator den Lync Server 2013-Pool, den Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="783f0-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="783f0-151">Entfernen Sie die Abhängigkeit auf die Lync Server 2013-Archivierung und Überwachung Speicher.</span><span class="sxs-lookup"><span data-stu-id="783f0-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="783f0-152">Klicken Sie auf **Aktion** > **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="783f0-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="783f0-153">Deaktivieren Sie das Kontrollkästchen **Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="783f0-153">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot des Kontrollkästchens „Archivierung“ im Dialogfeld „Eigenschaften bearbeiten“.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="783f0-155">Deaktivieren Sie das Kontrollkästchen **Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="783f0-155">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“ mit dem Kontrollkästchen „Überwachung“.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="783f0-157">Mit der rechten Maustaste in des Lync Server 2013-Pools, wählen Sie die **Durchführen eines Upgrades auf Skype für Business Server 2015**, und führen Sie die Schritte.</span><span class="sxs-lookup"><span data-stu-id="783f0-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="783f0-159">Klicken Sie im Topologie-Generator auf **Aktion** > **Topologie veröffentlichen** oder **Aktion** > **Topologie** > **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="783f0-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="783f0-160">Option 3: Upgrade Front-End-Pool und neue Skype für Business Server 2015 Archivierung und Überwachung Informationsspeicher zugeordnet</span><span class="sxs-lookup"><span data-stu-id="783f0-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="783f0-161">Wenn Sie die folgenden Anweisungen ausführen, wird die Archivierung und Überwachung im vorherigen Speicher abgebrochen und im neuen, von Ihnen erstellten Speicher gestartet.</span><span class="sxs-lookup"><span data-stu-id="783f0-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="783f0-162">Wählen Sie im Topologie-Generator den Lync Server 2013-Pool, den Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="783f0-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="783f0-163">Entfernen Sie die Abhängigkeit auf die Lync Server 2013-Archivierung und Überwachung Speicher.</span><span class="sxs-lookup"><span data-stu-id="783f0-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="783f0-164">Klicken Sie auf **Aktion** > **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="783f0-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="783f0-165">Deaktivieren Sie das Kontrollkästchen **Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="783f0-165">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot des Kontrollkästchens „Archivierung“ im Dialogfeld „Eigenschaften bearbeiten“.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="783f0-167">Deaktivieren Sie das Kontrollkästchen **Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="783f0-167">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“ mit dem Kontrollkästchen „Überwachung“.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="783f0-169">Mit der rechten Maustaste in des Lync Server 2013-Pools, wählen Sie die **Durchführen eines Upgrades auf Skype für Business Server 2015**, und führen Sie die Schritte.</span><span class="sxs-lookup"><span data-stu-id="783f0-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="783f0-171">Erstellen Sie einen neuen SQL-Speicher für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="783f0-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="783f0-172">Wählen Sie den Pool und die **Aktion** > **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="783f0-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="783f0-173">Aktivieren Sie das Kontrollkästchen **Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="783f0-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="783f0-174">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="783f0-174">Click **New**.</span></span>
    
     ![Screenshot des Dialogfelds „Bearbeiten von Eigenschaften“, in dem im Bereich „Archivierung“ die Schaltfläche „Neu“ angezeigt wird.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="783f0-176">Erstellen Sie einen neuen SQL-Speicher für die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="783f0-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="783f0-177">Wählen Sie den Pool und die **Aktion** > **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="783f0-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="783f0-178">Wählen Sie das Kontrollkästchen **Überwachung** aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="783f0-179">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="783f0-179">Click **New**.</span></span>
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“, in dem im Bereich „Überwachung“ die Schaltfläche „Neu“ angezeigt wird.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="783f0-181">Klicken Sie im Topologie-Generator auf **Aktion** > **Topologie veröffentlichen** oder **Aktion** > **Topologie** > **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="783f0-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="783f0-182">Wählen Sie während der Veröffentlichung die Installation einer Datenbank im neuen Speicher für die Archivierung und Überwachung aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="783f0-183">Schritt 3: Auf die Replikation warten</span><span class="sxs-lookup"><span data-stu-id="783f0-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="783f0-184">Die Replikation nimmt etwas Zeit in Anspruch, um die aktualisierte Topologie auf allen Servern der Umgebung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="783f0-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="783f0-185">Schritt 4: Alle Dienste im Pool abbrechen, für den ein Upgrade durchgeführt werden soll</span><span class="sxs-lookup"><span data-stu-id="783f0-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="783f0-186">Auf jedem Server bedient, die den Pool, den Sie möchten aktualisieren, führen Sie das folgende Cmdlet in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="783f0-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="783f0-187">Es wird empfohlen, Disable-CsComputer verwenden, da Sie möglicherweise den Server während des Vorgangs In-Place Upgrade neu starten müssen.</span><span class="sxs-lookup"><span data-stu-id="783f0-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="783f0-188">Wenn Sie „Stop-CsWindowsService“ verwenden, werden einige Dienste nach einem Computerneustart eventuell automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="783f0-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="783f0-189">Dies kann dazu führen, dass das direkte Upgrade nicht ordnungsgemäß ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="783f0-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="783f0-190">Schritt 5: Upgrades für Front-End-Pools und Nicht-Front-End-Pool-Server durchführen</span><span class="sxs-lookup"><span data-stu-id="783f0-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="783f0-191">Vor dem Aktualisieren installieren Sie alle neue erforderlichen Komponenten für Skype für Business Server 2015 benötigt die umfassen: > mindestens 32GB freiem Speicherplatz, bevor Sie versuchen, ein Upgrade.</span><span class="sxs-lookup"><span data-stu-id="783f0-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="783f0-192">Darüber hinaus stellen Sie sicher, dass das Laufwerk eine lokale Festplatte ist, nicht über USB oder Firewire verbunden ist, mit dem NTFS-Dateisystem formatiert ist, nicht komprimiert ist und keine Seite Datei enthält. > PowerShell, Version 6.2.9200.0 oder höher. > die neuesten Lync Server 2013 Kumulatives Update installiert. > SQL Server 2012 SP1 installiert. > die folgenden KB (automatisch installiert, wenn Microsoft Update verwenden) durch die Installation: > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="783f0-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="783f0-193">Verwenden Sie die In-Place Upgrade auf jedem Server, um den Front-End-Pool, edgepool, Mediation Server und Pools für beständigen Chat zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="783f0-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="783f0-194">Führen Sie auf jedem Server **Setup.exe** aus **OCS_Volume\Setup\amd64** auf die Skype für Business Server 2015-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="783f0-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="783f0-195">Akzeptieren Sie den Lizenzvertrag, und folgen Sie den Anweisungen für die In-Place Upgrade.</span><span class="sxs-lookup"><span data-stu-id="783f0-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="783f0-196">Wiederholen Sie diese Schritte für jeden Server im Front-End-Pool und auf jedem Poolserver der nicht - Front-End-aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="783f0-197">Sie werden möglicherweise während des direkten Upgrades zum Neustarten des Servers aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="783f0-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="783f0-198">Das ist normal.</span><span class="sxs-lookup"><span data-stu-id="783f0-198">That's ok.</span></span> <span data-ttu-id="783f0-199">Nach einem Neustart, wird die In-Place Upgrade aus, an der Stelle fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="783f0-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="783f0-200">Nach dem erfolgreichen direkten Upgrade wird Ihnen die folgende Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="783f0-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Screenshot mit erfolgreich abgeschlossenem direktem Upgrade.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="783f0-202">Schritt 6: Dienste auf den Servern mit Upgrade neu starten</span><span class="sxs-lookup"><span data-stu-id="783f0-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="783f0-203">Vor dem Neustart der Dienste, stellen Sie sicher, dass %ProgramData%\WindowsFabric auf allen Front-End-Servern nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="783f0-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="783f0-204">Falls doch, löschen Sie es, bevor Sie die Dienste starten.</span><span class="sxs-lookup"><span data-stu-id="783f0-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="783f0-205">Nachdem Sie alle Server in der Front-End-Pool aktualisiert haben, starten Sie die Dienste mit den folgenden PowerShell-Befehl neu:</span><span class="sxs-lookup"><span data-stu-id="783f0-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="783f0-p115">Wenn bereits ein anstehender Systemstart erforderlich ist, bevor sie das direkte Upgrade ausführen, werden Sie beim direkten Upgrade am Ende der Installation nicht zu einem Neustart aufgefordert. Dies führt zu Assembly-Ausnahmen gegenüber dem ersten Front-End-Server, wenn Sie versuchen, die Services mit dem Start-CSPool-Cmdlet zu starten. Nehmen Sie zur Fehlerbehebung einen Neustart aller Server im Pool vor und führen Sie das Cmdlet dann erneut aus.</span><span class="sxs-lookup"><span data-stu-id="783f0-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="783f0-209">Für Nicht-Front-End-Poolserver starten Sie die Dienste mithilfe des folgenden Befehls neu:</span><span class="sxs-lookup"><span data-stu-id="783f0-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="783f0-210">Nachdem Sie auf der Seite für das direkte Upgrade auf **OK** geklickt haben, wird folgende Erinnerung an die Ausführung dieses Schritts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="783f0-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Screenshot, der die nächsten Schritte nach dem erfolgreichen Abschluss eines direkten Upgrades zeigt.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="783f0-212">Schritt 7: Überprüfen Sie, ob es sich bei Skype für Business Funktionalität works</span><span class="sxs-lookup"><span data-stu-id="783f0-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="783f0-213">Stellen Sie sicher, dass das Upgrade für den Pool erfolgreich war, die aktualisiert wurde, testen Sie Skype für Unternehmen, um sicherzustellen, dass die Funktionalität wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="783f0-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="783f0-214">Schritt 8: Ein Upgrade der sekundären Pools durchführen</span><span class="sxs-lookup"><span data-stu-id="783f0-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="783f0-215">Wiederholen Sie die Schritte in diesem Thema, um ein Upgrade aller zusätzlichen Pools durchzuführen, die in Ihrer Umgebung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="783f0-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="783f0-216">Problembehandlung beim direkten Upgrade</span><span class="sxs-lookup"><span data-stu-id="783f0-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="783f0-217">Wenn das direkte Upgrade fehlschlägt, wird Ihnen ggf. eine Meldung angezeigt, die in etwa dem folgenden Bild entspricht.</span><span class="sxs-lookup"><span data-stu-id="783f0-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Screenshot, der einen Fehler bei einem direkten Upgrade zeigt, das fehlschlägt, weil ein benötigtes kumulatives Update nicht installiert war.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="783f0-p116">Überprüfen Sie die vollständige Meldung unten auf der Seite, um Hilfe zur Fehlerbehebung zu erhalten. Klicken Sie auf **Protokoll anzeigen**, um mehr Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="783f0-p116">Review the full message at the bottom of the page to help you troubleshoot the issue. Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="783f0-221">Ausfall der In-Place Upgrade auf **Verifying upgraden Bereitschaft** oder **Fehlende erforderliche Komponenten installieren**, stellen Sie sicher, dass der Server hat die neuesten Windows Server, Lync Server und SQL Server Updates angewendet und die gesamte erforderliche Software und Rollen werden installiert.</span><span class="sxs-lookup"><span data-stu-id="783f0-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="783f0-222">Eine Liste der was erforderlich ist finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Installieren der erforderlichen Komponenten für Skype für Business Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="783f0-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="783f0-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="783f0-223">See also</span></span>

[<span data-ttu-id="783f0-224">Planen des Upgrades auf Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="783f0-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="783f0-225">Serveranforderungen für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="783f0-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="783f0-226">Installieren der erforderlichen Komponenten für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="783f0-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="783f0-227">Installieren von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="783f0-227">Install Skype for Business Server 2015</span></span>](install/install.md)