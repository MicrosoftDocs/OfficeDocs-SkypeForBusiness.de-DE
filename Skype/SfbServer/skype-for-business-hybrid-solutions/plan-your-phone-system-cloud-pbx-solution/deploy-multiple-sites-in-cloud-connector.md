---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.
ms.openlocfilehash: b6d4c489136f038a5d4dbe7188958ef60e4a5aed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295713"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="03583-103">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="03583-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="03583-104">Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="03583-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="03583-p101">In diesem Abschnitt wird die Bereitstellung mehrerer PSTN-Standorte (Public Switched Telephone Network, Telefonfestnetz) erläutert. Standorte werden jeweils nacheinander wie bei der Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden Überlegungen zu Standorten und Unterschiede zwischen Standorten in einer Bereitstellung mit mehreren Standorten beschrieben. </span><span class="sxs-lookup"><span data-stu-id="03583-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="03583-108">Mehrere PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="03583-109">Die folgende Abbildung zeigt eine Beispielkonfiguration Skype für Business Cloud Connector Edition für andere PSTN-Websites bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="03583-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="03583-110">Stellen Sie vor dem Starten der Bereitstellung sicher, dass Ihre Konfigurationseinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="03583-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="03583-111">PSTN-Standort 1</span><span class="sxs-lookup"><span data-stu-id="03583-111">PSTN Site 1</span></span>
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="03583-112">PSTN-Standort 2</span><span class="sxs-lookup"><span data-stu-id="03583-112">PSTN Site 2</span></span>
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="03583-113">Führen Sie für jede PSTN-Website, die Sie hinzufügen möchten die Schritte unter [Deploy einer einzelnen Website in der Cloud-Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="03583-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03583-114">Der freigegebene Ordner für die Vorbereitung hoher Verfügbarkeit wird pro PSTN-Standort erstellt.</span><span class="sxs-lookup"><span data-stu-id="03583-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="03583-115">Der freigegebene Ordner **muss** sich zwischen den PSTN-Standorten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="03583-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="03583-116">Verwenden Sie nicht den gleichen freigegebenen Ordner für mehrere Websites. ></span><span class="sxs-lookup"><span data-stu-id="03583-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="03583-117">Bereitstellung eines einzelnen Standorts mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="03583-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="03583-118"></span></span>

<span data-ttu-id="03583-119">In der folgenden Tabelle sind die Unterschiede zwischen der Bereitstellung an einem einzelnen Standort mit hoher Verfügbarkeit und der Bereitstellung an mehreren Standorten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="03583-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="03583-120">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="03583-120">**Category**</span></span>|<span data-ttu-id="03583-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="03583-121">**Item**</span></span>|<span data-ttu-id="03583-122">**Einzelner Standort mit hoher Verfügbarkeit**</span><span class="sxs-lookup"><span data-stu-id="03583-122">**Single-Site with HA**</span></span>|<span data-ttu-id="03583-123">**Mehrere Standorte**</span><span class="sxs-lookup"><span data-stu-id="03583-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="03583-124">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="03583-124">Setup</span></span>  <br/> |<span data-ttu-id="03583-125">Freigegebener Ordner</span><span class="sxs-lookup"><span data-stu-id="03583-125">Shared folder</span></span>  <br/> |<span data-ttu-id="03583-126">Erfordert den **gleiche** freigegebenen Ordner mehreren appliances</span><span class="sxs-lookup"><span data-stu-id="03583-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="03583-127">Benötigt für jede Appliance einen **unterschiedlichen** freigegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="03583-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="03583-128">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-128">Configure</span></span>  <br/> |<span data-ttu-id="03583-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="03583-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="03583-130">Benötigt für alle Appliances **dieselbe** Domäne.</span><span class="sxs-lookup"><span data-stu-id="03583-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="03583-131">Benötigt **dieselbe** Domäne für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-132">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-132">Configure</span></span>  <br/> |<span data-ttu-id="03583-133">SIP-Domänen</span><span class="sxs-lookup"><span data-stu-id="03583-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="03583-134">Domänennamen und der Reihenfolge sollte sein die **gleichen** mehreren appliances</span><span class="sxs-lookup"><span data-stu-id="03583-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="03583-135">Domänennamen und der Reihenfolge sollte sein die **gleichen** PSTN-websiteübergreifenden</span><span class="sxs-lookup"><span data-stu-id="03583-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-136">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-136">Configure</span></span>  <br/> |<span data-ttu-id="03583-137">Standortname</span><span class="sxs-lookup"><span data-stu-id="03583-137">Site name</span></span>  <br/> |<span data-ttu-id="03583-138">**Identischer** Standortname für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="03583-139">**Unterschiedlicher** Standortname für jeden einzelnen PSTN-Standort</span><span class="sxs-lookup"><span data-stu-id="03583-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-140">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-140">Configure</span></span>  <br/> |<span data-ttu-id="03583-141">Servernamen</span><span class="sxs-lookup"><span data-stu-id="03583-141">Server names</span></span>  <br/> |<span data-ttu-id="03583-142">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="03583-143">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-144">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-144">Configure</span></span>  <br/> |<span data-ttu-id="03583-145">FQDNs interner Pools</span><span class="sxs-lookup"><span data-stu-id="03583-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="03583-146">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="03583-147">**Identisch** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-148">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-148">Configure</span></span>  <br/> |<span data-ttu-id="03583-149">Interne IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="03583-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="03583-150">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="03583-151">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-152">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-152">Configure</span></span>  <br/> |<span data-ttu-id="03583-153">Externer FQDN</span><span class="sxs-lookup"><span data-stu-id="03583-153">External FQDN</span></span>  <br/> |<span data-ttu-id="03583-154">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="03583-155">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-156">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-156">Configure</span></span>  <br/> |<span data-ttu-id="03583-157">Externe IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="03583-157">External IPs</span></span>  <br/> |<span data-ttu-id="03583-158">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="03583-159">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-160">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-160">Configure</span></span>  <br/> |<span data-ttu-id="03583-161">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="03583-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="03583-162">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="03583-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="03583-163">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="03583-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="03583-164">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03583-164">Configure</span></span>  <br/> |<span data-ttu-id="03583-165">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="03583-165">DNS record</span></span>  <br/> |<span data-ttu-id="03583-166">Hinzufügen von Datensätzen mit der **gleichen** externen Zugriff FQDNs und **verschiedene** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="03583-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="03583-167">Datensätze mit **unterschiedlichen** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="03583-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="03583-168">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="03583-168">Setup</span></span>  <br/> |<span data-ttu-id="03583-169">Hybrid-Mandanten</span><span class="sxs-lookup"><span data-stu-id="03583-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="03583-170">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="03583-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="03583-171">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="03583-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="03583-172">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="03583-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="03583-173">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="03583-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="03583-174">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="03583-174">Setup</span></span>  <br/> |<span data-ttu-id="03583-175">Gateway</span><span class="sxs-lookup"><span data-stu-id="03583-175">Gateway</span></span>  <br/> |<span data-ttu-id="03583-176">Vermittlungsserver-Gateway **M:N**-Zuordnung an diesem Standort</span><span class="sxs-lookup"><span data-stu-id="03583-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="03583-177">PSTN-Gateways an den einzelnen PSTN-Standorten sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="03583-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="03583-178">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="03583-178">Setup</span></span>  <br/> |<span data-ttu-id="03583-179">Benutzer</span><span class="sxs-lookup"><span data-stu-id="03583-179">User</span></span>  <br/> |<span data-ttu-id="03583-180">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="03583-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="03583-181">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="03583-181">Set UserPSTNSettings</span></span>  <br/> |
   

