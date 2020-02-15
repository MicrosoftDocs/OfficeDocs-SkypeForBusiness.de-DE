---
title: Verbinden des pilotpools mit Legacy-Edge-Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39f3444c0d660a1ed73da566df6b5b348171f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="098d0-102">Verbinden des pilotpools mit Legacy-Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="098d0-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="098d0-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="098d0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="098d0-104">Nach der Bereitstellung lync Server 2013 ist eine Verbund Route für diesen Standort nicht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="098d0-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="098d0-105">Um die von Office Communications Server 2007 R2 verwendete Verbund Route verwenden zu können, müssen lync Server 2013 für die Verwendung dieser Route konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="098d0-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="098d0-106">Damit die lync Server 2013 Website den Director und Edgeserver des BackCompatSite verwenden kann, ordnen Sie die Legacy Edgepool mithilfe des Topologie-Generators zu.</span><span class="sxs-lookup"><span data-stu-id="098d0-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="098d0-107">So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="098d0-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="098d0-108">Öffnen Sie den Pilotpool im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="098d0-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="098d0-109">Wählen Sie Ihre lync Server 2013 Website aus.</span><span class="sxs-lookup"><span data-stu-id="098d0-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="098d0-110">Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="098d0-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="098d0-111">Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann den Office Communications Server 2007 R2 Director oder den Office Communications Server 2007 R2 Edgeserver, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="098d0-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="098d0-112">![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"")</span><span class="sxs-lookup"><span data-stu-id="098d0-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="098d0-113">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="098d0-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="098d0-114">Navigieren Sie im Topologie-Generator unter dem Knoten lync Server 2013 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="098d0-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="098d0-115">Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="098d0-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="098d0-116">Wählen Sie in der Liste die Edgeserverschnittstelle für BackCompatSite aus.</span><span class="sxs-lookup"><span data-stu-id="098d0-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="098d0-117">![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")</span><span class="sxs-lookup"><span data-stu-id="098d0-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="098d0-118">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="098d0-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="098d0-119">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten aus, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="098d0-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="098d0-120">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="098d0-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="098d0-121">Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="098d0-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

