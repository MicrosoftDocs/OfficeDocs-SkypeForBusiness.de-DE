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
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576987"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="10dcf-103">Konfigurieren der lokalen Medienoptimierung für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="10dcf-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="10dcf-104">Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die anderen Cloud-Sprachfeatures, wie standortbasiertes Routing und dynamische Notrufe, gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="10dcf-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="10dcf-105">Weitere Informationen zu netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="10dcf-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="10dcf-106">Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie [lokale Medienoptimierung für direktes Routing](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="10dcf-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="10dcf-107">Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10dcf-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="10dcf-108">Sie können das Team Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="10dcf-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="10dcf-109">Ausführliche Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="10dcf-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="10dcf-110">Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).</span><span class="sxs-lookup"><span data-stu-id="10dcf-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="10dcf-111">Konfigurieren Sie die SBCS für die lokale Medienoptimierung (gemäß ihrer SBC-Herstellerspezifikation).</span><span class="sxs-lookup"><span data-stu-id="10dcf-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="10dcf-112">Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="10dcf-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="10dcf-113">![Diagramm mit Netzwerk Setup für Beispiele](media/direct-routing-media-op-9.png "Netzwerk-Setup für Beispiele")</span><span class="sxs-lookup"><span data-stu-id="10dcf-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="10dcf-114">Konfigurieren des Benutzers und der SBC-Websites</span><span class="sxs-lookup"><span data-stu-id="10dcf-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="10dcf-115">Wenn Sie den Benutzer und die SBC-Websites konfigurieren möchten, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="10dcf-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="10dcf-116">[Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="10dcf-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="10dcf-117">[Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die netzwerkregionen, Netzwerkstandorte und Netzwerk-Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10dcf-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="10dcf-118">[Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie SBC (s) den Websites mit relevanten Modi und Proxy-SBC-Werten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="10dcf-119">Konfigurieren von SBC (s) für die lokale Medienoptimierung gemäß der SBC-Herstellerspezifikation</span><span class="sxs-lookup"><span data-stu-id="10dcf-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="10dcf-120">In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10dcf-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="10dcf-121">Informationen zur SBC-Konfiguration finden Sie in der Dokumentation Ihres SBC-Herstellers.</span><span class="sxs-lookup"><span data-stu-id="10dcf-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="10dcf-122">Die lokale Medienoptimierung wird von den folgenden SBC-Anbietern unterstützt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="10dcf-123">Anbieter</span><span class="sxs-lookup"><span data-stu-id="10dcf-123">Vendor</span></span> | <span data-ttu-id="10dcf-124">Produkt</span><span class="sxs-lookup"><span data-stu-id="10dcf-124">Product</span></span> |    <span data-ttu-id="10dcf-125">Software Version</span><span class="sxs-lookup"><span data-stu-id="10dcf-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="10dcf-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="10dcf-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="10dcf-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="10dcf-128">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="10dcf-130">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="10dcf-132">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="10dcf-134">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-135">Mediant-1000B-SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="10dcf-136">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="10dcf-138">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="10dcf-140">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="10dcf-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="10dcf-142">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="10dcf-142">7.20A.256</span></span> |
| [<span data-ttu-id="10dcf-143">Menüband-SBC-Kern</span><span class="sxs-lookup"><span data-stu-id="10dcf-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="10dcf-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="10dcf-144">SBC 5110</span></span>         | <span data-ttu-id="10dcf-145">8,2</span><span class="sxs-lookup"><span data-stu-id="10dcf-145">8.2</span></span>  |
|            |  <span data-ttu-id="10dcf-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="10dcf-146">SBC 5210</span></span>         | <span data-ttu-id="10dcf-147">8,2</span><span class="sxs-lookup"><span data-stu-id="10dcf-147">8.2</span></span>  |
|            |  <span data-ttu-id="10dcf-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="10dcf-148">SBC 5400</span></span>         | <span data-ttu-id="10dcf-149">8,2</span><span class="sxs-lookup"><span data-stu-id="10dcf-149">8.2</span></span>  |
|            |  <span data-ttu-id="10dcf-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="10dcf-150">SBC 7000</span></span>         | <span data-ttu-id="10dcf-151">8,2</span><span class="sxs-lookup"><span data-stu-id="10dcf-151">8.2</span></span>  |
|            |  <span data-ttu-id="10dcf-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="10dcf-152">SBC SWe</span></span>          | <span data-ttu-id="10dcf-153">8,2</span><span class="sxs-lookup"><span data-stu-id="10dcf-153">8.2</span></span>  |
| [<span data-ttu-id="10dcf-154">Menüband SBC-Kante</span><span class="sxs-lookup"><span data-stu-id="10dcf-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="10dcf-155">Lite SBC Schwedisch</span><span class="sxs-lookup"><span data-stu-id="10dcf-155">SBC SWe Lite</span></span> | <span data-ttu-id="10dcf-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-156">8.1.5</span></span> |
|               | <span data-ttu-id="10dcf-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="10dcf-157">SBC 1000</span></span> | <span data-ttu-id="10dcf-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-158">8.1.5</span></span>  |
|               | <span data-ttu-id="10dcf-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="10dcf-159">SBC 2000</span></span> | <span data-ttu-id="10dcf-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-160">8.1.5</span></span>  |
| [<span data-ttu-id="10dcf-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="10dcf-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="10dcf-162">anynode</span><span class="sxs-lookup"><span data-stu-id="10dcf-162">anynode</span></span>          | <span data-ttu-id="10dcf-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="10dcf-163">4.0.1+</span></span> |
| [<span data-ttu-id="10dcf-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="10dcf-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="10dcf-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="10dcf-165">AP 1100</span></span> | <span data-ttu-id="10dcf-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="10dcf-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="10dcf-167">AP 3900</span></span> | <span data-ttu-id="10dcf-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="10dcf-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="10dcf-169">AP 4600</span></span> | <span data-ttu-id="10dcf-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="10dcf-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="10dcf-171">AP 6300</span></span> | <span data-ttu-id="10dcf-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="10dcf-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="10dcf-173">AP 6350</span></span> | <span data-ttu-id="10dcf-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="10dcf-175">VME</span><span class="sxs-lookup"><span data-stu-id="10dcf-175">VME</span></span>     | <span data-ttu-id="10dcf-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="10dcf-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="10dcf-177">Verwalten externer vertrauenswürdiger IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="10dcf-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="10dcf-178">Externe vertrauenswürdige IPS sind die Internet externen IPS des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="10dcf-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="10dcf-179">Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams-Clients verwendet werden, wenn Sie eine Verbindung mit Microsoft 365 herstellen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="10dcf-180">Sie müssen diese externen IPS für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="10dcf-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="10dcf-181">Wenn Sie die öffentlichen IP-Adressen für jede Website hinzufügen möchten, verwenden Sie das Cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="10dcf-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="10dcf-182">Sie können eine unbegrenzte Anzahl von vertrauenswürdigen IP-Adressen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="10dcf-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="10dcf-183">Wenn die von Microsoft 365 gesehenen externen IPS sowohl IPv4-als auch IPv6-Adressen sind, müssen Sie beide Typen von IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="10dcf-184">Verwenden Sie für IPv4 Maske 32.</span><span class="sxs-lookup"><span data-stu-id="10dcf-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="10dcf-185">Verwenden Sie für IPv6 die Maske 128.</span><span class="sxs-lookup"><span data-stu-id="10dcf-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="10dcf-186">Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie unterschiedliche MaskBits für das Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="10dcf-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="10dcf-187">Beispiel für das Hinzufügen von vertrauenswürdigen IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="10dcf-188">Definieren der Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="10dcf-188">Define the network topology</span></span>

<span data-ttu-id="10dcf-189">In diesem Abschnitt wird beschrieben, wie Sie die netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze für Ihre Netzwerktopologie definieren.</span><span class="sxs-lookup"><span data-stu-id="10dcf-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="10dcf-190">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, daher müssen Sie sicherstellen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="10dcf-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="10dcf-191">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="10dcf-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="10dcf-192">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="10dcf-192">Define network regions</span></span>

<span data-ttu-id="10dcf-193">Verwenden Sie zum Definieren von netzwerkregionen das Cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="10dcf-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="10dcf-194">Der Parameter Regions-Nr ist ein logischer Name, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="10dcf-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="10dcf-195">Der CentralSite <site ID> -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="10dcf-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="10dcf-196">Im folgenden Beispiel wird eine netzwerkregion mit dem Namen APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="10dcf-197">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="10dcf-197">Define network sites</span></span>

<span data-ttu-id="10dcf-198">Verwenden Sie zum Definieren von Netzwerk Websites das Cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="10dcf-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="10dcf-199">Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="10dcf-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="10dcf-200">Im folgenden Beispiel werden drei neue Netzwerk Websites, Vietnam, Indonesien und Singapur, in der Region APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="10dcf-201">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="10dcf-201">Define network subnets</span></span>

<span data-ttu-id="10dcf-202">Verwenden Sie das Cmdlet New-CsTenantNetworkSubnet, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="10dcf-203">Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="10dcf-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="10dcf-204">Im folgenden Beispiel werden drei Netzwerk-Subnetze definiert und den drei Netzwerkstandorten zugeordnet: Vietnam, Indonesien und Singapur:</span><span class="sxs-lookup"><span data-stu-id="10dcf-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="10dcf-205">Definieren der virtuellen Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="10dcf-205">Define the virtual network topology</span></span> 

<span data-ttu-id="10dcf-206">Zunächst erstellt der mandantenadministrator mithilfe des Cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="10dcf-207">Der mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerk Websites für die PSTN-Gateway-Objekte mit dem Cmdlet "CsOnlinePSTNGateway" angibt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="10dcf-208">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10dcf-208">Note the following:</span></span> 
   - <span data-ttu-id="10dcf-209">Wenn der Kunde über einen einzelnen SBC verfügt, muss der-ProxySBC-Parameter entweder obligatorisch $NULL oder SBC-FQDN-Wert sein (zentrales SBC-Szenario mit zentralisierten Trunks).</span><span class="sxs-lookup"><span data-stu-id="10dcf-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="10dcf-210">Der-MediaBypass-Parameter muss auf $true eingestellt sein, um die lokale Medienoptimierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="10dcf-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="10dcf-211">Wenn der SBC-BypassMode-Parametersatz nicht vorhanden ist, werden keine X-MS-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="10dcf-212">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie den gleichen Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="10dcf-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="10dcf-213">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="10dcf-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="10dcf-214">Im folgenden Beispiel werden drei SBCS zu den Netzwerkstandorten Vietnam, Indonesien und Singapur im Bereich APAC mit dem Modus immer umgehen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="10dcf-215">Hinweis: um unterbrechungsfreie Vorgänge zu gewährleisten, wenn die lokale Medienoptimierung und standortbasiertes Routing (LBR) gleichzeitig konfiguriert sind, muss Downstream-SBCS für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden Downstream-SBC auf $true festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="10dcf-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="10dcf-216">(Diese Einstellung ist für den Proxy-SBC nicht zwingend erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="10dcf-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="10dcf-217">Basierend auf den oben aufgeführten Informationen umfasst das direkte Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10dcf-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="10dcf-218">X-MS-Header, die beim direkten Routing bei Einladungen und erneuten Einladungen eingeführt werden, wenn BypassMode definiert ist:</span><span class="sxs-lookup"><span data-stu-id="10dcf-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="10dcf-219">Header Name</span><span class="sxs-lookup"><span data-stu-id="10dcf-219">Header name</span></span> | <span data-ttu-id="10dcf-220">Werte</span><span class="sxs-lookup"><span data-stu-id="10dcf-220">Values</span></span> | <span data-ttu-id="10dcf-221">Kommentare</span><span class="sxs-lookup"><span data-stu-id="10dcf-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="10dcf-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="10dcf-222">X-MS-UserLocation</span></span> | <span data-ttu-id="10dcf-223">intern/extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-223">internal/external</span></span> | <span data-ttu-id="10dcf-224">Gibt an, ob der Benutzer intern oder extern ist</span><span class="sxs-lookup"><span data-stu-id="10dcf-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="10dcf-225">Request-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="10dcf-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="10dcf-226">SBC-FQDN</span><span class="sxs-lookup"><span data-stu-id="10dcf-226">SBC FQDN</span></span> | <span data-ttu-id="10dcf-227">Der FQDN, der für den Anruf vorgesehen ist, auch wenn der SBC nicht direkt mit dem direkten Routing verbunden ist</span><span class="sxs-lookup"><span data-stu-id="10dcf-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="10dcf-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="10dcf-228">X-MS-MediaPath</span></span> | <span data-ttu-id="10dcf-229">Beispiel: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="10dcf-230">Die Reihenfolge der SBCS, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10dcf-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="10dcf-231">Der endgültige SBC ist immer der letzte.</span><span class="sxs-lookup"><span data-stu-id="10dcf-231">The final SBC is always last</span></span> |
| <span data-ttu-id="10dcf-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="10dcf-232">X-MS-UserSite</span></span> | <span data-ttu-id="10dcf-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="10dcf-233">usersiteID</span></span> | <span data-ttu-id="10dcf-234">Vom mandantenadministrator festgelegte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10dcf-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="10dcf-235">Anruf Flüsse</span><span class="sxs-lookup"><span data-stu-id="10dcf-235">Call flows</span></span> 

<span data-ttu-id="10dcf-236">Im folgenden werden die Anruf Flüsse für zwei Modi angezeigt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="10dcf-237">Immer umgehen</span><span class="sxs-lookup"><span data-stu-id="10dcf-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="10dcf-238">Nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="10dcf-239">Modus immer umgehen</span><span class="sxs-lookup"><span data-stu-id="10dcf-239">Always Bypass mode</span></span>

<span data-ttu-id="10dcf-240">Der Bypass-Modus ist immer die einfachste Option für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="10dcf-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="10dcf-241">Der mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCS konfigurieren, wenn alle SBCS von einer beliebigen Website aus erreichbar sind.</span><span class="sxs-lookup"><span data-stu-id="10dcf-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="10dcf-242">In den Beispielen wird der Modus "immer umgehen" für die folgenden Szenarien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="10dcf-243">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="10dcf-244">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="10dcf-245">Ausgehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="10dcf-246">Eingehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="10dcf-247">In der folgenden Tabelle sind die in den Beispielen verwendeten FQDN-und IP-Adressen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10dcf-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="10dcf-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="10dcf-248">FQDN</span></span> | <span data-ttu-id="10dcf-249">Externe SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="10dcf-249">SBC external IP address</span></span> | <span data-ttu-id="10dcf-250">Interne SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="10dcf-250">SBC internal IP Address</span></span> | <span data-ttu-id="10dcf-251">Internes Subnetz</span><span class="sxs-lookup"><span data-stu-id="10dcf-251">Internal subnet</span></span> | <span data-ttu-id="10dcf-252">Ort</span><span class="sxs-lookup"><span data-stu-id="10dcf-252">Location</span></span> | <span data-ttu-id="10dcf-253">Externe NAT (vertrauenswürdige IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="10dcf-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="10dcf-255">Keine</span><span class="sxs-lookup"><span data-stu-id="10dcf-255">None</span></span> | <span data-ttu-id="10dcf-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-256">192.168.1.5</span></span> | <span data-ttu-id="10dcf-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="10dcf-257">192.168.1.0/24</span></span> | <span data-ttu-id="10dcf-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="10dcf-258">Vietnam</span></span> | <span data-ttu-id="10dcf-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="10dcf-259">172.16.240.110</span></span> |
| <span data-ttu-id="10dcf-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="10dcf-261">Keine</span><span class="sxs-lookup"><span data-stu-id="10dcf-261">None</span></span> | <span data-ttu-id="10dcf-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-262">192.168.2.5</span></span> | <span data-ttu-id="10dcf-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="10dcf-263">192.168.2.0/24</span></span> | <span data-ttu-id="10dcf-264">Indonesien</span><span class="sxs-lookup"><span data-stu-id="10dcf-264">Indonesia</span></span> | <span data-ttu-id="10dcf-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="10dcf-265">172.16.240.120</span></span> |
| <span data-ttu-id="10dcf-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="10dcf-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="10dcf-267">172.16.240.133</span></span> | <span data-ttu-id="10dcf-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="10dcf-268">192.168.3.5</span></span> | <span data-ttu-id="10dcf-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="10dcf-269">192.168.3.0/24</span></span> | <span data-ttu-id="10dcf-270">Singapur</span><span class="sxs-lookup"><span data-stu-id="10dcf-270">Singapore</span></span> | <span data-ttu-id="10dcf-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="10dcf-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="10dcf-272">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="10dcf-273">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-273">Mode</span></span> |    <span data-ttu-id="10dcf-274">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-274">User</span></span> |  <span data-ttu-id="10dcf-275">Ort</span><span class="sxs-lookup"><span data-stu-id="10dcf-275">Location</span></span> |  <span data-ttu-id="10dcf-276">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="10dcf-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-277">AlwaysBypass</span></span> |    <span data-ttu-id="10dcf-278">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-278">Internal</span></span> |  <span data-ttu-id="10dcf-279">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-279">The same site as SBC</span></span> |  <span data-ttu-id="10dcf-280">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="10dcf-280">Outbound</span></span> |

<span data-ttu-id="10dcf-281">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="10dcf-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="10dcf-282">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="10dcf-282">User physical location</span></span>| <span data-ttu-id="10dcf-283">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="10dcf-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="10dcf-284">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="10dcf-284">User phone number</span></span>  | <span data-ttu-id="10dcf-285">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="10dcf-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="10dcf-286">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="10dcf-287">Vietnam</span></span> | <span data-ttu-id="10dcf-288">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="10dcf-288">+84 4 3926 3000</span></span> | <span data-ttu-id="10dcf-289">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="10dcf-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="10dcf-290">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="10dcf-291">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="10dcf-292">VNsbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="10dcf-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="10dcf-293">proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="10dcf-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="10dcf-294">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit Always Bypass-Modus und den Benutzer am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="10dcf-295">![Diagramm mit ausgehenden Anrufen](media/direct-routing-media-op-10.png "Ausgehende Anrufe")</span><span class="sxs-lookup"><span data-stu-id="10dcf-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="10dcf-296">Die folgende Tabelle zeigt die X-MS-Kopfzeilen, die durch Direct Routing gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="10dcf-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="10dcf-297">Parameter</span><span class="sxs-lookup"><span data-stu-id="10dcf-297">Parameter</span></span> | <span data-ttu-id="10dcf-298">Erklärung</span><span class="sxs-lookup"><span data-stu-id="10dcf-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="10dcf-299">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="10dcf-300">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet</span><span class="sxs-lookup"><span data-stu-id="10dcf-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="10dcf-301">X-MS-UserLocation: intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="10dcf-302">Das Feld hat angegeben, dass sich der Benutzer im Unternehmensnetzwerk befindet</span><span class="sxs-lookup"><span data-stu-id="10dcf-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="10dcf-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="10dcf-304">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="10dcf-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="10dcf-305">In diesem Fall, da wir immer Bypass haben und der Client intern ist, wird der Zielname als einziger Name im Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="10dcf-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="10dcf-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="10dcf-307">Das Feld, das auf der Website angegeben ist, in der sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="10dcf-308">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="10dcf-309">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-309">Mode</span></span> |    <span data-ttu-id="10dcf-310">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-310">User</span></span> |  <span data-ttu-id="10dcf-311">Ort</span><span class="sxs-lookup"><span data-stu-id="10dcf-311">Location</span></span> |  <span data-ttu-id="10dcf-312">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-313">AlwaysBypass</span></span> |    <span data-ttu-id="10dcf-314">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-314">Internal</span></span> | <span data-ttu-id="10dcf-315">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-315">The same site as SBC</span></span> | <span data-ttu-id="10dcf-316">Inbound</span><span class="sxs-lookup"><span data-stu-id="10dcf-316">Inbound</span></span> |


<span data-ttu-id="10dcf-317">Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="10dcf-318">Wenn die Vermutung nicht korrekt ist, wird eine erneute Einladung benötigt.</span><span class="sxs-lookup"><span data-stu-id="10dcf-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="10dcf-319">In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneut einladen).</span><span class="sxs-lookup"><span data-stu-id="10dcf-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="10dcf-320">Der SBC, der mit dem Direct Routing-Dienst verbunden ist, meldet den ursprünglichen SBC-Standort durch Bereitstellen von Daten Satz Routen-und Kontaktfeldern.</span><span class="sxs-lookup"><span data-stu-id="10dcf-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="10dcf-321">Basierend auf diesen Feldern wird der Medienpfad durch direkte Weiterleitung berechnet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="10dcf-322">Hinweis: da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="10dcf-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="10dcf-323">Die direkte Weiterleitung wird in diesem Fall immer 180-Klingeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="10dcf-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="10dcf-324">Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe mit dem AlwaysBypass-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="10dcf-326">Ausgehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="10dcf-327">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-327">Mode</span></span> |    <span data-ttu-id="10dcf-328">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-328">User</span></span> |  <span data-ttu-id="10dcf-329">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-329">Site</span></span> |  <span data-ttu-id="10dcf-330">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="10dcf-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-331">AlwaysBypass</span></span> |  <span data-ttu-id="10dcf-332">Extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-332">External</span></span> |  <span data-ttu-id="10dcf-333">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="10dcf-333">N/A</span></span> | <span data-ttu-id="10dcf-334">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="10dcf-334">Outbound</span></span> |


<span data-ttu-id="10dcf-335">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern:</span><span class="sxs-lookup"><span data-stu-id="10dcf-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-12.png)

<span data-ttu-id="10dcf-337">Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="10dcf-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="10dcf-338">Parameter</span><span class="sxs-lookup"><span data-stu-id="10dcf-338">Parameter</span></span> |   <span data-ttu-id="10dcf-339">Erklärung</span><span class="sxs-lookup"><span data-stu-id="10dcf-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="10dcf-340">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="10dcf-341">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="10dcf-342">X-MS-UserLocation: Extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="10dcf-343">Das Feld hat angegeben, dass der Benutzer sich außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="10dcf-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="10dcf-345">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="10dcf-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="10dcf-346">In diesem Fall, da wir immer Bypass haben und der Client extern ist.</span><span class="sxs-lookup"><span data-stu-id="10dcf-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="10dcf-347">Eingehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="10dcf-348">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-348">Mode</span></span> | <span data-ttu-id="10dcf-349">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-349">User</span></span> | <span data-ttu-id="10dcf-350">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-350">Site</span></span> |  <span data-ttu-id="10dcf-351">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="10dcf-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="10dcf-352">AlwaysBypass</span></span> |  <span data-ttu-id="10dcf-353">Extern</span><span class="sxs-lookup"><span data-stu-id="10dcf-353">External</span></span> |  <span data-ttu-id="10dcf-354">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="10dcf-354">N/A</span></span> |   <span data-ttu-id="10dcf-355">Inbound</span><span class="sxs-lookup"><span data-stu-id="10dcf-355">Inbound</span></span> |

<span data-ttu-id="10dcf-356">Bei einem eingehenden Anruf muss der SBC, der mit dem direkten Routing verbunden ist, eine erneute Einladung senden (Standardmäßig werden lokale Medien Kandidaten immer angeboten), wenn der Standort des Benutzers extern ist.</span><span class="sxs-lookup"><span data-stu-id="10dcf-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="10dcf-357">Die X-MediaPath wird basierend auf der Daten Satz Route und dem angegebenen SBC-Benutzer berechnet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="10dcf-358">Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern.</span><span class="sxs-lookup"><span data-stu-id="10dcf-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="10dcf-360">Nur für den lokalen Benutzermodus</span><span class="sxs-lookup"><span data-stu-id="10dcf-360">Only for local users mode</span></span>

<span data-ttu-id="10dcf-361">Lokale Medien Kandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Ort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="10dcf-362">In allen anderen Fällen fließen Medien entweder über eine interne oder externe IP-Adresse des Proxy-SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="10dcf-363">Die folgenden Szenarien werden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="10dcf-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="10dcf-364">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="10dcf-365">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="10dcf-366">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="10dcf-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="10dcf-367">Eingehende Anrufe und der Benutzer ist intern, aber nicht am selben Ort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="10dcf-368">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="10dcf-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="10dcf-369">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="10dcf-369">User physical location</span></span> |  <span data-ttu-id="10dcf-370">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="10dcf-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="10dcf-371">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="10dcf-371">User phone number</span></span> | <span data-ttu-id="10dcf-372">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="10dcf-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="10dcf-373">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="10dcf-374">Vietnam</span></span> | <span data-ttu-id="10dcf-375">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="10dcf-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="10dcf-376">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="10dcf-376">+84 4 5555 5555</span></span> | <span data-ttu-id="10dcf-377">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="10dcf-378">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10dcf-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="10dcf-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="10dcf-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="10dcf-380">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="10dcf-381">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-381">Mode</span></span> | <span data-ttu-id="10dcf-382">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-382">User</span></span> | <span data-ttu-id="10dcf-383">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-383">Site</span></span> | <span data-ttu-id="10dcf-384">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="10dcf-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="10dcf-386">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-386">Internal</span></span> |<span data-ttu-id="10dcf-387">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-387">Same as SBC</span></span>   | <span data-ttu-id="10dcf-388">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="10dcf-388">Outbound</span></span> |

<span data-ttu-id="10dcf-389">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="10dcf-390">Dies ist derselbe Fluss, der bei [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="10dcf-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="10dcf-392">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="10dcf-393">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-393">Mode</span></span> | <span data-ttu-id="10dcf-394">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-394">User</span></span> | <span data-ttu-id="10dcf-395">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-395">Site</span></span> | <span data-ttu-id="10dcf-396">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="10dcf-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="10dcf-398">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-398">Internal</span></span> | <span data-ttu-id="10dcf-399">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-399">Same as SBC</span></span> | <span data-ttu-id="10dcf-400">Inbound</span><span class="sxs-lookup"><span data-stu-id="10dcf-400">Inbound</span></span> |

<span data-ttu-id="10dcf-401">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="10dcf-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="10dcf-402">Hierbei handelt es sich um denselben Fluss wie in [eingehenden Anrufen, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="10dcf-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="10dcf-404">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk mit nur für lokale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="10dcf-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="10dcf-405">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-405">Mode</span></span> | <span data-ttu-id="10dcf-406">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-406">User</span></span> | <span data-ttu-id="10dcf-407">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-407">Site</span></span> |<span data-ttu-id="10dcf-408">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="10dcf-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="10dcf-410">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-410">Internal</span></span> |   <span data-ttu-id="10dcf-411">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-411">Different from SBC</span></span> | <span data-ttu-id="10dcf-412">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="10dcf-412">Outbound</span></span> |

<span data-ttu-id="10dcf-413">Das direkte Routing berechnet X-MediaPath basierend auf dem gemeldeten Speicherort des Benutzers und des Modus, der für den SBC konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="10dcf-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="10dcf-414">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="10dcf-416">Eingehender Anruf und der Benutzer ist intern, befindet sich aber nicht am gleichen Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="10dcf-417">Modus</span><span class="sxs-lookup"><span data-stu-id="10dcf-417">Mode</span></span> |    <span data-ttu-id="10dcf-418">Benutzer</span><span class="sxs-lookup"><span data-stu-id="10dcf-418">User</span></span> |  <span data-ttu-id="10dcf-419">Standort</span><span class="sxs-lookup"><span data-stu-id="10dcf-419">Site</span></span> |  <span data-ttu-id="10dcf-420">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="10dcf-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="10dcf-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="10dcf-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="10dcf-422">Intern</span><span class="sxs-lookup"><span data-stu-id="10dcf-422">Internal</span></span> |    <span data-ttu-id="10dcf-423">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="10dcf-423">Different from SBC</span></span> |    <span data-ttu-id="10dcf-424">Inbound</span><span class="sxs-lookup"><span data-stu-id="10dcf-424">Inbound</span></span> |

<span data-ttu-id="10dcf-425">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="10dcf-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-17.png)









