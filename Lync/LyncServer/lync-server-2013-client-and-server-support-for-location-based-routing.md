---
title: 'Lync Server 2013: Client-und Server Unterstützung für Location-Based Routing'
description: 'Lync Server 2013: Client-und Server Unterstützung für Location-Based Routing.'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549631"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4c2c7-103">Client-und Server Unterstützung für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c2c7-104">_**Letztes Änderungsstand des Themas:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="4c2c7-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="4c2c7-105">Location-Based Routing wird von lync Server erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="4c2c7-106">Lync Server können die Netzwerkstandorte identifizieren, auf denen Benutzer innerhalb des Unternehmensnetzwerks eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="4c2c7-107">Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, wird Ihr Standort als unbekannt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="4c2c7-108">Lync Server Support</span><span class="sxs-lookup"><span data-stu-id="4c2c7-108">Lync Server Support</span></span>

<span data-ttu-id="4c2c7-109">Für Location-Based Routing ist es erforderlich, dass lync Server 2013 ku1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="4c2c7-110">Wenn lync Server 2013 ku1 nicht auf bestimmten lync-Komponenten in der Topologie installiert ist, können Location-Based Routing Einschränkungen nicht vollständig erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="4c2c7-111">In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die für Location-Based Routing unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c2c7-112">Pool Version</span><span class="sxs-lookup"><span data-stu-id="4c2c7-112">Pool version</span></span></th>
<th><span data-ttu-id="4c2c7-113">Vermittlungsserver Version</span><span class="sxs-lookup"><span data-stu-id="4c2c7-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="4c2c7-114">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="4c2c7-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-115">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-116">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-117">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-118">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-120">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-121">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4c2c7-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-123">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-124">Kumulatives Update für lync Server 2013 Februar 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4c2c7-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-126">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-128">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="4c2c7-128">any</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-129">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4c2c7-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-131">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="4c2c7-131">any</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-132">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4c2c7-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-134">Beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="4c2c7-134">any</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-135">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="4c2c7-136">Lync-Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4c2c7-136">Lync Client Support</span></span>

<span data-ttu-id="4c2c7-137">In der folgenden Tabelle werden die Clients aufgeführt, die Location-Based Routing unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c2c7-138">Clienttyp</span><span class="sxs-lookup"><span data-stu-id="4c2c7-138">Client type</span></span></th>
<th><span data-ttu-id="4c2c7-139">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="4c2c7-139">Supported</span></span></th>
<th><span data-ttu-id="4c2c7-140">Details</span><span class="sxs-lookup"><span data-stu-id="4c2c7-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-142">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-142">yes</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-143">Einschließlich lync 2013 Kumulatives Update vom 2013. Februar</span><span class="sxs-lookup"><span data-stu-id="4c2c7-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="4c2c7-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-145">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4c2c7-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-147">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4c2c7-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-149">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-150">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="4c2c7-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-151">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-152">Lync für Windows 8</span><span class="sxs-lookup"><span data-stu-id="4c2c7-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-153">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c2c7-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-155">nein</span><span class="sxs-lookup"><span data-stu-id="4c2c7-155">no</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-156">VoIP muss für lync Mobile 2013-Clients deaktiviert werden, wenn Sie von Benutzern verwendet werden, bei denen Location-Based Routing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c2c7-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="4c2c7-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="4c2c7-158">ja</span><span class="sxs-lookup"><span data-stu-id="4c2c7-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="4c2c7-159">Wenn Sie VoIP für lync Mobile 2013-Clients deaktivieren möchten, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung IP-Audio/Video zu, die für alle Benutzer deaktiviert ist, die für das standortbasierte Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="4c2c7-160">Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c2c7-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c2c7-161">See Also</span></span>


[<span data-ttu-id="4c2c7-162">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c2c7-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

