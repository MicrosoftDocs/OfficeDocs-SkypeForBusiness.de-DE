---
title: Verbinden des pilotpools mit Legacy-Edge-Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eea7d203638e891dbda1b91c53967a4632cc1df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8b2a3-102">Verbinden des pilotpools mit Legacy-Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="8b2a3-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b2a3-103">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8b2a3-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8b2a3-104">Nach der Bereitstellung lync Server 2013 müssen Sie eine partnerverbundroute für Ihre Website konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="8b2a3-105">Um die von lync Server 2010 verwendete Verbund Route verwenden zu können, müssen lync Server 2013 für die Verwendung dieser Route konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="8b2a3-106">Damit die lync Server 2013 Website den Director und Edgeserver der lync Server 2010-Bereitstellung verwenden kann, ordnen Sie die Legacy-Edgepool mithilfe des Topologie-Generators zu.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8b2a3-107">So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="8b2a3-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="8b2a3-108">Öffnen Sie den **Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="8b2a3-109">Wählen Sie Ihren Standort aus, der sich direkt unterhalb des **Lync Server**-Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="8b2a3-110">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8b2a3-111">Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="8b2a3-112">Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann den lync Server 2010 Director oder den lync Server 2010 Edgeserver, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="8b2a3-113">![Eigenschaften bearbeiten, Verbund Route (Seite)](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Eigenschaften bearbeiten, Verbund Route (Seite)")</span><span class="sxs-lookup"><span data-stu-id="8b2a3-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="8b2a3-114">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="8b2a3-115">Navigieren Sie im Topologie-Generator unter dem Knoten lync Server 2013 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="8b2a3-116">Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="8b2a3-117">Wählen Sie in der Liste den Edgeserver der Vorversion aus.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="8b2a3-118">![Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges")</span><span class="sxs-lookup"><span data-stu-id="8b2a3-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="8b2a3-119">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="8b2a3-120">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten aus, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="8b2a3-121">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="8b2a3-122">Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="8b2a3-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

