---
title: 'Lync Server 2013: Bereitstellen von netzwerkregionen,-Websites und-Subnetzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e848a-102">Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e848a-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e848a-103">_**Letztes Änderungsdatum des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e848a-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e848a-104">Nachdem Enterprise-VoIP bereitgestellt wurde, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e848a-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="e848a-105">Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="e848a-105">Network regions</span></span>

  - <span data-ttu-id="e848a-106">Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="e848a-106">Network sites</span></span>

  - <span data-ttu-id="e848a-107">Netzwerk-Subnetze</span><span class="sxs-lookup"><span data-stu-id="e848a-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="e848a-108">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="e848a-108">Define Network Regions</span></span>

<span data-ttu-id="e848a-109">Verwenden Sie den lync Server Windows PowerShell-Befehl, die CsNetworkRegion-oder lync Server-Systemsteuerung, um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e848a-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="e848a-110">Weitere Informationen finden Sie unter [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="e848a-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="e848a-111">In diesem Beispiel wird mit dem folgenden Windows PowerShell-Befehl die in diesem Szenario definierte netzwerkregion, Region 1 (Indien), veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e848a-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="e848a-112">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="e848a-112">Define Network Sites</span></span>

<span data-ttu-id="e848a-113">Verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsNetworkSite oder die lync Server-Systemsteuerung, um Netzwerk Websites zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e848a-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="e848a-114">Weitere Informationen finden Sie unter [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="e848a-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="e848a-115">In diesem Beispiel veranschaulichen die folgende Tabelle und der lync Server-Windows PowerShell-Befehl die in diesem Szenario definierten Netzwerk Websites.</span><span class="sxs-lookup"><span data-stu-id="e848a-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="e848a-116">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="e848a-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e848a-117">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e848a-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e848a-118">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e848a-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e848a-119">Website-ID</span><span class="sxs-lookup"><span data-stu-id="e848a-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e848a-120">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e848a-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e848a-121">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e848a-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e848a-122">Regions-ID</span><span class="sxs-lookup"><span data-stu-id="e848a-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="e848a-123">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="e848a-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="e848a-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="e848a-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="e848a-125">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="e848a-125">Define Network Subnets</span></span>

<span data-ttu-id="e848a-126">Verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsNetworkSubnet oder die lync Server-Systemsteuerung, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e848a-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="e848a-127">Weitere Informationen finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="e848a-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="e848a-128">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell-Befehle die Zuweisung von Netzwerk-Subnetzen zu den Netzwerkstandorten Delhi und Hyderabad, die in diesem Szenario definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e848a-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="e848a-129">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="e848a-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e848a-130">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e848a-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e848a-131">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e848a-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e848a-132">Subnet-ID</span><span class="sxs-lookup"><span data-stu-id="e848a-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="e848a-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="e848a-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="e848a-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e848a-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e848a-135">Format</span><span class="sxs-lookup"><span data-stu-id="e848a-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="e848a-136">24</span><span class="sxs-lookup"><span data-stu-id="e848a-136">24</span></span></p></td>
<td><p><span data-ttu-id="e848a-137">24</span><span class="sxs-lookup"><span data-stu-id="e848a-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e848a-138">Website-ID</span><span class="sxs-lookup"><span data-stu-id="e848a-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e848a-139">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e848a-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e848a-140">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e848a-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e848a-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e848a-141">See Also</span></span>


[<span data-ttu-id="e848a-142">Konfigurieren von standortbasiertem Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e848a-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

