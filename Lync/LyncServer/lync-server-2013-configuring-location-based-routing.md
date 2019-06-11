---
title: 'Lync Server 2013: Konfigurieren von standortbasiertem Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="83df0-102">Konfigurieren von standortbasiertem Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83df0-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83df0-103">_**Letztes Änderungsdatum des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="83df0-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="83df0-104">Lync Server 2013 CU1, standortbasiertes Routing ist eine Funktion von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="83df0-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="83df0-105">Standortbasiertes Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 CU1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="83df0-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="83df0-106">Sie erzwingt Einschränkungen, ob Anrufe an PBX-oder PSTN-Ziele basierend auf dem Standort des lync-Anrufers weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="83df0-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="83df0-107">Standortbasiertes Routing wendet Anruf Autorisierungsregeln für PSTN-Anrufe auf der Grundlage des Netzwerkspeicherorts des Anrufers an.</span><span class="sxs-lookup"><span data-stu-id="83df0-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="83df0-108">Der Standort des Anrufers wird anhand der Netzwerk Website bestimmt, die dem Netzwerk-Subnetz zugeordnet ist, an dem der Anrufer angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="83df0-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="83df0-109">Zum Konfigurieren des standortbasierten Routings muss zuerst Enterprise-VoIP bereitgestellt und dann netzwerkregionen,-Standorte und-Subnetze konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="83df0-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="83df0-110">Damit wird die Grundlage für die Aktivierung des standortbasierten Routings eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="83df0-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="83df0-111">Vor der Bereitstellung von Standort basiertem Routing müssen Sie zuerst Enterprise-VoIP bereitstellen und netzwerkregionen,-Standorte und Netzwerk-Subnetze an Ihre Netzwerk Websites anschließen.</span><span class="sxs-lookup"><span data-stu-id="83df0-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="83df0-112">Nach Abschluss des Vorgangs können Sie standortbasiertes Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="83df0-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="83df0-113">Eine schrittweise Anleitung zum Konfigurieren von netzwerkregionen,-Websites und-Subnetzen finden Sie unter [Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="83df0-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="83df0-114">Dieser Abschnitt führt Sie durch die Konfiguration des standortbasierten Routings mit dem folgenden Beispiel als Abbildung.</span><span class="sxs-lookup"><span data-stu-id="83df0-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="83df0-115">![Beispiel für standortbasiertes Routing für Enterprise-VoIP] (images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Beispiel für standortbasiertes Routing für Enterprise-VoIP")</span><span class="sxs-lookup"><span data-stu-id="83df0-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="83df0-116">In der folgenden Tabelle sind die in diesem Beispiel definierten Benutzer dargestellt.</span><span class="sxs-lookup"><span data-stu-id="83df0-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83df0-117">Endpunkttyp</span><span class="sxs-lookup"><span data-stu-id="83df0-117">Endpoint type</span></span></th>
<th><span data-ttu-id="83df0-118">Ort</span><span class="sxs-lookup"><span data-stu-id="83df0-118">Location</span></span></th>
<th><span data-ttu-id="83df0-119">Nutzer</span><span class="sxs-lookup"><span data-stu-id="83df0-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83df0-120">Lync</span><span class="sxs-lookup"><span data-stu-id="83df0-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="83df0-121">Firmensitz in Delhi</span><span class="sxs-lookup"><span data-stu-id="83df0-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="83df0-122">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="83df0-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-123">Lync</span><span class="sxs-lookup"><span data-stu-id="83df0-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="83df0-124">Firmensitz in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83df0-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="83df0-125">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="83df0-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83df0-126">Lync</span><span class="sxs-lookup"><span data-stu-id="83df0-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="83df0-127">Unbekannt (z.b. Hotel)</span><span class="sxs-lookup"><span data-stu-id="83df0-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="83df0-128">Unk-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="83df0-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-129">PBX</span><span class="sxs-lookup"><span data-stu-id="83df0-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="83df0-130">Firmensitz in Delhi</span><span class="sxs-lookup"><span data-stu-id="83df0-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="83df0-131">Del-PBX-1, del-PBX-2</span><span class="sxs-lookup"><span data-stu-id="83df0-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83df0-132">PBX</span><span class="sxs-lookup"><span data-stu-id="83df0-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="83df0-133">Firmensitz in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83df0-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="83df0-134">Hyd-PBX-1, Hyd-PBX-2</span><span class="sxs-lookup"><span data-stu-id="83df0-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-135">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="83df0-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="83df0-136">Unbekannten</span><span class="sxs-lookup"><span data-stu-id="83df0-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="83df0-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="83df0-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="83df0-138">In der folgenden Tabelle sind die in dieser Beispielumgebung dargestellten Systeme dargestellt.</span><span class="sxs-lookup"><span data-stu-id="83df0-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83df0-139">System</span><span class="sxs-lookup"><span data-stu-id="83df0-139">System</span></span></th>
<th><span data-ttu-id="83df0-140">Ort</span><span class="sxs-lookup"><span data-stu-id="83df0-140">Location</span></span></th>
<th><span data-ttu-id="83df0-141">Name</span><span class="sxs-lookup"><span data-stu-id="83df0-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83df0-142">Lync Server 2013 CU1-Pool</span><span class="sxs-lookup"><span data-stu-id="83df0-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="83df0-143">Beliebig</span><span class="sxs-lookup"><span data-stu-id="83df0-143">any</span></span></p></td>
<td><p><span data-ttu-id="83df0-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="83df0-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-145">Lync Server 2013 CU1, Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="83df0-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="83df0-146">Beliebig</span><span class="sxs-lookup"><span data-stu-id="83df0-146">any</span></span></p></td>
<td><p><span data-ttu-id="83df0-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="83df0-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83df0-148">PSTN-Gateway 1</span><span class="sxs-lookup"><span data-stu-id="83df0-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="83df0-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="83df0-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="83df0-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="83df0-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-151">PSTN-Gateway 2</span><span class="sxs-lookup"><span data-stu-id="83df0-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="83df0-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83df0-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="83df0-153">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="83df0-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83df0-154">Telefonanlage 1</span><span class="sxs-lookup"><span data-stu-id="83df0-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="83df0-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="83df0-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="83df0-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="83df0-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83df0-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="83df0-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="83df0-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83df0-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="83df0-159">Red-PBX</span><span class="sxs-lookup"><span data-stu-id="83df0-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="83df0-160">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="83df0-160">In This Section</span></span>

  - [<span data-ttu-id="83df0-161">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83df0-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="83df0-162">Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83df0-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="83df0-163">Aktivieren des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83df0-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83df0-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83df0-164">See Also</span></span>


[<span data-ttu-id="83df0-165">Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83df0-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

