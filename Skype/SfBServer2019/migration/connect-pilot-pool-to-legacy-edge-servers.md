---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Föderations Route für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Föderations Route verwenden zu können, muss Skype for Business Server 2019 so konfiguriert sein, dass Sie diese Route verwenden kann.
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288628"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="dd6aa-104">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="dd6aa-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="dd6aa-105">Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Föderations Route für Ihre Website konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="dd6aa-106">Um die von der Legacy Installation verwendete Föderations Route verwenden zu können, muss Skype for Business Server 2019 so konfiguriert sein, dass Sie diese Route verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="dd6aa-107">Wenn Sie die Skype for Business Server 2019-Website für die Verwendung des Directors und des Edge-Servers der Legacy Bereitstellung aktivieren möchten, verwenden Sie den Topologie-Generator, um den Legacy-Edge-Pool zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="dd6aa-108">So ordnen Sie den Legacy-Edge-Pool mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="dd6aa-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="dd6aa-109">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="dd6aa-110">Wählen Sie Ihre Website aus, die sich direkt unterhalb des **Skype for Business Server** -Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="dd6aa-111">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="dd6aa-112">Wählen Sie im linken Bereich **Föderations Route**aus.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="dd6aa-113">Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann den Legacy-Director oder den Legacy-Edgeserver aus, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="dd6aa-114">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="dd6aa-115">Navigieren Sie im Topologie-Generator unter dem 2019-Knoten von Skype for Business Server zu den Front-End-Pools **Standard Edition Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="dd6aa-116">Aktivieren Sie unter **Zuordnungen**das Kontrollkästchen neben **Edge-Pool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="dd6aa-117">Wählen Sie in der Liste den Legacy-Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="dd6aa-118">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="dd6aa-119">Wählen Sie im **Topologie-Generator**den obersten Knoten, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="dd6aa-120">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="dd6aa-121">Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dd6aa-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

