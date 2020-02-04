---
title: 'Lync Server 2013: Client- und Serverunterstützung für standortbasiertes Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="65602-102">Client- und Serverunterstützung für standortbasiertes Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65602-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65602-103">_**Letztes Änderungsdatum des Themas:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="65602-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="65602-104">Standortbasiertes Routing wird von lync Server erzwungen.</span><span class="sxs-lookup"><span data-stu-id="65602-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="65602-105">Lync Server kann die Netzwerk Websites identifizieren, über die Benutzer im Unternehmensnetzwerk eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="65602-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="65602-106">Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, werden deren Positionen als unbekannt angesehen.</span><span class="sxs-lookup"><span data-stu-id="65602-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="65602-107">Lync Server-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="65602-107">Lync Server Support</span></span>

<span data-ttu-id="65602-108">Standortbasiertes Routing erfordert, dass lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="65602-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="65602-109">Wenn lync Server 2013 CU1 auf bestimmten lync-Komponenten in der Topologie nicht installiert ist, können standortbasierte Routing Einschränkungen nicht vollständig erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="65602-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="65602-110">In der folgenden Tabelle wird die Kombination aus Serverrollen und Versionen aufgeführt, die für standortbasiertes Routing unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="65602-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65602-111">Poolversion</span><span class="sxs-lookup"><span data-stu-id="65602-111">Pool version</span></span></th>
<th><span data-ttu-id="65602-112">Mediation Server-Version</span><span class="sxs-lookup"><span data-stu-id="65602-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="65602-113">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="65602-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65602-114">Lync Server 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="65602-115">Lync Server 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="65602-116">ja</span><span class="sxs-lookup"><span data-stu-id="65602-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-117">Lync Server 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="65602-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65602-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="65602-119">nein</span><span class="sxs-lookup"><span data-stu-id="65602-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-120">Lync Server 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="65602-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="65602-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="65602-122">nein</span><span class="sxs-lookup"><span data-stu-id="65602-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-123">Lync Server 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="65602-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="65602-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="65602-125">nein</span><span class="sxs-lookup"><span data-stu-id="65602-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65602-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="65602-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="65602-127">any</span></span></p></td>
<td><p><span data-ttu-id="65602-128">nein</span><span class="sxs-lookup"><span data-stu-id="65602-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="65602-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="65602-130">Beliebig</span><span class="sxs-lookup"><span data-stu-id="65602-130">any</span></span></p></td>
<td><p><span data-ttu-id="65602-131">nein</span><span class="sxs-lookup"><span data-stu-id="65602-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="65602-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="65602-133">Beliebig</span><span class="sxs-lookup"><span data-stu-id="65602-133">any</span></span></p></td>
<td><p><span data-ttu-id="65602-134">nein</span><span class="sxs-lookup"><span data-stu-id="65602-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="65602-135">Lync-Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="65602-135">Lync Client Support</span></span>

<span data-ttu-id="65602-136">In der folgenden Tabelle sind die Clients aufgeführt, die vom standortbasierten Routing unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="65602-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65602-137">Clienttyp</span><span class="sxs-lookup"><span data-stu-id="65602-137">Client type</span></span></th>
<th><span data-ttu-id="65602-138">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="65602-138">Supported</span></span></th>
<th><span data-ttu-id="65602-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65602-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65602-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="65602-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="65602-141">ja</span><span class="sxs-lookup"><span data-stu-id="65602-141">yes</span></span></p></td>
<td><p><span data-ttu-id="65602-142">Einschließlich lync 2013 Februar 2013 Kumulatives Update</span><span class="sxs-lookup"><span data-stu-id="65602-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="65602-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="65602-144">ja</span><span class="sxs-lookup"><span data-stu-id="65602-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="65602-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="65602-146">nein</span><span class="sxs-lookup"><span data-stu-id="65602-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="65602-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="65602-148">ja</span><span class="sxs-lookup"><span data-stu-id="65602-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="65602-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="65602-150">ja</span><span class="sxs-lookup"><span data-stu-id="65602-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-151">Lync für Windows 8</span><span class="sxs-lookup"><span data-stu-id="65602-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="65602-152">nein</span><span class="sxs-lookup"><span data-stu-id="65602-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65602-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="65602-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="65602-154">nein</span><span class="sxs-lookup"><span data-stu-id="65602-154">no</span></span></p></td>
<td><p><span data-ttu-id="65602-155">VoIP muss für lync Mobile 2013-Clients deaktiviert sein, wenn Sie von Benutzern mit aktiviertem Standort basiertem Routing verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65602-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65602-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="65602-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="65602-157">ja</span><span class="sxs-lookup"><span data-stu-id="65602-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="65602-158">Wenn Sie VoIP für lync Mobile 2013-Clients deaktivieren möchten, weisen Sie der Einstellung "IP Audio/Video" eine Mobilitätsrichtlinie zu, die für alle Benutzer deaktiviert ist, die für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="65602-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="65602-159">Ausführlichere Informationen zu Mobilitätsrichtlinien finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="65602-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65602-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65602-160">See Also</span></span>


[<span data-ttu-id="65602-161">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65602-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

