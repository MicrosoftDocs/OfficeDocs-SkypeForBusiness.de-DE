---
title: Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Erstellen und Einrichten von netzwerkregionen, Standorten und Subnetzen für standortbasierte Routing zum direkten weiterleiten.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b818b10a333fbb7cf50cf4e49d521aa224e2d17
ms.sourcegitcommit: b53d99d06178c26297d1349ff82d05f706dfb479
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30050764"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="6f42e-103">Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="6f42e-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="6f42e-104">Wenn Sie noch nicht haben lesen [Plan Location-Based Routing für das direkte Routing getan](location-based-routing-plan.md) , um weitere Schritte anzuzeigen müssen Sie vor der Bereitstellung von Netzwerkeinstellungen für standortbasierte Routing übernehmen.</span><span class="sxs-lookup"><span data-stu-id="6f42e-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you deploy network settings for Location-Based Routing.</span></span>

<span data-ttu-id="6f42e-105">In diesem Artikel wird beschrieben, wie Netzwerk für standortbasierte Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6f42e-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="6f42e-106">Nach der Bereitstellung von Telefon System direkten Routing in Ihrer Organisation sind die nächsten Schritte zum Erstellen und Einrichten von netzwerkregionen, Netzwerkstandorten und Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="6f42e-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="6f42e-107">Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige gute Kenntnisse im Umgang mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6f42e-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="6f42e-108">Weitere Informationen finden Sie unter [Teams PowerShell (Übersicht)](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6f42e-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="6f42e-109">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="6f42e-109">Define network regions</span></span>
 <span data-ttu-id="6f42e-110">Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche.</span><span class="sxs-lookup"><span data-stu-id="6f42e-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6f42e-111">Verwendung der ``New-CsTenantNetworkRegion`` PowerShell-Cmdlet, um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6f42e-111">Use the ``New-CsTenantNetworkRegion`` PowerShell cmdlet to define network regions.</span></span> <span data-ttu-id="6f42e-112">Beachten Sie, dass die ``RegionID`` Parameter ist ein logischer Name, der die Region des Bereichs darstellt und hat keine Abhängigkeiten oder Einschränkungen und der ``CentralSite <site ID>`` Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6f42e-112">Note that the ``RegionID`` parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the ``CentralSite <site ID>`` parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="6f42e-113">In diesem Beispiel erstellen wir eine netzwerkregion, die mit dem Namen Indien.</span><span class="sxs-lookup"><span data-stu-id="6f42e-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="6f42e-114">Definieren von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="6f42e-114">Define network sites</span></span>

<span data-ttu-id="6f42e-115">Verwendung der ``New-CsTenantNetworkSite`` PowerShell-Cmdlet, um Netzwerkstandorte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6f42e-115">Use the ``New-CsTenantNetworkSite`` PowerShell cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="6f42e-116">In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte Delhi und Hyderabad, in dem Bereich Indien.</span><span class="sxs-lookup"><span data-stu-id="6f42e-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="6f42e-117">Die folgende Tabelle zeigt der Netzwerkstandorte, die in diesem Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="6f42e-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="6f42e-118">Standort 1</span><span class="sxs-lookup"><span data-stu-id="6f42e-118">Site 1</span></span> |<span data-ttu-id="6f42e-119">Standort 2</span><span class="sxs-lookup"><span data-stu-id="6f42e-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6f42e-120">Site-ID</span><span class="sxs-lookup"><span data-stu-id="6f42e-120">Site ID</span></span>    |    <span data-ttu-id="6f42e-121">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6f42e-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="6f42e-122">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6f42e-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="6f42e-123">Bereichs-ID</span><span class="sxs-lookup"><span data-stu-id="6f42e-123">Region ID</span></span>  |     <span data-ttu-id="6f42e-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="6f42e-124">Region 1 (India)</span></span>    |   <span data-ttu-id="6f42e-125">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="6f42e-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="6f42e-126">Definieren von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="6f42e-126">Define network subnets</span></span>

<span data-ttu-id="6f42e-127">Verwendung der ``New-CsTenantNetworkSubnet`` -Cmdlet zum Definieren von Netzwerksubnetzen und verknüpfen Sie diese mit Netzwerkstandorten.</span><span class="sxs-lookup"><span data-stu-id="6f42e-127">Use the ``New-CsTenantNetworkSubnet`` cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="6f42e-128">Jeder internen Subnetz kann nur einem einzigen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6f42e-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="6f42e-129">In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz 192.168.0.0 und dem Netzwerkstandort Delhi und zwischen Subnetz 192.168.1.0 und dem Netzwerkstandort Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="6f42e-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="6f42e-130">Die folgende Tabelle zeigt die Subnetze in diesem Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="6f42e-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="6f42e-131">Standort 1</span><span class="sxs-lookup"><span data-stu-id="6f42e-131">Site 1</span></span> |<span data-ttu-id="6f42e-132">Standort 2</span><span class="sxs-lookup"><span data-stu-id="6f42e-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6f42e-133">Subnetz-ID</span><span class="sxs-lookup"><span data-stu-id="6f42e-133">Subnet ID</span></span>   |    <span data-ttu-id="6f42e-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="6f42e-134">192.168.0.0</span></span>     |  <span data-ttu-id="6f42e-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="6f42e-135">192.168.1.0</span></span>     |
|<span data-ttu-id="6f42e-136">Maske</span><span class="sxs-lookup"><span data-stu-id="6f42e-136">Mask</span></span>  |     <span data-ttu-id="6f42e-137">24</span><span class="sxs-lookup"><span data-stu-id="6f42e-137">24</span></span>    |   <span data-ttu-id="6f42e-138">24</span><span class="sxs-lookup"><span data-stu-id="6f42e-138">24</span></span>      |
|<span data-ttu-id="6f42e-139">Site-ID</span><span class="sxs-lookup"><span data-stu-id="6f42e-139">Site ID</span></span>  | <span data-ttu-id="6f42e-140">Website (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6f42e-140">Site (Delhi)</span></span> | <span data-ttu-id="6f42e-141">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6f42e-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="6f42e-142">Für mehrere Subnetze können Sie eine CSV-Datei mithilfe eines Skripts wie die folgenden importieren.</span><span class="sxs-lookup"><span data-stu-id="6f42e-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="6f42e-143">In diesem Beispiel sieht die CSV-Datei etwa so aussehen:</span><span class="sxs-lookup"><span data-stu-id="6f42e-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="6f42e-144">Definieren der externen Subnetze</span><span class="sxs-lookup"><span data-stu-id="6f42e-144">Define external subnets</span></span>
<span data-ttu-id="6f42e-145">Verwendung der ``New-CsTenantTrustedIPAddress`` -Cmdlet zum Definieren von externen Subnetze und weisen Sie diese den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6f42e-145">Use the ``New-CsTenantTrustedIPAddress`` cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="6f42e-146">Sie können eine unbegrenzte Anzahl von Subnetzen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="6f42e-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="6f42e-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f42e-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="6f42e-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6f42e-148">Next steps</span></span>
<span data-ttu-id="6f42e-149">Wechseln Sie zur [speicherortbasierte Routing für die direkte Weiterleitung aktivieren](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6f42e-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="6f42e-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6f42e-150">Related topics</span></span>
- [<span data-ttu-id="6f42e-151">Planen des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="6f42e-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="6f42e-152">Terminologie für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="6f42e-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
