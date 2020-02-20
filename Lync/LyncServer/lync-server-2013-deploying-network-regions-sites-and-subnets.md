---
title: 'Lync Server 2013: Bereitstellen von netzwerkregionen, Standorten und Subnetzen'
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
ms.openlocfilehash: eb1409213e2ba40936743e604af79d1fe564530c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="4bb1c-102">Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb1c-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bb1c-103">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="4bb1c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="4bb1c-104">Nachdem Enterprise-VoIP bereitgestellt wurde, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4bb1c-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="4bb1c-105">Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="4bb1c-105">Network regions</span></span>

  - <span data-ttu-id="4bb1c-106">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="4bb1c-106">Network sites</span></span>

  - <span data-ttu-id="4bb1c-107">Netzwerksubnetze</span><span class="sxs-lookup"><span data-stu-id="4bb1c-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="4bb1c-108">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="4bb1c-108">Define Network Regions</span></span>

<span data-ttu-id="4bb1c-109">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkRegion oder lync Server-Systemsteuerung, um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="4bb1c-110">Weitere Informationen finden Sie unter [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="4bb1c-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="4bb1c-111">In diesem Beispiel veranschaulicht der folgende Windows PowerShell Befehl die netzwerkregion, Region 1 (Indien), die in diesem Szenario definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="4bb1c-112">Definieren von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="4bb1c-112">Define Network Sites</span></span>

<span data-ttu-id="4bb1c-113">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSite oder lync Server-Systemsteuerung, um Netzwerkstandorte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="4bb1c-114">Weitere Informationen finden Sie unter [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="4bb1c-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="4bb1c-115">In diesem Beispiel veranschaulichen die folgenden Tabellen und lync Server Windows PowerShell Befehls die in diesem Szenario definierten Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="4bb1c-116">Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="4bb1c-117">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="4bb1c-118">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bb1c-119">Website-ID</span><span class="sxs-lookup"><span data-stu-id="4bb1c-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-120">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-121">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bb1c-122">Regions-ID</span><span class="sxs-lookup"><span data-stu-id="4bb1c-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-123">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="4bb1c-125">Definieren von Netzwerk Subnetzen</span><span class="sxs-lookup"><span data-stu-id="4bb1c-125">Define Network Subnets</span></span>

<span data-ttu-id="4bb1c-126">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSubnet oder lync Server-Systemsteuerung, um Netzwerksubnetze zu definieren und Sie Netzwerkstandorten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="4bb1c-127">Weitere Informationen finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="4bb1c-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="4bb1c-128">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell Befehle die Zuweisung von Netzwerk Subnetzen zu den in diesem Szenario definierten Netzwerkstandorten Delhi und Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="4bb1c-129">Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4bb1c-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="4bb1c-130">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="4bb1c-131">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bb1c-132">Subnetz-ID</span><span class="sxs-lookup"><span data-stu-id="4bb1c-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="4bb1c-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="4bb1c-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bb1c-135">Maske</span><span class="sxs-lookup"><span data-stu-id="4bb1c-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-136">24</span><span class="sxs-lookup"><span data-stu-id="4bb1c-136">24</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-137">24</span><span class="sxs-lookup"><span data-stu-id="4bb1c-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bb1c-138">Website-ID</span><span class="sxs-lookup"><span data-stu-id="4bb1c-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-139">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="4bb1c-140">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="4bb1c-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bb1c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bb1c-141">See Also</span></span>


[<span data-ttu-id="4bb1c-142">Konfigurieren des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb1c-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

