---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358921"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="701bd-103">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="701bd-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="701bd-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="701bd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="701bd-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="701bd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="701bd-106">Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="701bd-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="701bd-107">In diesem Abschnitt wird beschrieben, wie mehrere PSTN-Standorte (Public Switched Telephone Network) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="701bd-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="701bd-108">Websites werden jeweils einzeln bereitgestellt, wobei dieselben Schritte wie bei der Bereitstellungeines einzelnen Standorts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="701bd-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="701bd-109">In diesem Thema werden die Überlegungen und Unterschiede zwischen Websites in einer Bereitstellung mit mehreren Websites beschrieben.</span><span class="sxs-lookup"><span data-stu-id="701bd-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="701bd-110">Mehrere PSTN-Standorte (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="701bd-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="701bd-111">Im folgenden finden Sie eine Beispielkonfiguration für die Bereitstellung Skype for Business Cloud Connector Edition für verschiedene PSTN-Standorte.</span><span class="sxs-lookup"><span data-stu-id="701bd-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="701bd-112">Stellen Sie sicher, dass Ihre Konfigurationseinstellungen korrekt sind, bevor Sie eine Bereitstellung starten.</span><span class="sxs-lookup"><span data-stu-id="701bd-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="701bd-113">PSTN-Standort 1</span><span class="sxs-lookup"><span data-stu-id="701bd-113">PSTN Site 1</span></span>
  
```console
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

<span data-ttu-id="701bd-114">PSTN-Standort 2</span><span class="sxs-lookup"><span data-stu-id="701bd-114">PSTN Site 2</span></span>
  
```console
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

<span data-ttu-id="701bd-115">Führen Sie für jeden hinzuzufügenden PSTN-Standort die Schritte unter [Deploy an Single Site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)aus.</span><span class="sxs-lookup"><span data-stu-id="701bd-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="701bd-116">Der freigegebene Ordner zur Vorbereitung der Hochverfügbarkeit (ha) ist pro PSTN-Standort.</span><span class="sxs-lookup"><span data-stu-id="701bd-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="701bd-117">Der freigegebene Ordner **muss** zwischen PSTN-Standorten unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="701bd-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="701bd-118">Verwenden Sie nicht denselben freigegebenen Ordner für mehrere Websites. ></span><span class="sxs-lookup"><span data-stu-id="701bd-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="701bd-119">Einzelner Standort mit hoher Verfügbarkeit (ha) im Vergleich zu Bereitstellungen mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="701bd-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="701bd-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="701bd-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="701bd-121">In der folgenden Tabelle sind die Unterschiede zwischen einem einzelnen Standort mit ha-Unterstützung und einer Bereitstellung mit mehreren Standorten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="701bd-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="701bd-122">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="701bd-122">**Category**</span></span>|<span data-ttu-id="701bd-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="701bd-123">**Item**</span></span>|<span data-ttu-id="701bd-124">**Single-Site mit ha**</span><span class="sxs-lookup"><span data-stu-id="701bd-124">**Single-Site with HA**</span></span>|<span data-ttu-id="701bd-125">**Multi-Site**</span><span class="sxs-lookup"><span data-stu-id="701bd-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="701bd-126">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-126">Configure</span></span>  <br/> |<span data-ttu-id="701bd-127">Name der Appliance-Host</span><span class="sxs-lookup"><span data-stu-id="701bd-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="701bd-128">**Unterschiedliche** Across Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="701bd-129">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-130">Setup</span><span class="sxs-lookup"><span data-stu-id="701bd-130">Setup</span></span>  <br/> |<span data-ttu-id="701bd-131">Freigegebener Ordner</span><span class="sxs-lookup"><span data-stu-id="701bd-131">Shared folder</span></span>  <br/> |<span data-ttu-id="701bd-132">Erfordert **denselben** freigegebenen Ordner für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="701bd-133">Für Appliances ist ein **anderer** freigegebener Ordner erforderlich</span><span class="sxs-lookup"><span data-stu-id="701bd-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="701bd-134">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-134">Configure</span></span>  <br/> |<span data-ttu-id="701bd-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="701bd-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="701bd-136">Erfordert die **gleiche** Domäne für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="701bd-137">Erfordert die **gleiche** Domäne für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-138">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-138">Configure</span></span>  <br/> |<span data-ttu-id="701bd-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="701bd-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="701bd-140">Domänennamen und Reihenfolge sollten in allen Appliances **gleich** sein.</span><span class="sxs-lookup"><span data-stu-id="701bd-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="701bd-141">Domänennamen und Reihenfolge sollten für alle PSTN-Standorte **gleich** sein.</span><span class="sxs-lookup"><span data-stu-id="701bd-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-142">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-142">Configure</span></span>  <br/> |<span data-ttu-id="701bd-143">Websitename</span><span class="sxs-lookup"><span data-stu-id="701bd-143">Site name</span></span>  <br/> |<span data-ttu-id="701bd-144">**Gleiche** Website Name für Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="701bd-145">**Unterschiedliche** Website Name über PSTN-Standorte hinweg</span><span class="sxs-lookup"><span data-stu-id="701bd-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-146">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-146">Configure</span></span>  <br/> |<span data-ttu-id="701bd-147">Server Namen</span><span class="sxs-lookup"><span data-stu-id="701bd-147">Server names</span></span>  <br/> |<span data-ttu-id="701bd-148">**Unterschiedliche** Across Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="701bd-149">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-150">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-150">Configure</span></span>  <br/> |<span data-ttu-id="701bd-151">FQDNs interner Pools</span><span class="sxs-lookup"><span data-stu-id="701bd-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="701bd-152">**Gleich** in allen Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="701bd-153">**Gleich** auf allen PSTN-Standorten</span><span class="sxs-lookup"><span data-stu-id="701bd-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-154">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-154">Configure</span></span>  <br/> |<span data-ttu-id="701bd-155">Interne IPS</span><span class="sxs-lookup"><span data-stu-id="701bd-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="701bd-156">**Unterschiedliche** Across Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="701bd-157">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-158">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-158">Configure</span></span>  <br/> |<span data-ttu-id="701bd-159">Externer FQDN</span><span class="sxs-lookup"><span data-stu-id="701bd-159">External FQDN</span></span>  <br/> |<span data-ttu-id="701bd-160">**Gleich** in allen Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="701bd-161">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-162">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-162">Configure</span></span>  <br/> |<span data-ttu-id="701bd-163">Externe IPS</span><span class="sxs-lookup"><span data-stu-id="701bd-163">External IPs</span></span>  <br/> |<span data-ttu-id="701bd-164">**Unterschiedliche** Across Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="701bd-165">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-166">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-166">Configure</span></span>  <br/> |<span data-ttu-id="701bd-167">PSTN-GW-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="701bd-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="701bd-168">**Gleich** in allen Appliances</span><span class="sxs-lookup"><span data-stu-id="701bd-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="701bd-169">**Unterschiedliches** für PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="701bd-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="701bd-170">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="701bd-170">Configure</span></span>  <br/> |<span data-ttu-id="701bd-171">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="701bd-171">DNS record</span></span>  <br/> |<span data-ttu-id="701bd-172">Hinzufügen von Datensätzen mit **denselben** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="701bd-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="701bd-173">Hinzufügen von Datensätzen mit **verschiedenen** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="701bd-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="701bd-174">Setup</span><span class="sxs-lookup"><span data-stu-id="701bd-174">Setup</span></span>  <br/> |<span data-ttu-id="701bd-175">Hybrid Mandant</span><span class="sxs-lookup"><span data-stu-id="701bd-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="701bd-176">HybridPSTNSite festlegen</span><span class="sxs-lookup"><span data-stu-id="701bd-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="701bd-177">Festlegen von Peer Destination für Fallback</span><span class="sxs-lookup"><span data-stu-id="701bd-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="701bd-178">HybridPSTNSite festlegen</span><span class="sxs-lookup"><span data-stu-id="701bd-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="701bd-179">Festlegen von Peer Destination für Fallback</span><span class="sxs-lookup"><span data-stu-id="701bd-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="701bd-180">Setup</span><span class="sxs-lookup"><span data-stu-id="701bd-180">Setup</span></span>  <br/> |<span data-ttu-id="701bd-181">Gateway</span><span class="sxs-lookup"><span data-stu-id="701bd-181">Gateway</span></span>  <br/> |<span data-ttu-id="701bd-182">MS GW **m:n-trunk** -Zuordnung auf dieser Website</span><span class="sxs-lookup"><span data-stu-id="701bd-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="701bd-183">PSTN-Gateways an jedem PSTN-Standort sollten nur eine Verbindung mit dem Vermittlungsserver am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="701bd-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="701bd-184">Setup</span><span class="sxs-lookup"><span data-stu-id="701bd-184">Setup</span></span>  <br/> |<span data-ttu-id="701bd-185">Benutzer</span><span class="sxs-lookup"><span data-stu-id="701bd-185">User</span></span>  <br/> |<span data-ttu-id="701bd-186">UserPSTNSettings festlegen</span><span class="sxs-lookup"><span data-stu-id="701bd-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="701bd-187">UserPSTNSettings festlegen</span><span class="sxs-lookup"><span data-stu-id="701bd-187">Set UserPSTNSettings</span></span>  <br/> |
   

