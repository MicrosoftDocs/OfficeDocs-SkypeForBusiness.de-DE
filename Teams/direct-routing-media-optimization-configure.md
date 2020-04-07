---
title: Direkte Weiterleitung der lokalen Medienoptimierung
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Konfigurieren der lokalen Medienoptimierung für das direkte Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158013"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="4d8a7-103">Konfigurieren der lokalen Medienoptimierung für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="4d8a7-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="4d8a7-104">Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die anderen Cloud-Sprachfeatures, wie standortbasiertes Routing und dynamische Notrufe, gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="4d8a7-105">Weitere Informationen zu netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="4d8a7-106">Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie [lokale Medienoptimierung für direktes Routing](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="4d8a7-107">Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="4d8a7-108">Sie können das Team Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="4d8a7-109">Ausführliche Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="4d8a7-110">Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="4d8a7-111">Konfigurieren Sie die SBCS für die lokale Medienoptimierung (gemäß ihrer SBC-Herstellerspezifikation).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="4d8a7-112">Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="4d8a7-113">![Diagramm mit Netzwerk Setup für Beispiele](media/direct-routing-media-op-9.png "Netzwerk-Setup für Beispiele")</span><span class="sxs-lookup"><span data-stu-id="4d8a7-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="4d8a7-114">Konfigurieren des Benutzers und der SBC-Websites</span><span class="sxs-lookup"><span data-stu-id="4d8a7-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="4d8a7-115">Wenn Sie den Benutzer und die SBC-Websites konfigurieren möchten, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="4d8a7-116">[Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="4d8a7-117">[Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die netzwerkregionen, Netzwerkstandorte und Netzwerk-Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="4d8a7-118">[Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie SBC (s) den Websites mit relevanten Modi und Proxy-SBC-Werten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="4d8a7-119">Konfigurieren von SBC (s) für die lokale Medienoptimierung gemäß der SBC-Herstellerspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d8a7-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="4d8a7-120">In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="4d8a7-121">Informationen zur SBC-Konfiguration finden Sie in Ihrem SBC-Anbieterdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="4d8a7-122">Die lokale Medienoptimierung wird von den folgenden SBC-Anbietern unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="4d8a7-123">Anbieter</span><span class="sxs-lookup"><span data-stu-id="4d8a7-123">Vendor</span></span> | <span data-ttu-id="4d8a7-124">Produkt</span><span class="sxs-lookup"><span data-stu-id="4d8a7-124">Product</span></span> |    <span data-ttu-id="4d8a7-125">Software Version</span><span class="sxs-lookup"><span data-stu-id="4d8a7-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="4d8a7-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4d8a7-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="4d8a7-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="4d8a7-128">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="4d8a7-130">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="4d8a7-132">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="4d8a7-134">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-135">Mediant-1000B-SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="4d8a7-136">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="4d8a7-138">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="4d8a7-140">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="4d8a7-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="4d8a7-142">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="4d8a7-142">7.20A.256</span></span> |
| [<span data-ttu-id="4d8a7-143">Menüband-SBC-Kern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="4d8a7-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="4d8a7-144">SBC 5110</span></span>         | <span data-ttu-id="4d8a7-145">8,2</span><span class="sxs-lookup"><span data-stu-id="4d8a7-145">8.2</span></span>  |
|            |  <span data-ttu-id="4d8a7-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="4d8a7-146">SBC 5210</span></span>         | <span data-ttu-id="4d8a7-147">8,2</span><span class="sxs-lookup"><span data-stu-id="4d8a7-147">8.2</span></span>  |
|            |  <span data-ttu-id="4d8a7-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="4d8a7-148">SBC 5400</span></span>         | <span data-ttu-id="4d8a7-149">8,2</span><span class="sxs-lookup"><span data-stu-id="4d8a7-149">8.2</span></span>  |
|            |  <span data-ttu-id="4d8a7-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="4d8a7-150">SBC 7000</span></span>         | <span data-ttu-id="4d8a7-151">8,2</span><span class="sxs-lookup"><span data-stu-id="4d8a7-151">8.2</span></span>  |
|            |  <span data-ttu-id="4d8a7-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="4d8a7-152">SBC SWe</span></span>          | <span data-ttu-id="4d8a7-153">8,2</span><span class="sxs-lookup"><span data-stu-id="4d8a7-153">8.2</span></span>  |
| [<span data-ttu-id="4d8a7-154">Menüband SBC-Kante</span><span class="sxs-lookup"><span data-stu-id="4d8a7-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="4d8a7-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="4d8a7-155">SBC 1000</span></span>         | <span data-ttu-id="4d8a7-156">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="4d8a7-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="4d8a7-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="4d8a7-157">SBC 2000</span></span>         | <span data-ttu-id="4d8a7-158">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="4d8a7-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="4d8a7-159">Lite SBC Schwedisch</span><span class="sxs-lookup"><span data-stu-id="4d8a7-159">SBC SWe Lite</span></span>     | <span data-ttu-id="4d8a7-160">8.1.0, Build 222</span><span class="sxs-lookup"><span data-stu-id="4d8a7-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="4d8a7-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="4d8a7-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="4d8a7-162">anynode</span><span class="sxs-lookup"><span data-stu-id="4d8a7-162">anynode</span></span>          | <span data-ttu-id="4d8a7-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="4d8a7-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="4d8a7-164">Verwalten externer vertrauenswürdiger IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="4d8a7-165">Externe vertrauenswürdige IPS sind die Internet externen IPS des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="4d8a7-166">Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams-Clients verwendet werden, wenn Sie eine Verbindung mit Microsoft 365 herstellen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="4d8a7-167">Sie müssen diese externen IPS für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="4d8a7-168">Wenn Sie die öffentlichen IP-Adressen für jede Website hinzufügen möchten, verwenden Sie das Cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="4d8a7-169">Sie können eine unbegrenzte Anzahl von vertrauenswürdigen IP-Adressen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="4d8a7-170">Wenn die von Microsoft 365 gesehenen externen IPS sowohl IPv4-als auch IPv6-Adressen sind, müssen Sie beide Typen von IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="4d8a7-171">Verwenden Sie für IPv4 Maske 32.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="4d8a7-172">Verwenden Sie für IPv6 die Maske 128.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="4d8a7-173">Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie unterschiedliche MaskBits für das Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="4d8a7-174">Beispiel für das Hinzufügen von vertrauenswürdigen IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="4d8a7-175">Definieren der Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="4d8a7-175">Define the network topology</span></span>

<span data-ttu-id="4d8a7-176">In diesem Abschnitt wird beschrieben, wie Sie die netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze für Ihre Netzwerktopologie definieren.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="4d8a7-177">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, daher müssen Sie sicherstellen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="4d8a7-178">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="4d8a7-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="4d8a7-179">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-179">Define network regions</span></span>

<span data-ttu-id="4d8a7-180">Verwenden Sie zum Definieren von netzwerkregionen das Cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="4d8a7-181">Der Parameter Regions-Nr ist ein logischer Name, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="4d8a7-182">Der CentralSite <site ID> -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="4d8a7-183">Im folgenden Beispiel wird eine netzwerkregion mit dem Namen APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="4d8a7-184">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="4d8a7-184">Define network sites</span></span>

<span data-ttu-id="4d8a7-185">Verwenden Sie zum Definieren von Netzwerk Websites das Cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="4d8a7-186">Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="4d8a7-187">Im folgenden Beispiel werden drei neue Netzwerk Websites, Vietnam, Indonesien und Singapur, in der Region APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="4d8a7-188">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-188">Define network subnets</span></span>

<span data-ttu-id="4d8a7-189">Verwenden Sie das Cmdlet New-CsTenantNetworkSubnet, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="4d8a7-190">Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="4d8a7-191">Im folgenden Beispiel werden drei Netzwerk-Subnetze definiert und den drei Netzwerkstandorten zugeordnet: Vietnam, Indonesien und Singapur:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="4d8a7-192">Definieren der virtuellen Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="4d8a7-192">Define the virtual network topology</span></span> 

<span data-ttu-id="4d8a7-193">Zunächst erstellt der mandantenadministrator mithilfe des Cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="4d8a7-194">Der mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerk Websites für die PSTN-Gateway-Objekte mit dem Cmdlet "CsOnlinePSTNGateway" angibt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="4d8a7-195">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-195">Note the following:</span></span> 
   - <span data-ttu-id="4d8a7-196">Wenn der Kunde über einen einzelnen SBC verfügt, muss der-ProxySBC-Parameter entweder obligatorisch $NULL oder SBC-FQDN-Wert sein (zentrales SBC-Szenario mit zentralisierten Trunks).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="4d8a7-197">Der-MediaBypass-Parameter muss auf $true eingestellt sein, um die lokale Medienoptimierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="4d8a7-198">Wenn der SBC-BypassMode-Parametersatz nicht vorhanden ist, werden keine X-MS-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="4d8a7-199">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie den gleichen Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="4d8a7-200">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="4d8a7-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="4d8a7-201">Im folgenden Beispiel werden drei SBCS zu den Netzwerkstandorten Vietnam, Indonesien und Singapur im Bereich APAC mit dem Modus immer umgehen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="4d8a7-202">Hinweis: um unterbrechungsfreie Vorgänge zu gewährleisten, wenn die lokale Medienoptimierung und standortbasiertes Routing (LBR) gleichzeitig konfiguriert sind, muss Downstream-SBCS für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden Downstream-SBC auf $true festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="4d8a7-203">(Diese Einstellung ist für den Proxy-SBC nicht zwingend erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="4d8a7-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="4d8a7-204">Basierend auf den oben aufgeführten Informationen umfasst das direkte Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="4d8a7-205">X-MS-Header, die beim direkten Routing bei Einladungen und erneuten Einladungen eingeführt werden, wenn BypassMode definiert ist:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="4d8a7-206">Header Name</span><span class="sxs-lookup"><span data-stu-id="4d8a7-206">Header name</span></span> | <span data-ttu-id="4d8a7-207">Werte</span><span class="sxs-lookup"><span data-stu-id="4d8a7-207">Values</span></span> | <span data-ttu-id="4d8a7-208">Kommentare</span><span class="sxs-lookup"><span data-stu-id="4d8a7-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="4d8a7-209">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="4d8a7-209">X-MS-UserLocation</span></span> | <span data-ttu-id="4d8a7-210">intern/extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-210">internal/external</span></span> | <span data-ttu-id="4d8a7-211">Gibt an, ob der Benutzer intern oder extern ist</span><span class="sxs-lookup"><span data-stu-id="4d8a7-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="4d8a7-212">Request-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="4d8a7-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="4d8a7-213">SBC-FQDN</span><span class="sxs-lookup"><span data-stu-id="4d8a7-213">SBC FQDN</span></span> | <span data-ttu-id="4d8a7-214">Der FQDN, der für den Anruf vorgesehen ist, auch wenn der SBC nicht direkt mit dem direkten Routing verbunden ist</span><span class="sxs-lookup"><span data-stu-id="4d8a7-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="4d8a7-215">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="4d8a7-215">X-MS-MediaPath</span></span> | <span data-ttu-id="4d8a7-216">Beispiel: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-217">Die Reihenfolge der SBCS, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="4d8a7-218">Der endgültige SBC ist immer der letzte.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-218">The final SBC is always last</span></span> |
| <span data-ttu-id="4d8a7-219">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="4d8a7-219">X-MS-UserSite</span></span> | <span data-ttu-id="4d8a7-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="4d8a7-220">usersiteID</span></span> | <span data-ttu-id="4d8a7-221">Vom mandantenadministrator festgelegte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d8a7-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="4d8a7-222">Anruf Flüsse</span><span class="sxs-lookup"><span data-stu-id="4d8a7-222">Call flows</span></span> 

<span data-ttu-id="4d8a7-223">Im folgenden werden die Anruf Flüsse für zwei Modi angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="4d8a7-224">Immer umgehen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="4d8a7-225">Nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="4d8a7-226">Modus immer umgehen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-226">Always Bypass mode</span></span>

<span data-ttu-id="4d8a7-227">Der Bypass-Modus ist immer die einfachste Option für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="4d8a7-228">Der mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCS konfigurieren, wenn alle SBCS von einer beliebigen Website aus erreichbar sind.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="4d8a7-229">In den Beispielen wird der Modus "immer umgehen" für die folgenden Szenarien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="4d8a7-230">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="4d8a7-231">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="4d8a7-232">Ausgehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="4d8a7-233">Eingehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="4d8a7-234">In der folgenden Tabelle sind die in den Beispielen verwendeten FQDN-und IP-Adressen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="4d8a7-235">FQDN</span><span class="sxs-lookup"><span data-stu-id="4d8a7-235">FQDN</span></span> | <span data-ttu-id="4d8a7-236">Externe SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="4d8a7-236">SBC external IP address</span></span> | <span data-ttu-id="4d8a7-237">Interne SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="4d8a7-237">SBC internal IP Address</span></span> | <span data-ttu-id="4d8a7-238">Internes Subnetz</span><span class="sxs-lookup"><span data-stu-id="4d8a7-238">Internal subnet</span></span> | <span data-ttu-id="4d8a7-239">Ort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-239">Location</span></span> | <span data-ttu-id="4d8a7-240">Externe NAT (vertrauenswürdige IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="4d8a7-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-242">Keine</span><span class="sxs-lookup"><span data-stu-id="4d8a7-242">None</span></span> | <span data-ttu-id="4d8a7-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="4d8a7-243">192.168.1.5</span></span> | <span data-ttu-id="4d8a7-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="4d8a7-244">192.168.1.0/24</span></span> | <span data-ttu-id="4d8a7-245">Vietnam</span><span class="sxs-lookup"><span data-stu-id="4d8a7-245">Vietnam</span></span> | <span data-ttu-id="4d8a7-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="4d8a7-246">172.16.240.110</span></span> |
| <span data-ttu-id="4d8a7-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-248">Keine</span><span class="sxs-lookup"><span data-stu-id="4d8a7-248">None</span></span> | <span data-ttu-id="4d8a7-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="4d8a7-249">192.168.2.5</span></span> | <span data-ttu-id="4d8a7-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="4d8a7-250">192.168.2.0/24</span></span> | <span data-ttu-id="4d8a7-251">Indonesien</span><span class="sxs-lookup"><span data-stu-id="4d8a7-251">Indonesia</span></span> | <span data-ttu-id="4d8a7-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="4d8a7-252">172.16.240.120</span></span> |
| <span data-ttu-id="4d8a7-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="4d8a7-254">172.16.240.133</span></span> | <span data-ttu-id="4d8a7-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="4d8a7-255">192.168.3.5</span></span> | <span data-ttu-id="4d8a7-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="4d8a7-256">192.168.3.0/24</span></span> | <span data-ttu-id="4d8a7-257">Singapur</span><span class="sxs-lookup"><span data-stu-id="4d8a7-257">Singapore</span></span> | <span data-ttu-id="4d8a7-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="4d8a7-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="4d8a7-259">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="4d8a7-260">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-260">Mode</span></span> |    <span data-ttu-id="4d8a7-261">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-261">User</span></span> |  <span data-ttu-id="4d8a7-262">Ort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-262">Location</span></span> |  <span data-ttu-id="4d8a7-263">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="4d8a7-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-264">AlwaysBypass</span></span> |    <span data-ttu-id="4d8a7-265">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-265">Internal</span></span> |  <span data-ttu-id="4d8a7-266">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-266">The same site as SBC</span></span> |  <span data-ttu-id="4d8a7-267">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="4d8a7-267">Outbound</span></span> |

<span data-ttu-id="4d8a7-268">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="4d8a7-269">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-269">User physical location</span></span>| <span data-ttu-id="4d8a7-270">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="4d8a7-271">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-271">User phone number</span></span>  | <span data-ttu-id="4d8a7-272">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4d8a7-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="4d8a7-273">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-274">Vietnam</span><span class="sxs-lookup"><span data-stu-id="4d8a7-274">Vietnam</span></span> | <span data-ttu-id="4d8a7-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="4d8a7-275">+84 4 3926 3000</span></span> | <span data-ttu-id="4d8a7-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="4d8a7-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="4d8a7-277">Priorität 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="4d8a7-278">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="4d8a7-279">VNsbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="4d8a7-280">proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="4d8a7-281">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit Always Bypass-Modus und den Benutzer am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="4d8a7-282">![Diagramm mit ausgehenden Anrufen](media/direct-routing-media-op-10.png "Ausgehende Anrufe")</span><span class="sxs-lookup"><span data-stu-id="4d8a7-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="4d8a7-283">Die folgende Tabelle zeigt die X-MS-Kopfzeilen, die durch Direct Routing gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="4d8a7-284">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d8a7-284">Parameter</span></span> | <span data-ttu-id="4d8a7-285">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="4d8a7-286">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-287">Der Zielname des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet</span><span class="sxs-lookup"><span data-stu-id="4d8a7-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="4d8a7-288">X-MS-UserLocation: intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="4d8a7-289">Das Feld hat angegeben, dass sich der Benutzer im Unternehmensnetzwerk befindet</span><span class="sxs-lookup"><span data-stu-id="4d8a7-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="4d8a7-290">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="4d8a7-291">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="4d8a7-292">In diesem Fall, da wir immer Bypass haben und der Client intern ist, wird der Zielname als einziger Name im Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="4d8a7-293">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="4d8a7-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="4d8a7-294">Das Feld, das auf der Website angegeben ist, in der sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="4d8a7-295">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="4d8a7-296">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-296">Mode</span></span> |    <span data-ttu-id="4d8a7-297">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-297">User</span></span> |  <span data-ttu-id="4d8a7-298">Ort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-298">Location</span></span> |  <span data-ttu-id="4d8a7-299">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-300">AlwaysBypass</span></span> |    <span data-ttu-id="4d8a7-301">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-301">Internal</span></span> | <span data-ttu-id="4d8a7-302">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-302">The same site as SBC</span></span> | <span data-ttu-id="4d8a7-303">Inbound</span><span class="sxs-lookup"><span data-stu-id="4d8a7-303">Inbound</span></span> |


<span data-ttu-id="4d8a7-304">Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="4d8a7-305">Wenn die Vermutung nicht korrekt ist, wird eine erneute Einladung benötigt.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="4d8a7-306">In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneut einladen).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="4d8a7-307">Der SBC, der mit dem Direct Routing-Dienst verbunden ist, meldet den ursprünglichen SBC-Standort durch Bereitstellen von Daten Satz Routen-und Kontaktfeldern.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="4d8a7-308">Basierend auf diesen Feldern wird der Medienpfad durch direkte Weiterleitung berechnet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="4d8a7-309">Hinweis: da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="4d8a7-310">Die direkte Weiterleitung wird in diesem Fall immer 180-Klingeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="4d8a7-311">Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe mit dem AlwaysBypass-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="4d8a7-313">Ausgehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="4d8a7-314">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-314">Mode</span></span> |    <span data-ttu-id="4d8a7-315">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-315">User</span></span> |  <span data-ttu-id="4d8a7-316">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-316">Site</span></span> |  <span data-ttu-id="4d8a7-317">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="4d8a7-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-318">AlwaysBypass</span></span> |  <span data-ttu-id="4d8a7-319">Extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-319">External</span></span> |  <span data-ttu-id="4d8a7-320">N/A</span><span class="sxs-lookup"><span data-stu-id="4d8a7-320">N/A</span></span> | <span data-ttu-id="4d8a7-321">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="4d8a7-321">Outbound</span></span> |


<span data-ttu-id="4d8a7-322">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-12.png)

<span data-ttu-id="4d8a7-324">Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="4d8a7-325">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d8a7-325">Parameter</span></span> |   <span data-ttu-id="4d8a7-326">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="4d8a7-327">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-328">Der Zielname des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="4d8a7-329">X-MS-UserLocation: Extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="4d8a7-330">Das Feld hat angegeben, dass der Benutzer sich außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="4d8a7-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="4d8a7-332">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="4d8a7-333">In diesem Fall, da wir immer Bypass haben und der Client extern ist.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="4d8a7-334">Eingehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="4d8a7-335">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-335">Mode</span></span> | <span data-ttu-id="4d8a7-336">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-336">User</span></span> | <span data-ttu-id="4d8a7-337">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-337">Site</span></span> |  <span data-ttu-id="4d8a7-338">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="4d8a7-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="4d8a7-339">AlwaysBypass</span></span> |  <span data-ttu-id="4d8a7-340">Extern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-340">External</span></span> |  <span data-ttu-id="4d8a7-341">N/A</span><span class="sxs-lookup"><span data-stu-id="4d8a7-341">N/A</span></span> |   <span data-ttu-id="4d8a7-342">Inbound</span><span class="sxs-lookup"><span data-stu-id="4d8a7-342">Inbound</span></span> |

<span data-ttu-id="4d8a7-343">Bei einem eingehenden Anruf muss der SBC, der mit dem direkten Routing verbunden ist, eine erneute Einladung senden (Standardmäßig werden lokale Medien Kandidaten immer angeboten), wenn der Standort des Benutzers extern ist.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="4d8a7-344">Die X-MediaPath wird basierend auf der Daten Satz Route und dem angegebenen SBC-Benutzer berechnet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="4d8a7-345">Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="4d8a7-347">Nur für den lokalen Benutzermodus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-347">Only for local users mode</span></span>

<span data-ttu-id="4d8a7-348">Lokale Medien Kandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Ort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="4d8a7-349">In allen anderen Fällen fließen Medien entweder über eine interne oder externe IP-Adresse des Proxy-SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="4d8a7-350">Die folgenden Szenarien werden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="4d8a7-351">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="4d8a7-352">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="4d8a7-353">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="4d8a7-354">Eingehende Anrufe und der Benutzer ist intern, aber nicht am selben Ort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="4d8a7-355">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="4d8a7-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="4d8a7-356">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-356">User physical location</span></span> |  <span data-ttu-id="4d8a7-357">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="4d8a7-358">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-358">User phone number</span></span> | <span data-ttu-id="4d8a7-359">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4d8a7-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="4d8a7-360">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-361">Vietnam</span><span class="sxs-lookup"><span data-stu-id="4d8a7-361">Vietnam</span></span> | <span data-ttu-id="4d8a7-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="4d8a7-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="4d8a7-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="4d8a7-363">+84 4 5555 5555</span></span> | <span data-ttu-id="4d8a7-364">Priorität 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="4d8a7-365">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d8a7-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="4d8a7-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="4d8a7-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="4d8a7-367">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="4d8a7-368">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-368">Mode</span></span> | <span data-ttu-id="4d8a7-369">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-369">User</span></span> | <span data-ttu-id="4d8a7-370">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-370">Site</span></span> | <span data-ttu-id="4d8a7-371">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="4d8a7-373">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-373">Internal</span></span> |<span data-ttu-id="4d8a7-374">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-374">Same as SBC</span></span>   | <span data-ttu-id="4d8a7-375">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="4d8a7-375">Outbound</span></span> |

<span data-ttu-id="4d8a7-376">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="4d8a7-377">Dies ist derselbe Fluss, der bei [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="4d8a7-379">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="4d8a7-380">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-380">Mode</span></span> | <span data-ttu-id="4d8a7-381">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-381">User</span></span> | <span data-ttu-id="4d8a7-382">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-382">Site</span></span> | <span data-ttu-id="4d8a7-383">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="4d8a7-385">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-385">Internal</span></span> | <span data-ttu-id="4d8a7-386">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-386">Same as SBC</span></span> | <span data-ttu-id="4d8a7-387">Inbound</span><span class="sxs-lookup"><span data-stu-id="4d8a7-387">Inbound</span></span> |

<span data-ttu-id="4d8a7-388">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="4d8a7-389">Hierbei handelt es sich um denselben Fluss wie in [eingehenden Anrufen, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="4d8a7-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="4d8a7-391">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk mit nur für lokale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="4d8a7-392">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-392">Mode</span></span> | <span data-ttu-id="4d8a7-393">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-393">User</span></span> | <span data-ttu-id="4d8a7-394">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-394">Site</span></span> |<span data-ttu-id="4d8a7-395">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="4d8a7-397">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-397">Internal</span></span> |   <span data-ttu-id="4d8a7-398">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-398">Different from SBC</span></span> | <span data-ttu-id="4d8a7-399">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="4d8a7-399">Outbound</span></span> |

<span data-ttu-id="4d8a7-400">Das direkte Routing berechnet X-MediaPath basierend auf dem gemeldeten Speicherort des Benutzers und des Modus, der für den SBC konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="4d8a7-401">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="4d8a7-403">Eingehender Anruf und der Benutzer ist intern, befindet sich aber nicht am gleichen Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="4d8a7-404">Modus</span><span class="sxs-lookup"><span data-stu-id="4d8a7-404">Mode</span></span> |    <span data-ttu-id="4d8a7-405">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d8a7-405">User</span></span> |  <span data-ttu-id="4d8a7-406">Standort</span><span class="sxs-lookup"><span data-stu-id="4d8a7-406">Site</span></span> |  <span data-ttu-id="4d8a7-407">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="4d8a7-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="4d8a7-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="4d8a7-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="4d8a7-409">Intern</span><span class="sxs-lookup"><span data-stu-id="4d8a7-409">Internal</span></span> |    <span data-ttu-id="4d8a7-410">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="4d8a7-410">Different from SBC</span></span> |    <span data-ttu-id="4d8a7-411">Inbound</span><span class="sxs-lookup"><span data-stu-id="4d8a7-411">Inbound</span></span> |

<span data-ttu-id="4d8a7-412">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="4d8a7-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-17.png)









