---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie Skype for Business Server 2019 bereitgestellt haben, müssen Sie eine partnerverbundroute für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Verbund Route verwenden zu können, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753925"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="fc8b5-104">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="fc8b5-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="fc8b5-105">Nachdem Sie Skype for Business Server 2019 bereitgestellt haben, müssen Sie eine partnerverbundroute für Ihre Website konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="fc8b5-106">Um die von der Legacy Installation verwendete Verbund Route verwenden zu können, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="fc8b5-107">Damit die Skype for Business Server 2019-Website den Director und Edgeserver der Legacy-Bereitstellung verwenden kann, ordnen Sie die Legacy Edgepool mithilfe des Topologie-Generators zu.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="fc8b5-108">So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="fc8b5-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="fc8b5-109">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="fc8b5-110">Wählen Sie Ihre Website aus, die sich direkt unterhalb des **Skype for Business Server** Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="fc8b5-111">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="fc8b5-112">Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="fc8b5-113">Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann Legacy Director oder Legacy Edgeserver aus, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="fc8b5-114">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="fc8b5-115">Navigieren Sie im Topologie-Generator unter dem Knoten Skype for Business Server 2019 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="fc8b5-116">Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="fc8b5-117">Wählen Sie in der Liste den Edgeserver der Vorversion aus.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="fc8b5-118">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="fc8b5-119">Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="fc8b5-120">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="fc8b5-121">Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="fc8b5-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

