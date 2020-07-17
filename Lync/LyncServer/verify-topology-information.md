---
title: Überprüfen der Topologieinformationen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4330d31b0cdaf10a3586324711aed98ab541b6eb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="e5a15-102">Überprüfen der Topologieinformationen</span><span class="sxs-lookup"><span data-stu-id="e5a15-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a15-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e5a15-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e5a15-104">Der erste Schritt bei der Überprüfung der erfolgreichen Zusammenführung besteht darin, die Informationen Office Communications Server 2007 R2 Topologie anzuzeigen, die Sie mit lync Server 2013 zusammengeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e5a15-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="e5a15-105">Im Topologie-Generator zeigt der Knoten **BackCompatSite** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aller Office Communications Server 2007 R2 Pools und Server an, die Sie zusammengeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e5a15-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="e5a15-106">So zeigen Sie den Knoten "BackCompatSite" im Topologie-Generator an</span><span class="sxs-lookup"><span data-stu-id="e5a15-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="e5a15-107">Öffnen Sie in Ihrer Office Communications Server 2007 R2 Umgebung das Verwaltungstool Office Communications Server 2007 R2, und notieren Sie sich die FQDNs der Legacy Pools und-Server.</span><span class="sxs-lookup"><span data-stu-id="e5a15-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="e5a15-108">Öffnen Sie in ihrer lync Server 2013 Umgebung den Topologie-Generator, und erweitern Sie dann den Knoten **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="e5a15-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="e5a15-109">Stellen Sie sicher, dass die FQDNs für die zusammenzuführenden Pools und Server angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e5a15-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5a15-110">Unter <STRONG>BackCompatSite</STRONG> werden keine Informationen für Serverrollen angezeigt, die mit einem Front-End-Server oder Standard Edition-Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e5a15-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="e5a15-111">Es werden nur Serverrollen angezeigt, die für die Interoperabilität zwischen Office Communications Server 2007 R2 und lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e5a15-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="e5a15-112">![Dialogfeld "Topologie-Generator BackCompatSite"](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Dialogfeld "Topologie-Generator BackCompatSite"")</span><span class="sxs-lookup"><span data-stu-id="e5a15-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="e5a15-113">Sie können auch lync Server 2013-Systemsteuerung verwenden, um die zusammengeführte Topologie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5a15-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="e5a15-114">In lync Server 2013 Systemsteuerung werden die einzelnen Server-FQDN, der Pool-FQDN und der Websitename für die zusammengeführte Topologie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5a15-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="e5a15-115">Zusammengeführte Server haben den **Standort**namen **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="e5a15-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="e5a15-116">So zeigen Sie die zusammengeführte Topologie in lync Server 2013 Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="e5a15-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e5a15-117">Öffnen Sie lync Server 2013 Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="e5a15-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="e5a15-118">Klicken Sie auf **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="e5a15-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="e5a15-119">Stellen Sie auf der Registerkarte **Status** sicher, dass die zusammengeführten Pools und Server angezeigt werden, indem Sie in der Spalte **Standort** nach **BackCompatSite** suchen.</span><span class="sxs-lookup"><span data-stu-id="e5a15-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="e5a15-120">![Lync Server-Systemsteuerung anzeigen der zusammengeführten Topologie](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server-Systemsteuerung anzeigen der zusammengeführten Topologie")</span><span class="sxs-lookup"><span data-stu-id="e5a15-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="e5a15-121">Wenn Sie weitere Einzelheiten zu einem zusammengeführten Pool anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPool**.</span><span class="sxs-lookup"><span data-stu-id="e5a15-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="e5a15-122">Zusätzlich zu den Informationen, die im Topologie-Generator und in lync Server 2013 Systemsteuerung zur Verfügung stehen, zeigt dieses Cmdlet die Dienste an, die im lync Server 2013-Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5a15-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5a15-123">Wenn Sie die Topologie nach dem Ausführen des Merge-Assistenten im Topologie-Generator veröffentlichen, werden die Konferenzverzeichnisse mit lync Server 2013 zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e5a15-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="e5a15-124">Konferenzverzeichnisse können Sie überprüfen, indem Sie das Cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5a15-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="e5a15-125">So zeigen Sie Dienste in einem zusammengeführten Pool an</span><span class="sxs-lookup"><span data-stu-id="e5a15-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="e5a15-126">Öffnen Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="e5a15-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e5a15-127">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5a15-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="e5a15-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5a15-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="e5a15-129">So überprüfen Sie zusammengeführte Konferenzverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="e5a15-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="e5a15-130">Öffnen Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="e5a15-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e5a15-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5a15-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="e5a15-132">Stellen Sie sicher, dass sich alle Konferenzverzeichnisse für den Pool oder Server, den Sie zusammenführen, jetzt in lync Server 2013 befinden.</span><span class="sxs-lookup"><span data-stu-id="e5a15-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

