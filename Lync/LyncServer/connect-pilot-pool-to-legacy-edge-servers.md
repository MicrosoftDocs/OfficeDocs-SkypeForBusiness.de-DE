---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
description: Verbinden Sie den Pilot Pool mit Legacy-Edge-Servern.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550271"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="ef5b5-103">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="ef5b5-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef5b5-104">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="ef5b5-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="ef5b5-105">Nach der Bereitstellung lync Server 2013 müssen Sie eine partnerverbundroute für Ihre Website konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="ef5b5-106">Um die von lync Server 2010 verwendete Verbund Route verwenden zu können, müssen lync Server 2013 für die Verwendung dieser Route konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="ef5b5-107">Damit die lync Server 2013 Website den Director und Edgeserver der lync Server 2010-Bereitstellung verwenden kann, ordnen Sie die Legacy-Edgepool mithilfe des Topologie-Generators zu.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="ef5b5-108">So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu</span><span class="sxs-lookup"><span data-stu-id="ef5b5-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="ef5b5-109">Öffnen Sie den **Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="ef5b5-110">Wählen Sie Ihren Standort aus, der sich direkt unterhalb des **Lync Server**-Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="ef5b5-111">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="ef5b5-112">Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="ef5b5-113">Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann den lync Server 2010 Director oder den lync Server 2010 Edgeserver, wenn kein Director aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="ef5b5-114">![Eigenschaften bearbeiten, Verbund Route (Seite)](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Eigenschaften bearbeiten, Verbund Route (Seite)")</span><span class="sxs-lookup"><span data-stu-id="ef5b5-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="ef5b5-115">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="ef5b5-116">Navigieren Sie im Topologie-Generator unter dem Knoten lync Server 2013 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="ef5b5-117">Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="ef5b5-118">Wählen Sie in der Liste den Edgeserver der Vorversion aus.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="ef5b5-119">![Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges")</span><span class="sxs-lookup"><span data-stu-id="ef5b5-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="ef5b5-120">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="ef5b5-121">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten aus, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="ef5b5-122">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="ef5b5-123">Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ef5b5-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

