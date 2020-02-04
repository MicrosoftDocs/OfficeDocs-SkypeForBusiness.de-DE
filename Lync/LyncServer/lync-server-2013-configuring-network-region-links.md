---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Regions Verknüpfungen'
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
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="99ff4-102">Konfigurieren von Netzwerkbereichs Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99ff4-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99ff4-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="99ff4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="99ff4-104">Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="99ff4-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="99ff4-105">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="99ff4-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="99ff4-106">Sie können die lync Server-Systemsteuerung verwenden, um eine Verknüpfung zwischen zwei netzwerkregionen zu definieren und die Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen Regionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="99ff4-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="99ff4-107">Details zum Löschen einer vorhandenen Netzwerk Regions Verknüpfung finden Sie unter [Löschen von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="99ff4-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="99ff4-108">So erstellen Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="99ff4-108">To create a network region link</span></span>

1.  <span data-ttu-id="99ff4-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="99ff4-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99ff4-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="99ff4-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99ff4-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99ff4-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99ff4-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="99ff4-113">Klicken Sie auf der Seite **Regions Link** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="99ff4-114">Geben Sie im Feld **neuer Bereich**einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="99ff4-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99ff4-115">Dieser Wert muss innerhalb ihrer lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="99ff4-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="99ff4-116">Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden zu verknüpfende Regionen aus.</span><span class="sxs-lookup"><span data-stu-id="99ff4-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="99ff4-117">Wählen Sie in der Dropdownliste **netzwerkregion \#2** die andere Region aus, die verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="99ff4-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="99ff4-118">Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="99ff4-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="99ff4-119">Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie in der Dropdownliste **bandbreitenrichtlinie** ein Profil für Bandbreitenrichtlinien aus.</span><span class="sxs-lookup"><span data-stu-id="99ff4-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="99ff4-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="99ff4-121">So ändern Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="99ff4-121">To modify a network region link</span></span>

1.  <span data-ttu-id="99ff4-122">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="99ff4-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99ff4-123">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="99ff4-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99ff4-124">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99ff4-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99ff4-125">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="99ff4-126">Klicken Sie auf der Seite **Regions Link** auf den zu ändernden Bereichs Link.</span><span class="sxs-lookup"><span data-stu-id="99ff4-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="99ff4-127">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="99ff4-128">Im **Link "Region bearbeiten**" können Sie die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diesen Link ändern.</span><span class="sxs-lookup"><span data-stu-id="99ff4-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="99ff4-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="99ff4-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99ff4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99ff4-130">See Also</span></span>


[<span data-ttu-id="99ff4-131">Löschen von Netzwerkbereichs Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99ff4-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="99ff4-132">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="99ff4-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="99ff4-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="99ff4-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="99ff4-134">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="99ff4-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="99ff4-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="99ff4-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
