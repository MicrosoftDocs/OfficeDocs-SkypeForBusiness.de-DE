---
title: 'Lync Server 2013: Bereitstellen von netzwerkregionen, Standorten und Subnetzen'
description: 'Lync Server 2013: Bereitstellen von netzwerkregionen, Standorten und Subnetzen.'
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
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561091"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="1d409-103">Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d409-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d409-104">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="1d409-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="1d409-105">Nachdem Enterprise-VoIP bereitgestellt wurde, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1d409-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="1d409-106">Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="1d409-106">Network regions</span></span>

  - <span data-ttu-id="1d409-107">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="1d409-107">Network sites</span></span>

  - <span data-ttu-id="1d409-108">Netzwerksubnetze</span><span class="sxs-lookup"><span data-stu-id="1d409-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="1d409-109">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="1d409-109">Define Network Regions</span></span>

<span data-ttu-id="1d409-110">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkRegion oder lync Server-Systemsteuerung, um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1d409-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="1d409-111">Weitere Informationen finden Sie unter [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="1d409-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="1d409-112">In diesem Beispiel veranschaulicht der folgende Windows PowerShell Befehl die netzwerkregion, Region 1 (Indien), die in diesem Szenario definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1d409-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="1d409-113">Definieren von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="1d409-113">Define Network Sites</span></span>

<span data-ttu-id="1d409-114">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSite oder lync Server-Systemsteuerung, um Netzwerkstandorte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1d409-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="1d409-115">Weitere Informationen finden Sie unter [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="1d409-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="1d409-116">In diesem Beispiel veranschaulichen die folgenden Tabellen und lync Server Windows PowerShell Befehls die in diesem Szenario definierten Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="1d409-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="1d409-117">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="1d409-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="1d409-118">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1d409-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="1d409-119">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1d409-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d409-120">Website-ID</span><span class="sxs-lookup"><span data-stu-id="1d409-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="1d409-121">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1d409-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="1d409-122">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1d409-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d409-123">Regions-ID</span><span class="sxs-lookup"><span data-stu-id="1d409-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="1d409-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="1d409-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="1d409-125">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="1d409-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="1d409-126">Definieren von Netzwerk Subnetzen</span><span class="sxs-lookup"><span data-stu-id="1d409-126">Define Network Subnets</span></span>

<span data-ttu-id="1d409-127">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSubnet oder lync Server-Systemsteuerung, um Netzwerksubnetze zu definieren und Sie Netzwerkstandorten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d409-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="1d409-128">Weitere Informationen finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="1d409-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="1d409-129">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell Befehle die Zuweisung von Netzwerk Subnetzen zu den in diesem Szenario definierten Netzwerkstandorten Delhi und Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1d409-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="1d409-130">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="1d409-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="1d409-131">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1d409-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="1d409-132">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1d409-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d409-133">Subnetz-ID</span><span class="sxs-lookup"><span data-stu-id="1d409-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="1d409-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="1d409-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="1d409-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="1d409-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d409-136">Maske</span><span class="sxs-lookup"><span data-stu-id="1d409-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="1d409-137">24</span><span class="sxs-lookup"><span data-stu-id="1d409-137">24</span></span></p></td>
<td><p><span data-ttu-id="1d409-138">24</span><span class="sxs-lookup"><span data-stu-id="1d409-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d409-139">Website-ID</span><span class="sxs-lookup"><span data-stu-id="1d409-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="1d409-140">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1d409-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="1d409-141">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1d409-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d409-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d409-142">See Also</span></span>


[<span data-ttu-id="1d409-143">Konfigurieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d409-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

