---
title: Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie netzwerkregionen,-Standorte und-Subnetze für standortbasiertes Routing für das direkte Routing erstellen und einrichten.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570699"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="46171-103">Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="46171-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="46171-104">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des ortsbasierten Routings für das direkte Routing](location-based-routing-plan.md) , um weitere Schritte zu überprüfen, die Sie ausführen müssen, bevor Sie die Netzwerkeinstellungen für standortbasiertes Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46171-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="46171-105">In diesem Artikel wird beschrieben, wie Sie Netzwerkeinstellungen für standortbasiertes Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46171-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="46171-106">Nachdem Sie die direkte Weiterleitung des Telefonsystems in Ihrer Organisation bereitgestellt haben, besteht der nächste Schritt darin, netzwerkregionen, Netzwerk Websites und Netzwerk-Subnets zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="46171-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="46171-107">Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="46171-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="46171-108">Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="46171-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="46171-109">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="46171-109">Define network regions</span></span>
 <span data-ttu-id="46171-110">Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg.</span><span class="sxs-lookup"><span data-stu-id="46171-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="46171-111">Verwenden Sie das Cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) , um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="46171-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="46171-112">Beachten Sie, dass der Parameter "Regions-ID" ein logischer Name ist, der die Geographie des Bereichs darstellt &lt;und keine&gt; Abhängigkeiten oder Einschränkungen aufweist, und der CentralSite-Parameter der Website-ID optional ist.</span><span class="sxs-lookup"><span data-stu-id="46171-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="46171-113">In diesem Beispiel erstellen wir eine netzwerkregion mit dem Namen Indien.</span><span class="sxs-lookup"><span data-stu-id="46171-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="46171-114">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="46171-114">Define network sites</span></span>

<span data-ttu-id="46171-115">Verwenden Sie das Cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) , um Netzwerk Websites zu definieren.</span><span class="sxs-lookup"><span data-stu-id="46171-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="46171-116">In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte, Delhi und Hyderabad, in der Region Indien.</span><span class="sxs-lookup"><span data-stu-id="46171-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="46171-117">In der folgenden Tabelle sind die Netzwerk Websites aufgeführt, die in diesem Beispiel definiert sind.</span><span class="sxs-lookup"><span data-stu-id="46171-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="46171-118">Website 1</span><span class="sxs-lookup"><span data-stu-id="46171-118">Site 1</span></span> |<span data-ttu-id="46171-119">Website 2</span><span class="sxs-lookup"><span data-stu-id="46171-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="46171-120">Website-ID</span><span class="sxs-lookup"><span data-stu-id="46171-120">Site ID</span></span>    |    <span data-ttu-id="46171-121">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="46171-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="46171-122">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="46171-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="46171-123">Regions-ID</span><span class="sxs-lookup"><span data-stu-id="46171-123">Region ID</span></span>  |     <span data-ttu-id="46171-124">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="46171-124">Region 1 (India)</span></span>    |   <span data-ttu-id="46171-125">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="46171-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="46171-126">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="46171-126">Define network subnets</span></span>

<span data-ttu-id="46171-127">Verwenden Sie das Cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="46171-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="46171-128">Jedes interne Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="46171-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="46171-129">In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz-192.168.0.0 und der Delhi-Netzwerk Website und zwischen Subnetz 2001:4898: E8:25:844E: 926f: 85ad: dd8e und der Hyderabad-Netzwerk Website.</span><span class="sxs-lookup"><span data-stu-id="46171-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="46171-130">In der folgenden Tabelle sind die in diesem Beispiel definierten Subnets aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="46171-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="46171-131">Website 1</span><span class="sxs-lookup"><span data-stu-id="46171-131">Site 1</span></span> |<span data-ttu-id="46171-132">Website 2</span><span class="sxs-lookup"><span data-stu-id="46171-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="46171-133">Subnet-ID</span><span class="sxs-lookup"><span data-stu-id="46171-133">Subnet ID</span></span>   |    <span data-ttu-id="46171-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="46171-134">192.168.0.0</span></span>     |  <span data-ttu-id="46171-135">2001:4898: E8:25:844E: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="46171-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="46171-136">Format</span><span class="sxs-lookup"><span data-stu-id="46171-136">Mask</span></span>  |     <span data-ttu-id="46171-137">24</span><span class="sxs-lookup"><span data-stu-id="46171-137">24</span></span>    |   <span data-ttu-id="46171-138">120</span><span class="sxs-lookup"><span data-stu-id="46171-138">120</span></span>      |
|<span data-ttu-id="46171-139">Website-ID</span><span class="sxs-lookup"><span data-stu-id="46171-139">Site ID</span></span>  | <span data-ttu-id="46171-140">Website (Delhi)</span><span class="sxs-lookup"><span data-stu-id="46171-140">Site (Delhi)</span></span> | <span data-ttu-id="46171-141">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="46171-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="46171-142">Bei mehreren Subnetzen können Sie eine CSV-Datei mit einem Skript wie dem folgenden importieren.</span><span class="sxs-lookup"><span data-stu-id="46171-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="46171-143">In diesem Beispiel sieht die CSV-Datei etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="46171-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="46171-144">Definieren externer Subnetze</span><span class="sxs-lookup"><span data-stu-id="46171-144">Define external subnets</span></span>
<span data-ttu-id="46171-145">Verwenden Sie das Cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , um externe Subnetze zu definieren und dem Mandanten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="46171-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="46171-146">Sie können eine unbegrenzte Anzahl von Subnetzen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="46171-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="46171-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="46171-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="46171-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="46171-148">Next steps</span></span>
<span data-ttu-id="46171-149">Wechseln Sie zum [Aktivieren des ortsbasierten Routings für das direkte Routing](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="46171-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="46171-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="46171-150">Related topics</span></span>
- [<span data-ttu-id="46171-151">Planen des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="46171-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="46171-152">Terminologie für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="46171-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
