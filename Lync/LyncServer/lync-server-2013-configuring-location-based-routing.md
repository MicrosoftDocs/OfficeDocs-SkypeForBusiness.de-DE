---
title: 'Lync Server 2013: Konfigurieren des Location-Based Routings'
description: 'Lync Server 2013: Konfigurieren des Location-Based Routings.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570881"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="236ce-103">Konfigurieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236ce-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="236ce-104">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="236ce-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="236ce-105">Lync Server 2013 ku1 ist Location-Based Routing ein Feature von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="236ce-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="236ce-106">Location-Based Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 ku1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="236ce-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="236ce-107">Es erzwingt Einschränkungen, ob Anrufe basierend auf dem Standort des lync-Anrufers an PBX-oder PSTN-Ziele weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="236ce-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="236ce-108">Location-Based Routing wendet Anruf Autorisierungsregeln basierend auf dem Netzwerkstandort des Anrufers auf PSTN-Anrufe an.</span><span class="sxs-lookup"><span data-stu-id="236ce-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="236ce-109">Der Speicherort des Anrufers wird basierend auf dem Netzwerkstandort bestimmt, der dem Netzwerk Subnetz zugeordnet ist, mit dem der Anrufer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="236ce-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="236ce-110">Zum Konfigurieren Location-Based Routings müssen Sie zunächst Enterprise-VoIP bereitstellen und dann netzwerkregionen, Standorte und Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="236ce-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="236ce-111">Dadurch wird die Grundlage für die Aktivierung Location-Based Routings eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="236ce-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="236ce-112">Vor der Bereitstellung Location-Based Routing müssen Sie zunächst Enterprise-VoIP bereitstellen und netzwerkregionen,-Standorte und Netzwerk-Subnetze ihren Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="236ce-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="236ce-113">Nach Abschluss des Vorgangs können Sie Location-Based Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="236ce-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="236ce-114">Schritte zum Konfigurieren von netzwerkregionen, Standorten und Subnetzen finden Sie unter [Deploying Advanced Enterprise Voice Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="236ce-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="236ce-115">Dieser Abschnitt führt Sie durch die Konfiguration von Location-Based Routing mit dem folgenden Beispiel als Illustration.</span><span class="sxs-lookup"><span data-stu-id="236ce-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="236ce-116">![Beispiel für Enterprise-VoIP-standortbasiertes Routing](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Beispiel für Enterprise-VoIP-standortbasiertes Routing")</span><span class="sxs-lookup"><span data-stu-id="236ce-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="236ce-117">In der folgenden Tabelle werden die in diesem Beispiel definierten Benutzer dargestellt.</span><span class="sxs-lookup"><span data-stu-id="236ce-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="236ce-118">Endpunkttyp</span><span class="sxs-lookup"><span data-stu-id="236ce-118">Endpoint type</span></span></th>
<th><span data-ttu-id="236ce-119">Standort</span><span class="sxs-lookup"><span data-stu-id="236ce-119">Location</span></span></th>
<th><span data-ttu-id="236ce-120">Benutzer</span><span class="sxs-lookup"><span data-stu-id="236ce-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="236ce-121">Lync</span><span class="sxs-lookup"><span data-stu-id="236ce-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="236ce-122">Unternehmenszentrale in Delhi</span><span class="sxs-lookup"><span data-stu-id="236ce-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="236ce-123">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="236ce-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-124">Lync</span><span class="sxs-lookup"><span data-stu-id="236ce-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="236ce-125">Firmenzentrale in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="236ce-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="236ce-126">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="236ce-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236ce-127">Lync</span><span class="sxs-lookup"><span data-stu-id="236ce-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="236ce-128">Unbekannt (d. h. Hotel)</span><span class="sxs-lookup"><span data-stu-id="236ce-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="236ce-129">Unk-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="236ce-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-130">PBX</span><span class="sxs-lookup"><span data-stu-id="236ce-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="236ce-131">Unternehmenszentrale in Delhi</span><span class="sxs-lookup"><span data-stu-id="236ce-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="236ce-132">Del-PBX-1, del-PBX-2</span><span class="sxs-lookup"><span data-stu-id="236ce-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236ce-133">PBX</span><span class="sxs-lookup"><span data-stu-id="236ce-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="236ce-134">Firmenzentrale in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="236ce-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="236ce-135">Hyd-PBX-1, Hyd-PBX-2</span><span class="sxs-lookup"><span data-stu-id="236ce-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-136">PSTN</span><span class="sxs-lookup"><span data-stu-id="236ce-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="236ce-137">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="236ce-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="236ce-138">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="236ce-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="236ce-139">Die folgende Tabelle stellt die in dieser Beispielumgebung dargestellten Systeme dar.</span><span class="sxs-lookup"><span data-stu-id="236ce-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="236ce-140">System</span><span class="sxs-lookup"><span data-stu-id="236ce-140">System</span></span></th>
<th><span data-ttu-id="236ce-141">Standort</span><span class="sxs-lookup"><span data-stu-id="236ce-141">Location</span></span></th>
<th><span data-ttu-id="236ce-142">Name</span><span class="sxs-lookup"><span data-stu-id="236ce-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="236ce-143">Lync Server 2013 ku1-Pool</span><span class="sxs-lookup"><span data-stu-id="236ce-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="236ce-144">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="236ce-144">any</span></span></p></td>
<td><p><span data-ttu-id="236ce-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="236ce-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-146">Lync Server 2013 ku1, Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="236ce-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="236ce-147">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="236ce-147">any</span></span></p></td>
<td><p><span data-ttu-id="236ce-148">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="236ce-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236ce-149">PSTN-Gateway 1</span><span class="sxs-lookup"><span data-stu-id="236ce-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="236ce-150">Delhi</span><span class="sxs-lookup"><span data-stu-id="236ce-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="236ce-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="236ce-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-152">PSTN-Gateway 2</span><span class="sxs-lookup"><span data-stu-id="236ce-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="236ce-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="236ce-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="236ce-154">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="236ce-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236ce-155">Nebenstellenanlage 1</span><span class="sxs-lookup"><span data-stu-id="236ce-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="236ce-156">Delhi</span><span class="sxs-lookup"><span data-stu-id="236ce-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="236ce-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="236ce-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236ce-158">Nebenstellenanlage 2</span><span class="sxs-lookup"><span data-stu-id="236ce-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="236ce-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="236ce-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="236ce-160">Red-PBX</span><span class="sxs-lookup"><span data-stu-id="236ce-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="236ce-161">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="236ce-161">In This Section</span></span>

  - [<span data-ttu-id="236ce-162">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236ce-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="236ce-163">Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236ce-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="236ce-164">Aktivieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236ce-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="236ce-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="236ce-165">See Also</span></span>


[<span data-ttu-id="236ce-166">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236ce-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

