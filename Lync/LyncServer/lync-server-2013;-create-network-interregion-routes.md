---
title: Lync Server 2013; Erstellen von Netzwerk interregions-Routen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 9d234d959f434e9e2b96850add488ecd4eac952c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="22ec7-102">Erstellen von Netzwerk interregions-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22ec7-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22ec7-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="22ec7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="22ec7-104">Eine *Netzwerk-interregions-Route* definiert die Route zwischen zwei netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="22ec7-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="22ec7-105">Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk-interregions-Route erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22ec7-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="22ec7-106">So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="22ec7-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="22ec7-107">Während die Region Links Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegt, bestimmt eine interregions Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einem anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="22ec7-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="22ec7-108">Details zum Arbeiten mit Netzwerk interregions-Routen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="22ec7-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="22ec7-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22ec7-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="22ec7-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22ec7-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="22ec7-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22ec7-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="22ec7-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="22ec7-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="22ec7-113">In der Beispieltopologie müssen Netzwerk interregions-Routen für jedes der drei Regions Paare definiert werden: Nordamerika/EMEA, EMEA/APAC und Nordamerika/APAC.</span><span class="sxs-lookup"><span data-stu-id="22ec7-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="22ec7-114">So erstellen Sie Netzwerk interregions-Routen mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="22ec7-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="22ec7-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="22ec7-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="22ec7-116">Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="22ec7-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="22ec7-117">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="22ec7-117">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="22ec7-118">Für die Route Nordamerika/APAC-Netzwerk Interregion sind zwei Netzwerk Regions Verknüpfungen erforderlich, da zwischen Ihnen keine direkte Netzwerk Regions Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="22ec7-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="22ec7-119">So erstellen Sie Netzwerk interregions-Routen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="22ec7-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="22ec7-120">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="22ec7-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22ec7-121">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22ec7-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="22ec7-122">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="22ec7-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="22ec7-123">Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="22ec7-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="22ec7-124">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="22ec7-124">Click **New**.</span></span>

5.  <span data-ttu-id="22ec7-125">Klicken Sie auf der Seite **neue Regions Route** auf **Name** , und geben Sie dann einen Namen für die Route des Netzwerk interregions ein.</span><span class="sxs-lookup"><span data-stu-id="22ec7-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="22ec7-126">Klicken Sie auf **netzwerkregion \#1**, und klicken Sie dann in der Liste auf einen Netzwerkbereich, den Sie an \#netzwerkregion 2 weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="22ec7-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="22ec7-127">Klicken Sie auf **netzwerkregion \#2**, und klicken Sie dann in der Liste auf einen Netzwerkbereich, den Sie an \#netzwerkregion 1 weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="22ec7-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="22ec7-128">Klicken Sie neben dem Feld **Netzwerk Regions Verknüpfungen** auf **Hinzufügen** , und fügen Sie dann einen Netzwerk Regions Link hinzu, der in der Netzwerk interregions-Route verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22ec7-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="22ec7-129">Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="22ec7-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="22ec7-130">Beispielsweise erfordert die Route Nordamerika/APAC-Netzwerk Interregion zwei Netzwerk Regions Verknüpfungen, da zwischen Ihnen keine direkte Netzwerk Regions Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="22ec7-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="22ec7-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="22ec7-131">Click **Commit**.</span></span>

10. <span data-ttu-id="22ec7-132">Um das Erstellen von Netzwerk interregions-Routen für Ihre Topologie abzuschließen, wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Netzwerk interregions-Routen.</span><span class="sxs-lookup"><span data-stu-id="22ec7-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

