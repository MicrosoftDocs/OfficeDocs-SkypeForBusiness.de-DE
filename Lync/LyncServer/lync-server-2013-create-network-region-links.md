---
title: 'Lync Server 2013: Erstellen von Netzwerk Regions Links'
description: 'Lync Server 2013: Erstellen von Netzwerk Regions Links.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6510d252ac1534a3a8e9f14d56acc8d0d8b60a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553935"
---
# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="9b5c4-103">Erstellen von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b5c4-103">Create network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b5c4-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9b5c4-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9b5c4-105">Regionen in einem Netzwerk sind über eine physische WAN-Verbindung verbunden.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="9b5c4-106">Eine *Netzwerk Regions Verbindung* erstellt eine Verknüpfung zwischen zwei Regionen, die für die Anrufsteuerung konfiguriert sind, und legt die Bandbreitenbeschränkungen für den Audio-und Videodatenverkehr zwischen diesen Regionen fest.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-106">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="9b5c4-107">Ausführliche Informationen zum Arbeiten mit Netzwerk Regions Verknüpfungen finden Sie in der lync Server-Verwaltungsshell Dokumentation zu den folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9b5c4-107">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9b5c4-108">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b5c4-108">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="9b5c4-109">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b5c4-109">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="9b5c4-110">Gruppe-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b5c4-110">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="9b5c4-111">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b5c4-111">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="9b5c4-112">Die Beispieltopologie hat eine Verbindung zwischen den Regionen Nordamerika und APAC sowie eine Verbindung zwischen den Regionen EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-112">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="9b5c4-113">Jede dieser Regions Verknüpfungen wird durch die WAN-Bandbreite eingeschränkt, wie in der Tabelle "Bereichs Link-bandbreiteninformationen" im [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) Abschnitt der Planungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-113">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="9b5c4-114">So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe von lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9b5c4-114">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="9b5c4-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9b5c4-116">Führen Sie das New-CsNetworkRegionLink-Cmdlet aus, um die Regions Verknüpfungen zu erstellen und entsprechende bandbreitenrichtlinienprofile anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-116">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="9b5c4-117">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9b5c4-117">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="9b5c4-118">So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="9b5c4-118">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9b5c4-119">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b5c4-120">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b5c4-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9b5c4-121">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-121">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9b5c4-122">Klicken Sie auf die Navigationsschaltfläche **Regions Verknüpfung** .</span><span class="sxs-lookup"><span data-stu-id="9b5c4-122">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="9b5c4-123">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-123">Click **New**.</span></span>

5.  <span data-ttu-id="9b5c4-124">Klicken Sie auf der Seite **neue Regions Verknüpfung** auf **Name** , und geben Sie dann einen Namen für die Netzwerk Regions Verknüpfung ein.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-124">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="9b5c4-125">Klicken Sie auf **netzwerkregion \# 1**, und klicken Sie dann auf die netzwerkregion in der Liste, die Sie mit der netzwerkregion 2 verknüpfen möchten \# .</span><span class="sxs-lookup"><span data-stu-id="9b5c4-125">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="9b5c4-126">Klicken Sie auf **netzwerkregion \# 2**, und klicken Sie dann auf eine netzwerkregion in der Liste, die Sie mit der netzwerkregion 1 verknüpfen möchten \# .</span><span class="sxs-lookup"><span data-stu-id="9b5c4-126">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="9b5c4-127">Klicken Sie optional auf **bandbreitenrichtlinie**, und wählen Sie dann das bandbreitenrichtlinienprofil aus, das Sie auf den Link netzwerkregion anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-127">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9b5c4-128">Wenden Sie nur dann eine bandbreitenrichtlinie an, wenn die Netzwerk Regions Verbindung Bandbreiteneinschränkungen unterliegt und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-128">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="9b5c4-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-129">Click **Commit**.</span></span>

10. <span data-ttu-id="9b5c4-130">Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Regionen, um die Erstellung von Netzwerk Regions Verknüpfungen für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-130">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
