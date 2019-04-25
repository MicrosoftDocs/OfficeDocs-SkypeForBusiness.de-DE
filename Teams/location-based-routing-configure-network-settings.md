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
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222363"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="2c4a1-103">Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="2c4a1-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="2c4a1-104">Wenn Sie noch nicht haben lesen [Plan Location-Based Routing für das direkte Routing getan](location-based-routing-plan.md) , um weitere Schritte überprüfen müssen Sie ergreifen, bevor Sie Netzwerkeinstellungen für standortbasierte Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="2c4a1-105">In diesem Artikel wird beschrieben, wie Netzwerk für standortbasierte Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="2c4a1-106">Nach der Bereitstellung von Telefon System direkten Routing in Ihrer Organisation sind die nächsten Schritte zum Erstellen und Einrichten von netzwerkregionen, Netzwerkstandorten und Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="2c4a1-107">Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige gute Kenntnisse im Umgang mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2c4a1-108">Weitere Informationen finden Sie unter [Teams PowerShell (Übersicht)](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c4a1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="2c4a1-109">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="2c4a1-109">Define network regions</span></span>
 <span data-ttu-id="2c4a1-110">Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2c4a1-111">Verwenden Sie das Cmdlet " [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) ", um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="2c4a1-112">Beachten Sie, dass der Parameter RegionID ein logischer Name der Region des Bereichs darstellt und hat keine Abhängigkeiten oder Einschränkungen und der CentralSite &lt;site-ID&gt; Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="2c4a1-113">In diesem Beispiel erstellen wir eine netzwerkregion, die mit dem Namen Indien.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="2c4a1-114">Definieren von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="2c4a1-114">Define network sites</span></span>

<span data-ttu-id="2c4a1-115">Verwenden Sie das [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) -Cmdlet, um Netzwerkstandorte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="2c4a1-116">In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte Delhi und Hyderabad, in dem Bereich Indien.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="2c4a1-117">Die folgende Tabelle zeigt der Netzwerkstandorte, die in diesem Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="2c4a1-118">Standort 1</span><span class="sxs-lookup"><span data-stu-id="2c4a1-118">Site 1</span></span> |<span data-ttu-id="2c4a1-119">Standort 2</span><span class="sxs-lookup"><span data-stu-id="2c4a1-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2c4a1-120">Site-ID</span><span class="sxs-lookup"><span data-stu-id="2c4a1-120">Site ID</span></span>    |    <span data-ttu-id="2c4a1-121">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="2c4a1-122">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="2c4a1-123">Bereichs-ID</span><span class="sxs-lookup"><span data-stu-id="2c4a1-123">Region ID</span></span>  |     <span data-ttu-id="2c4a1-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-124">Region 1 (India)</span></span>    |   <span data-ttu-id="2c4a1-125">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="2c4a1-126">Definieren von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="2c4a1-126">Define network subnets</span></span>

<span data-ttu-id="2c4a1-127">Verwenden Sie das Cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) von Netzwerksubnetzen definieren und diese zu Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="2c4a1-128">Jeder internen Subnetz kann nur einem einzigen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="2c4a1-129">In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz 192.168.0.0 und dem Netzwerkstandort Delhi und zwischen Subnetz 192.168.1.0 und dem Netzwerkstandort Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="2c4a1-130">Die folgende Tabelle zeigt die Subnetze in diesem Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="2c4a1-131">Standort 1</span><span class="sxs-lookup"><span data-stu-id="2c4a1-131">Site 1</span></span> |<span data-ttu-id="2c4a1-132">Standort 2</span><span class="sxs-lookup"><span data-stu-id="2c4a1-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2c4a1-133">Subnetz-ID</span><span class="sxs-lookup"><span data-stu-id="2c4a1-133">Subnet ID</span></span>   |    <span data-ttu-id="2c4a1-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="2c4a1-134">192.168.0.0</span></span>     |  <span data-ttu-id="2c4a1-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2c4a1-135">192.168.1.0</span></span>     |
|<span data-ttu-id="2c4a1-136">Maske</span><span class="sxs-lookup"><span data-stu-id="2c4a1-136">Mask</span></span>  |     <span data-ttu-id="2c4a1-137">24</span><span class="sxs-lookup"><span data-stu-id="2c4a1-137">24</span></span>    |   <span data-ttu-id="2c4a1-138">24</span><span class="sxs-lookup"><span data-stu-id="2c4a1-138">24</span></span>      |
|<span data-ttu-id="2c4a1-139">Site-ID</span><span class="sxs-lookup"><span data-stu-id="2c4a1-139">Site ID</span></span>  | <span data-ttu-id="2c4a1-140">Website (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-140">Site (Delhi)</span></span> | <span data-ttu-id="2c4a1-141">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2c4a1-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="2c4a1-142">Für mehrere Subnetze können Sie eine CSV-Datei mithilfe eines Skripts wie die folgenden importieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="2c4a1-143">In diesem Beispiel sieht die CSV-Datei etwa so aussehen:</span><span class="sxs-lookup"><span data-stu-id="2c4a1-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="2c4a1-144">Definieren der externen Subnetze</span><span class="sxs-lookup"><span data-stu-id="2c4a1-144">Define external subnets</span></span>
<span data-ttu-id="2c4a1-145">Verwenden Sie das Cmdlet " [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) " zum Definieren von externen Subnetze und weisen Sie diese den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="2c4a1-146">Sie können eine unbegrenzte Anzahl von Subnetzen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="2c4a1-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="2c4a1-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c4a1-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="2c4a1-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2c4a1-148">Next steps</span></span>
<span data-ttu-id="2c4a1-149">Wechseln Sie zur [speicherortbasierte Routing für die direkte Weiterleitung aktivieren](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2c4a1-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="2c4a1-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2c4a1-150">Related topics</span></span>
- [<span data-ttu-id="2c4a1-151">Planen des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="2c4a1-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="2c4a1-152">Terminologie für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="2c4a1-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
