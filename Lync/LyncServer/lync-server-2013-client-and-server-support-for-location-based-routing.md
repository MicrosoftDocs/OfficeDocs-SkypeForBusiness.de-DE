---
title: 'Lync Server 2013: Client-und Server Unterstützung für standortbasiertes Routing'
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
ms.openlocfilehash: 3d78ae3fcfe9bd834fbddced1bdeccc20be45481
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="fb7c2-102">Client-und Server Unterstützung für standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb7c2-103">_**Letztes Änderungsstand des Themas:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="fb7c2-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="fb7c2-104">Das standortbasierte Routing wird von lync Server erzwungen.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="fb7c2-105">Lync Server können die Netzwerkstandorte identifizieren, auf denen Benutzer innerhalb des Unternehmensnetzwerks eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="fb7c2-106">Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, wird Ihr Standort als unbekannt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="fb7c2-107">Lync Server Support</span><span class="sxs-lookup"><span data-stu-id="fb7c2-107">Lync Server Support</span></span>

<span data-ttu-id="fb7c2-108">Für das standortbasierte Routing muss lync Server 2013 ku1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="fb7c2-109">Wenn lync Server 2013 ku1 nicht auf bestimmten lync-Komponenten in der Topologie installiert ist, können standortbasierte Routing Einschränkungen nicht vollständig erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="fb7c2-110">In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die für das standortbasierte Routing unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb7c2-111">Pool Version</span><span class="sxs-lookup"><span data-stu-id="fb7c2-111">Pool version</span></span></th>
<th><span data-ttu-id="fb7c2-112">Vermittlungsserver Version</span><span class="sxs-lookup"><span data-stu-id="fb7c2-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="fb7c2-113">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb7c2-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-114">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-115">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-116">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-117">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-119">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-120">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fb7c2-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-122">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-123">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fb7c2-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-125">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-127">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="fb7c2-127">any</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-128">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fb7c2-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-130">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="fb7c2-130">any</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-131">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fb7c2-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-133">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="fb7c2-133">any</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-134">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="fb7c2-135">Lync-Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="fb7c2-135">Lync Client Support</span></span>

<span data-ttu-id="fb7c2-136">In der folgenden Tabelle werden die Clients aufgeführt, die standortbasiertes Routing unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb7c2-137">Clienttyp</span><span class="sxs-lookup"><span data-stu-id="fb7c2-137">Client type</span></span></th>
<th><span data-ttu-id="fb7c2-138">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb7c2-138">Supported</span></span></th>
<th><span data-ttu-id="fb7c2-139">Details</span><span class="sxs-lookup"><span data-stu-id="fb7c2-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-141">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-141">yes</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-142">Einschließlich lync 2013 Kumulatives Update vom 2013. Februar</span><span class="sxs-lookup"><span data-stu-id="fb7c2-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="fb7c2-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-144">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fb7c2-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-146">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="fb7c2-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-148">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="fb7c2-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-150">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-151">Lync für Windows 8</span><span class="sxs-lookup"><span data-stu-id="fb7c2-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-152">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb7c2-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-154">Nein</span><span class="sxs-lookup"><span data-stu-id="fb7c2-154">no</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-155">VoIP muss für lync Mobile 2013-Clients deaktiviert werden, wenn Sie von Benutzern mit aktiviertem Standort basiertem Routing verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb7c2-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="fb7c2-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="fb7c2-157">ja</span><span class="sxs-lookup"><span data-stu-id="fb7c2-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="fb7c2-158">Wenn Sie VoIP für lync Mobile 2013-Clients deaktivieren möchten, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung IP-Audio/Video zu, die für alle Benutzer deaktiviert ist, die für das standortbasierte Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="fb7c2-159">Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb7c2-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb7c2-160">See Also</span></span>


[<span data-ttu-id="fb7c2-161">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7c2-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

