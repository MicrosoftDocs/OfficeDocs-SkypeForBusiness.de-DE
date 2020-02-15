---
title: Verbinden eines Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient. Wenn die Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBVg von der Front-End-Pool entfernt werden, während der Pool aktualisiert wird, nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBVg erneut mit der aktualisierten Front E verbunden werden. ND-Pool. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zuerst in eine andere Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBVg der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBVg verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:'
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027786"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="af204-108">Verbinden eines Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="af204-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="af204-109">Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient.</span><span class="sxs-lookup"><span data-stu-id="af204-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="af204-110">Wenn die Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBVg von der Front-End-Pool entfernt werden, während der Pool aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="af204-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="af204-111">Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBVg erneut mit der aktualisierten Front-End-Pool verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="af204-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="af204-112">Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie.</span><span class="sxs-lookup"><span data-stu-id="af204-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="af204-113">Benutzer, die in der Legacy-SBA verwaltet werden, müssen zuerst in eine andere Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="af204-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="af204-114">Nachdem die SBVg der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBVg verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="af204-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="af204-115">Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="af204-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="af204-116">Verlagern von Zweigstellenbenutzern, die sich in der Legacy-SBA befinden, in eine andere Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="af204-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="af204-117">Entfernen Sie SBA aus der Legacy Topologie, um die vorhandene Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="af204-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="af204-118">Fügen Sie SBA zur Skype for Business Server 2019-Topologie hinzu, und konfigurieren Sie diese neue Front-End-Pool als Sicherungs Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="af204-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="af204-119">Stellen Sie die Zweigstellenbenutzer in die neue Skype for Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="af204-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="af204-120">Hinzufügen eines Legacy-SBA-Zweigstellen Standorts zu Ihrer Topologie</span><span class="sxs-lookup"><span data-stu-id="af204-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="af204-121">Öffnen Sie den **Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="af204-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="af204-122">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Zweigstellenstandorte**, und klicken Sie dann auf **Neue Zweigstelle**.</span><span class="sxs-lookup"><span data-stu-id="af204-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="af204-123">Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.</span><span class="sxs-lookup"><span data-stu-id="af204-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="af204-124">(Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.</span><span class="sxs-lookup"><span data-stu-id="af204-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="af204-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af204-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="af204-126">(Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="af204-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="af204-127">Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="af204-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="af204-128">Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="af204-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="af204-129">Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="af204-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="af204-130">Klicken Sie auf **weiter**, und wenn Sie eine Survivable Branch Appliance oder einen Server an dieser Website verwenden, müssen Sie den Assistenten zum **Öffnen des neuen überlebten Assistenten deaktivieren, wenn dieser Assistent geschlossen** wird.</span><span class="sxs-lookup"><span data-stu-id="af204-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="af204-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="af204-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="af204-132">So ordnen Sie das Legacy-SBA dem Skype for Business Server 2019 Front-End-Pool zu:</span><span class="sxs-lookup"><span data-stu-id="af204-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="af204-133">Erweitern Sie den Zweigstellenstandort, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="af204-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="af204-134">Klicken Sie mit der rechten Maustaste auf ältere Version, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="af204-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="af204-135">Klicken Sie auf **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="af204-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="af204-136">Befolgen Sie die Anweisungen im Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="af204-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="af204-137">Informationen zu Assistenten Elementen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="af204-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="af204-138">Ein Survivable Branch Appliance kann nur einem Überwachungsspeicher zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="af204-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="af204-139">Wenn Sie an diesem Standort keinen Survivable Branch Appliance oder Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="af204-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="af204-140">Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, den Sie der Topologie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="af204-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

