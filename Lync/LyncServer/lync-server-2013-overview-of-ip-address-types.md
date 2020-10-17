---
title: 'Lync Server 2013: Übersicht über IP-Adresstypen'
description: 'Lync Server 2013: Übersicht über IP-Adresstypen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559221"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="d8c4e-103">Übersicht über IP-Adresstypen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c4e-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c4e-104">_**Letztes Änderungsstand des Themas:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="d8c4e-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="d8c4e-105">Beim Konfigurieren von IP-Adressen in lync Server 2013 haben Sie drei Optionen.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="d8c4e-106">Sie können lync Server 2013 so konfigurieren, dass nur IP Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als *dualer Stapel*bezeichnet) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="d8c4e-107">Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="d8c4e-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="d8c4e-108">**Nur IPv4**     IPv6 wurde erstellt, da die IPv4-Adressen auf der Welt nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="d8c4e-109">IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen kommunizieren muss, unterstützen vielleicht derzeit noch nicht IPv6, und möglicherweise bleibt das auch noch eine ganze Weile so.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="d8c4e-110">Eine nur-IPv4-Konfiguration hilft sicherzustellen, dass Ihre lync Server Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="d8c4e-111">**Nur IPv6**     Umgekehrt schließt eine vollständige IPv6-Implementierung zu diesem Zeitpunkt die Kommunikation mit vielen vorhandenen Geräten aus.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="d8c4e-112">**Dualer Stapel**     Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="d8c4e-113">Diese Konfiguration wird in lync Server 2013 unterstützt, da in den meisten Fällen der Übergang von voll-IPv4 zu voll-IPv6 einige Jahre dauern wird.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="d8c4e-114">In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene lync Server Features erläutert.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8c4e-p104">Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der Produktionsbereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="d8c4e-117">Clientregistrierung</span><span class="sxs-lookup"><span data-stu-id="d8c4e-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c4e-118">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d8c4e-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="d8c4e-119">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="d8c4e-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-123">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-124">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-125">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-126">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-127">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-128">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-131">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="d8c4e-134">Peer-zu-Peer-Client</span><span class="sxs-lookup"><span data-stu-id="d8c4e-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="d8c4e-p105">Peer-zu-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c4e-137">Clientendpunkt 1</span><span class="sxs-lookup"><span data-stu-id="d8c4e-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="d8c4e-138">Clientendpunkt 2</span><span class="sxs-lookup"><span data-stu-id="d8c4e-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-142">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-143">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-144">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-146">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="d8c4e-149">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="d8c4e-149">Conferencing</span></span>

<span data-ttu-id="d8c4e-150">Konferenzfunktionen beinhalten Audio/Video, Anwendungsfreigabe und Zusammenarbeit an Daten (Whiteboards und Dateifreigabe).</span><span class="sxs-lookup"><span data-stu-id="d8c4e-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c4e-151">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d8c4e-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="d8c4e-152">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="d8c4e-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-156">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-157">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-158">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-159">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-160">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-161">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-164">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="d8c4e-167">Vermittlungsserver/PSTN</span><span class="sxs-lookup"><span data-stu-id="d8c4e-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="d8c4e-168">Lync Server 2013 unterstützt keine medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="d8c4e-169">Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c4e-170">Primäre Schnittstelle\*</span><span class="sxs-lookup"><span data-stu-id="d8c4e-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="d8c4e-171">PSTN-Schnittstelle (auf dem Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="d8c4e-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="d8c4e-172">Einstellung für das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="d8c4e-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-173">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-174">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-176">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-177">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-178">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-179">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-180">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8c4e-182">\* Die primäre Schnittstelle ist die Schnittstelle, die mit den lync Server Komponenten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="d8c4e-183">Peer-zu-Peer-Kommunikation mit Remotebenutzern</span><span class="sxs-lookup"><span data-stu-id="d8c4e-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="d8c4e-184">Peer-zu-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c4e-185">Netzwerk des Remotebenutzers</span><span class="sxs-lookup"><span data-stu-id="d8c4e-185">Remote user network</span></span></th>
<th><span data-ttu-id="d8c4e-186">Edgeserver (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="d8c4e-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-189">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-190">IPv4</span><span class="sxs-lookup"><span data-stu-id="d8c4e-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-191">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-192">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-194">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d8c4e-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="d8c4e-197">Konfiguration mit Front-End-Pool und Edgepool</span><span class="sxs-lookup"><span data-stu-id="d8c4e-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="d8c4e-198">In der folgenden Tabelle ist die Unterstützungsmatrix zwischen dem Front-End-Server Pool und dem internen Edgeserver Pool dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="d8c4e-199">Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)</span><span class="sxs-lookup"><span data-stu-id="d8c4e-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d8c4e-200"><strong>Edgepool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-201"><strong>Edgepool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-202"><strong>Edgepool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-203"><strong>Front-End-Pool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-204">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-205">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-206">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-207"><strong>Front-End-Pool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-208">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-209">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-210">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-211"><strong>Front-End-Pool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-212">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-212">No</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-213">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-213">No</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-214">Ja\*</span><span class="sxs-lookup"><span data-stu-id="d8c4e-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8c4e-215">\* Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="d8c4e-216">Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="d8c4e-217">Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="d8c4e-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d8c4e-218"><strong>Edgepool (externer Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-219"><strong>Edgepool (Externer Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-220"><strong>Edgepool (Externer Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-221"><strong>Edgepool (interner Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-222">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-223">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-224">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c4e-225"><strong>Edgepool (interner Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-226">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-226">No</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-227">Ja</span><span class="sxs-lookup"><span data-stu-id="d8c4e-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-228">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c4e-229"><strong>Edgepool (interner Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d8c4e-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d8c4e-230">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-230">No</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-231">Nein</span><span class="sxs-lookup"><span data-stu-id="d8c4e-231">No</span></span></p></td>
<td><p><span data-ttu-id="d8c4e-232">Ja\*</span><span class="sxs-lookup"><span data-stu-id="d8c4e-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8c4e-233">\* Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="d8c4e-234">Erweiterte Unterstützung für Enterprise-VoIP für IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="d8c4e-235">Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E9-1-1-Notrufdienste oder Medienumgehung beinhalten, müssen als Implementierung nur mit IPv4 oder als Dualer-Stapel-Implementierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8c4e-236">In einer Dual-Stacked-Bereitstellung, auch wenn ein lync-Client eine Verbindung mit einem lync Server mithilfe von IPv6 herstellt, bemühen sich lync am besten, eine geeignete IPv4-Adresse zur Unterstützung von E9-1-1 zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="d8c4e-237">Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="d8c4e-p107">Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="d8c4e-241">Unterstützung anderer lync Server 2013 Features für IPv6</span><span class="sxs-lookup"><span data-stu-id="d8c4e-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="d8c4e-242">Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt lync Server 2013 IPv6 für die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="d8c4e-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="d8c4e-243">**Beständiger Chat**</span><span class="sxs-lookup"><span data-stu-id="d8c4e-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="d8c4e-244">Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="d8c4e-245">Ausführliche Informationen zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation Deploying persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="d8c4e-246">**QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen**</span><span class="sxs-lookup"><span data-stu-id="d8c4e-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="d8c4e-247">In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="d8c4e-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

