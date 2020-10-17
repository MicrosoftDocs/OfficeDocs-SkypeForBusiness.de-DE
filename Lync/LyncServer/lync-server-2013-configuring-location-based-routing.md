---
title: 'Lync Server 2013: Konfigurieren des Location-Based Routings'
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
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517415"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b1548-102">Konfigurieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1548-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1548-103">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="b1548-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="b1548-104">Lync Server 2013 ku1 ist Location-Based Routing ein Feature von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="b1548-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="b1548-105">Location-Based Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 ku1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b1548-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="b1548-106">Es erzwingt Einschränkungen, ob Anrufe basierend auf dem Standort des lync-Anrufers an PBX-oder PSTN-Ziele weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="b1548-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="b1548-107">Location-Based Routing wendet Anruf Autorisierungsregeln basierend auf dem Netzwerkstandort des Anrufers auf PSTN-Anrufe an.</span><span class="sxs-lookup"><span data-stu-id="b1548-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="b1548-108">Der Speicherort des Anrufers wird basierend auf dem Netzwerkstandort bestimmt, der dem Netzwerk Subnetz zugeordnet ist, mit dem der Anrufer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b1548-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="b1548-109">Zum Konfigurieren Location-Based Routings müssen Sie zunächst Enterprise-VoIP bereitstellen und dann netzwerkregionen, Standorte und Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b1548-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="b1548-110">Dadurch wird die Grundlage für die Aktivierung Location-Based Routings eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b1548-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="b1548-111">Vor der Bereitstellung Location-Based Routing müssen Sie zunächst Enterprise-VoIP bereitstellen und netzwerkregionen,-Standorte und Netzwerk-Subnetze ihren Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b1548-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="b1548-112">Nach Abschluss des Vorgangs können Sie Location-Based Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b1548-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="b1548-113">Schritte zum Konfigurieren von netzwerkregionen, Standorten und Subnetzen finden Sie unter [Deploying Advanced Enterprise Voice Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="b1548-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="b1548-114">Dieser Abschnitt führt Sie durch die Konfiguration von Location-Based Routing mit dem folgenden Beispiel als Illustration.</span><span class="sxs-lookup"><span data-stu-id="b1548-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="b1548-115">![Beispiel für Enterprise-VoIP-standortbasiertes Routing](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Beispiel für Enterprise-VoIP-standortbasiertes Routing")</span><span class="sxs-lookup"><span data-stu-id="b1548-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="b1548-116">In der folgenden Tabelle werden die in diesem Beispiel definierten Benutzer dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b1548-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1548-117">Endpunkttyp</span><span class="sxs-lookup"><span data-stu-id="b1548-117">Endpoint type</span></span></th>
<th><span data-ttu-id="b1548-118">Standort</span><span class="sxs-lookup"><span data-stu-id="b1548-118">Location</span></span></th>
<th><span data-ttu-id="b1548-119">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b1548-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1548-120">Lync</span><span class="sxs-lookup"><span data-stu-id="b1548-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="b1548-121">Unternehmenszentrale in Delhi</span><span class="sxs-lookup"><span data-stu-id="b1548-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="b1548-122">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="b1548-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-123">Lync</span><span class="sxs-lookup"><span data-stu-id="b1548-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="b1548-124">Firmenzentrale in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="b1548-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="b1548-125">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="b1548-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1548-126">Lync</span><span class="sxs-lookup"><span data-stu-id="b1548-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="b1548-127">Unbekannt (d. h. Hotel)</span><span class="sxs-lookup"><span data-stu-id="b1548-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="b1548-128">Unk-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="b1548-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-129">PBX</span><span class="sxs-lookup"><span data-stu-id="b1548-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="b1548-130">Unternehmenszentrale in Delhi</span><span class="sxs-lookup"><span data-stu-id="b1548-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="b1548-131">Del-PBX-1, del-PBX-2</span><span class="sxs-lookup"><span data-stu-id="b1548-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1548-132">PBX</span><span class="sxs-lookup"><span data-stu-id="b1548-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="b1548-133">Firmenzentrale in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="b1548-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="b1548-134">Hyd-PBX-1, Hyd-PBX-2</span><span class="sxs-lookup"><span data-stu-id="b1548-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="b1548-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="b1548-136">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b1548-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="b1548-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="b1548-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="b1548-138">Die folgende Tabelle stellt die in dieser Beispielumgebung dargestellten Systeme dar.</span><span class="sxs-lookup"><span data-stu-id="b1548-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1548-139">System</span><span class="sxs-lookup"><span data-stu-id="b1548-139">System</span></span></th>
<th><span data-ttu-id="b1548-140">Standort</span><span class="sxs-lookup"><span data-stu-id="b1548-140">Location</span></span></th>
<th><span data-ttu-id="b1548-141">Name</span><span class="sxs-lookup"><span data-stu-id="b1548-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1548-142">Lync Server 2013 ku1-Pool</span><span class="sxs-lookup"><span data-stu-id="b1548-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="b1548-143">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="b1548-143">any</span></span></p></td>
<td><p><span data-ttu-id="b1548-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="b1548-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-145">Lync Server 2013 ku1, Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b1548-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b1548-146">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="b1548-146">any</span></span></p></td>
<td><p><span data-ttu-id="b1548-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="b1548-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1548-148">PSTN-Gateway 1</span><span class="sxs-lookup"><span data-stu-id="b1548-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="b1548-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="b1548-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="b1548-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="b1548-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-151">PSTN-Gateway 2</span><span class="sxs-lookup"><span data-stu-id="b1548-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="b1548-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="b1548-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="b1548-153">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="b1548-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1548-154">Nebenstellenanlage 1</span><span class="sxs-lookup"><span data-stu-id="b1548-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="b1548-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="b1548-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="b1548-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="b1548-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1548-157">Nebenstellenanlage 2</span><span class="sxs-lookup"><span data-stu-id="b1548-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="b1548-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="b1548-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="b1548-159">Red-PBX</span><span class="sxs-lookup"><span data-stu-id="b1548-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="b1548-160">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b1548-160">In This Section</span></span>

  - [<span data-ttu-id="b1548-161">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1548-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="b1548-162">Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1548-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="b1548-163">Aktivieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1548-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1548-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1548-164">See Also</span></span>


[<span data-ttu-id="b1548-165">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1548-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

