---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Bereitstellung von Skype für Business Server 2019, müssen Sie eine der partnerverbundroute des Standorts für Ihre Website zu konfigurieren. Um die partnerverbundroute verwenden, die von der Vorversion Installation verwendet wird, muss Skype für Business Server 2019 konfiguriert sein, um diese Route verwendet werden.
ms.openlocfilehash: 5a3498041b4af762d184cd56e3883a90612b13e0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238668"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="e9779-104">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="e9779-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="e9779-105">Nach der Bereitstellung von Skype für Business Server 2019, müssen Sie eine der partnerverbundroute des Standorts für Ihre Website zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e9779-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="e9779-106">Um die partnerverbundroute verwenden, die von der Vorversion Installation verwendet wird, muss Skype für Business Server 2019 konfiguriert sein, um diese Route verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9779-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="e9779-107">Verwenden Sie zum Aktivieren der Skype für Business Server 2019 Standort den Director und Edgeserver der Bereitstellung der Vorversion verwenden Topologie-Generator edgepool der Vorgängerversion zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e9779-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="e9779-108">Edgepool der Vorgängerversion mithilfe des Topologie-Generator zuordnen</span><span class="sxs-lookup"><span data-stu-id="e9779-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="e9779-109">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e9779-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="e9779-110">Wählen Sie Ihren Standort, der direkt unterhalb des Knotens **Skype für Business Server** ist.</span><span class="sxs-lookup"><span data-stu-id="e9779-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="e9779-111">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e9779-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="e9779-112">Wählen Sie im linken Bereich die Option **partnerverbundroute**aus.</span><span class="sxs-lookup"><span data-stu-id="e9779-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="e9779-113">Klicken Sie unter **Zuweisung der partnerverbundroute Route**wählen Sie **SIP-Partnerverbund aktivieren**aus, und wählen Sie dann die Vorversion Director oder Edgeserver der Vorversion Wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="e9779-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="e9779-114">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e9779-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="e9779-115">Navigieren Sie im Topologie-Generator unter der Skype für Business Server 2019-Knoten zu der **Standard Edition-Server** oder **Enterprise Edition-Front-End-Pools**, mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e9779-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="e9779-116">Wählen Sie unter **Zuordnungen**das Kontrollkästchen neben **edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="e9779-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="e9779-117">Wählen Sie aus der Liste Edgeserver der Vorversion aus.</span><span class="sxs-lookup"><span data-stu-id="e9779-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="e9779-118">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e9779-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="e9779-119">Wählen Sie im **Topologie-Generator**den obersten Knoten, **Skype für Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="e9779-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="e9779-120">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e9779-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="e9779-121">Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e9779-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

