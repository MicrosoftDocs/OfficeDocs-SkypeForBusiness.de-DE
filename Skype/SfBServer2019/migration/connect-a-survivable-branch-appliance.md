---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Jeder Survivable Branch Appliance (SBA) ist einem Front-End-Pool die dient als sicherungsregistrierung für die SBA zugeordnet. Wenn der Front-End Pool zu Skype für Business Server 2019, die SBA migriert wurde während der Pool aktualisiert wird, sobald der Pool zu Skype für Business Server 2019 migriert wurde, aus dem Front-End-Pool getrennt werden müssen, kann die SBA mit der aktualisierten Front-E erneut verknüpft werden. Nd-Pool. Dies umfasst die SBA aus der Vorversion Topologie im Topologie-Generator löschen und dann die Skype für Business Server 2019 Topologie die SBA hinzuzufügen. Benutzer, die sich in der Legacy-SBA zuerst in einen anderen Front-End-Pool verschoben werden muss vor dem Entfernen der SBA aus der Topologie. Nachdem die Skype für Business Server 2019 Topologie die SBA hinzugefügt wird, können diese Benutzer dann wieder auf die SBA verschoben werden. Diese Schritte werden im folgenden zusammengefasst:'
ms.openlocfilehash: e4917b20e9e680627e92935dcb10ebf06c2e3d2d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887484"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="e5877-108">Verbinden einer Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="e5877-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="e5877-109">Jeder Survivable Branch Appliance (SBA) ist einem Front-End-Pool, der als sicherungsregistrierung für die SBA fungiert zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e5877-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="e5877-110">Wenn Sie der Front-End-Pool zu Skype für Business Server 2019 migriert wurde, muss die SBA aus dem Front-End-Pool aufgehoben werden soll, während der Pool aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5877-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="e5877-111">Nach der Pool zu Skype für Business Server 2019 migriert wurde, kann die SBA wieder mit dem aktualisierten Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e5877-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="e5877-112">Dies umfasst die SBA aus der Vorversion Topologie im Topologie-Generator löschen und dann die Skype für Business Server 2019 Topologie die SBA hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5877-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="e5877-113">Benutzer, die sich in der Legacy-SBA zuerst in einen anderen Front-End-Pool verschoben werden muss vor dem Entfernen der SBA aus der Topologie.</span><span class="sxs-lookup"><span data-stu-id="e5877-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="e5877-114">Nachdem die Skype für Business Server 2019 Topologie die SBA hinzugefügt wurde, können diese Benutzer wieder auf die SBA verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="e5877-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="e5877-115">Diese Schritte werden im folgenden zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="e5877-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="e5877-116">Verschieben Sie Benutzer an Zweigstellenstandorten in der Vorversion SBA in einen anderen Front-End-Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e5877-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="e5877-117">Entfernen der SBA aus der Vorversion Topologie der vorhandenen Front-End-Pools als sicherungsregistrierung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="e5877-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="e5877-118">Fügen Sie der SBA zur die Skype für Business Server 2019 Topologie hinzu und konfigurieren Sie dieses neuen Front-End-Pools als sicherungsregistrierung.</span><span class="sxs-lookup"><span data-stu-id="e5877-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="e5877-119">Verschieben der Zweigstellenbenutzer auf die neue Skype für Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="e5877-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="e5877-120">Hinzufügen der Vorversion SBA-Zweigniederlassung zu einer Topologie</span><span class="sxs-lookup"><span data-stu-id="e5877-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="e5877-121">**Topologie-Generator**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5877-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="e5877-122">Klicken Sie im linken Bereich mit der rechten Maustaste **Zweigniederlassungen**, und klicken Sie dann auf **Neue Zweigniederlassung**.</span><span class="sxs-lookup"><span data-stu-id="e5877-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="e5877-123">Klicken Sie auf **Name**, und geben Sie den Namen des zweigstellenstandorts, klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** .</span><span class="sxs-lookup"><span data-stu-id="e5877-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="e5877-124">(Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="e5877-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="e5877-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5877-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="e5877-126">(Optional) Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e5877-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="e5877-127">Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in dem sich die Zweigniederlassung befindet.</span><span class="sxs-lookup"><span data-stu-id="e5877-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="e5877-128">Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen der das Bundesland oder die Region, in dem sich die Zweigniederlassung befindet.</span><span class="sxs-lookup"><span data-stu-id="e5877-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="e5877-129">Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen aufrufenden Code für das Land/Region, in dem sich die Zweigniederlassung befindet.</span><span class="sxs-lookup"><span data-stu-id="e5877-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="e5877-130">Klicken Sie auf **Weiter**, und klicken Sie dann, wenn Sie eine Survivable Branch Appliance oder einen Server an diesem Standort arbeiten, werden Sie sicher, dass Sie das Kontrollkästchen **Öffnen Sie den neuen Survivable Assistenten Wenn dieser Assistent geschlossen** .</span><span class="sxs-lookup"><span data-stu-id="e5877-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="e5877-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e5877-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="e5877-132">So verknüpfen Sie die legacy-SBA der Skype für Business Server 2019 Front-End-Pool:</span><span class="sxs-lookup"><span data-stu-id="e5877-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="e5877-133">Erweitern Sie den Zweigstellenstandort, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5877-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="e5877-134">Mit der rechten Maustaste auf die ältere Version, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="e5877-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="e5877-135">Klicken Sie auf **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="e5877-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="e5877-136">Führen Sie die Schritte des Assistenten, das geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e5877-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="e5877-137">Informationen zum Assistenten für Elemente finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="e5877-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="e5877-138">Survivable Branch Appliance kann nur eine Überwachungsspeicher zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e5877-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="e5877-139">Wenn Sie nicht über eine Survivable Branch Appliance oder einen Server an diesem Standort arbeiten, deaktivieren Sie das Kontrollkästchen **Öffnen Sie den neuen Survivable Assistenten Wenn dieser Assistent geschlossen** , und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e5877-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="e5877-140">Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5877-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

