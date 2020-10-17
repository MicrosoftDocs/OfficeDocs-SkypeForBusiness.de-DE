---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Regions Links'
description: 'Lync Server 2013: Konfigurieren von Netzwerk Regions Links.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547011"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="6dd0a-103">Konfigurieren von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd0a-103">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd0a-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6dd0a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6dd0a-105">Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="6dd0a-106">Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="6dd0a-107">Sie können die lync Server-Systemsteuerung verwenden, um eine Verknüpfung zwischen zwei netzwerkregionen zu definieren und die Bandbreitenbeschränkungen für Audio-und Videoverbindungen zwischen diesen Regionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-107">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="6dd0a-108">Ausführliche Informationen zum Löschen einer vorhandenen Netzwerk Regions Verbindung finden Sie unter [Löschen von Netzwerk Regions Links in lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="6dd0a-108">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="6dd0a-109">So erstellen Sie eine Netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="6dd0a-109">To create a network region link</span></span>

1.  <span data-ttu-id="6dd0a-110">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6dd0a-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6dd0a-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6dd0a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6dd0a-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="6dd0a-114">Klicken Sie auf der Seite **Regionenverbindung** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-114">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="6dd0a-115">Geben Sie im Abschnitt **Neue Regionenverbindung** im Feld **Name** einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-115">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6dd0a-116">Dieser Wert muss innerhalb ihrer lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-116">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="6dd0a-117">Wählen Sie in der Dropdownliste **netzwerkregion \# 1** eine der beiden Regionen aus, die verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-117">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="6dd0a-118">Wählen Sie in der Dropdownliste **netzwerkregion \# 2** den anderen zu verknüpfenden Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-118">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="6dd0a-119">Diese Region muss sich von der für die netzwerkregion 1 ausgewählten Region unterscheiden \# .</span><span class="sxs-lookup"><span data-stu-id="6dd0a-119">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="6dd0a-120">(Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie ein Bandbreitenrichtlinienprofil in der Dropdownliste **Bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-120">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="6dd0a-121">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="6dd0a-122">So ändern Sie eine Netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="6dd0a-122">To modify a network region link</span></span>

1.  <span data-ttu-id="6dd0a-123">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6dd0a-124">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6dd0a-125">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6dd0a-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6dd0a-126">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-126">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="6dd0a-127">Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-127">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="6dd0a-128">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-128">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6dd0a-129">Im Abschnitt **Regionenverbindung bearbeiten** können Sie die verknüpften Regionen oder das Bandbreitenrichtlinienprofil für diese Region ändern.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-129">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="6dd0a-130">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="6dd0a-130">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6dd0a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dd0a-131">See Also</span></span>


[<span data-ttu-id="6dd0a-132">Löschen von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd0a-132">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="6dd0a-133">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="6dd0a-133">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="6dd0a-134">Gruppe-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="6dd0a-134">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="6dd0a-135">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="6dd0a-135">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="6dd0a-136">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="6dd0a-136">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
