---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="a1dc4-102">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="a1dc4-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1dc4-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a1dc4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a1dc4-104">Nach der Bereitstellung von lync Server 2013 ist eine Föderations Route für diesen Standort nicht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="a1dc4-105">Um die von Office Communications Server 2007 R2 verwendete Federated-Route zu verwenden, muss lync Server 2013 für die Verwendung dieser Route konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="a1dc4-106">Um die lync Server 2013-Website für die Verwendung des Directors und des Edge-Servers des BackCompatSite zu aktivieren, verwenden Sie den Topologie-Generator, um den Legacy-Edge-Pool zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="a1dc4-107">So ordnen Sie den Legacy-Edge-Pool mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="a1dc4-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="a1dc4-108">Öffnen Sie die Topologie des pilotpools im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="a1dc4-109">Wählen Sie Ihre lync Server 2013-Website aus.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="a1dc4-110">Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="a1dc4-111">Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann den Office Communications Server 2007 R2-Director oder den Office Communications Server 2007 R2-Edgeserver aus, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="a1dc4-112">![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Dialogfeld \"Eigenschaften bearbeiten\", Seite \"Verbund Route\"")</span><span class="sxs-lookup"><span data-stu-id="a1dc4-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="a1dc4-113">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="a1dc4-114">Navigieren Sie im Topologie-Generator unter dem lync Server 2013-Knoten zu den Front-End-Pools **Standard Edition Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="a1dc4-115">Aktivieren Sie unter **Zuordnungen**das Kontrollkästchen neben **Edge-Pool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="a1dc4-116">Wählen Sie in der Liste die Edge-Server-Oberfläche für den BackCompatSite aus.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="a1dc4-117">![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Dialogfeld \"Eigenschaften bearbeiten\", Seite \"Allgemein\"")</span><span class="sxs-lookup"><span data-stu-id="a1dc4-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="a1dc4-118">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="a1dc4-119">Wählen Sie im **Topologie-Generator**den obersten Knoten, **lync Server**, aus.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="a1dc4-120">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="a1dc4-121">Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a1dc4-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

