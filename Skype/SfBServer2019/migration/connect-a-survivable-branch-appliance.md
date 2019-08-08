---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verbunden, der als Backup-Registrar für die SBA fungiert. Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBA vom Front-End-Pool entfernt werden, während der Pool aktualisiert wird, nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBA erneut mit dem aktualisierten Front-E verknüpft werden. ND-Pool. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zunächst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBA zur Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden. Nachfolgend werden die folgenden Schritte zusammengefasst:'
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239284"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="69f56-108">Verbinden einer Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="69f56-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="69f56-109">Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verknüpft, der als Sicherungs Registrierungsstelle für die SBA fungiert.</span><span class="sxs-lookup"><span data-stu-id="69f56-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="69f56-110">Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss der SBA beim Upgrade des Pools vom Front-End-Pool abgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="69f56-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="69f56-111">Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann der SBA dem aktualisierten Front-End-Pool erneut zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="69f56-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="69f56-112">Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie.</span><span class="sxs-lookup"><span data-stu-id="69f56-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="69f56-113">Benutzer, die in der Legacy-SBA verwaltet werden, müssen zunächst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="69f56-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="69f56-114">Nachdem die SBA zur Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="69f56-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="69f56-115">Nachfolgend werden die folgenden Schritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="69f56-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="69f56-116">Verschieben Sie Branch-Benutzer, die sich im Legacy-SBA befinden, in einen anderen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="69f56-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="69f56-117">Entfernen Sie SBA aus der Legacy Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="69f56-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="69f56-118">Fügen Sie SBA zur Skype for Business Server 2019-Topologie hinzu, und konfigurieren Sie diesen neuen Front-End-Pool als Sicherungs Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="69f56-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="69f56-119">Verschieben Sie die Benutzer der Verzweigung in den neuen Skype for Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="69f56-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="69f56-120">Hinzufügen einer älteren SBA-Verzweigungs Website zu Ihrer Topologie</span><span class="sxs-lookup"><span data-stu-id="69f56-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="69f56-121">Öffnen Sie den **Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="69f56-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="69f56-122">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.</span><span class="sxs-lookup"><span data-stu-id="69f56-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="69f56-123">Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="69f56-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="69f56-124">Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="69f56-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="69f56-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69f56-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="69f56-126">Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="69f56-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="69f56-127">Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="69f56-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="69f56-128">Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.</span><span class="sxs-lookup"><span data-stu-id="69f56-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="69f56-129">Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="69f56-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="69f56-130">Klicken Sie auf **weiter**, und wenn Sie eine überlebensfähige Branch-Appliance oder einen Server an dieser Website verwenden, müssen Sie das Kontrollkästchen **den neuen Überlebenden-Assistenten öffnen, wenn dieser Assistent geschlossen** wird, deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="69f56-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="69f56-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="69f56-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="69f56-132">So ordnen Sie das Legacy-SBA dem Skype for Business Server 2019-Front-End-Pool zu:</span><span class="sxs-lookup"><span data-stu-id="69f56-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="69f56-133">Erweitern Sie die erstellte Verzweigungs Website.</span><span class="sxs-lookup"><span data-stu-id="69f56-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="69f56-134">Klicken Sie mit der rechten Maustaste auf Legacy Version, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="69f56-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="69f56-135">Klicken Sie auf **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="69f56-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="69f56-136">Folgen Sie den Anweisungen im Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="69f56-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="69f56-137">Informationen zu Assistenten Elementen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="69f56-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="69f56-138">Eine Survivable Branch-Appliance kann nur einem Überwachungsspeicher zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="69f56-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="69f56-139">Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="69f56-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="69f56-140">Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie der Topologie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="69f56-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

