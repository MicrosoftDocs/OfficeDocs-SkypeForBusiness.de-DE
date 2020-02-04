---
title: 'Lync Server 2013: Übersicht über IP-Adresstypen'
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
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="918c8-102">Übersicht über IP-Adresstypen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="918c8-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="918c8-103">_**Letztes Änderungsdatum des Themas:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="918c8-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="918c8-104">Bei der Konfiguration von IP-Adressen in lync Server 2013 stehen Ihnen drei Optionen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="918c8-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="918c8-105">Sie können lync Server 2013 so konfigurieren, dass nur IP, Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als *dualer Stack*bezeichnet) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="918c8-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="918c8-106">Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="918c8-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="918c8-107">\*\*\*\*   IPv6 wurde nur erstellt, weil die IPv4-Adressen für die Welt nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="918c8-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="918c8-108">IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so.</span><span class="sxs-lookup"><span data-stu-id="918c8-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="918c8-109">Eine reine IPv4-Konfiguration wird dabei helfen, sicherzustellen, dass Ihre lync Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="918c8-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="918c8-110">**IPv6 nur**   umgekehrt schließt eine vollständige IPv6-Implementierung zu diesem Zeitpunkt die Kommunikation mit vielen vorhandenen Geräten aus.</span><span class="sxs-lookup"><span data-stu-id="918c8-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="918c8-111">**Dual Stack**   Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="918c8-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="918c8-112">Diese Konfiguration wird in lync Server 2013 unterstützt, da in den meisten Fällen der Übergang von Full-IPv4 zu voll-IPv6 mehrere Jahre dauern wird.</span><span class="sxs-lookup"><span data-stu-id="918c8-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="918c8-113">In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene lync Server-Features erläutert.</span><span class="sxs-lookup"><span data-stu-id="918c8-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="918c8-p104">Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der serienmäßigen Bereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="918c8-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="918c8-116">Clientregistrierung</span><span class="sxs-lookup"><span data-stu-id="918c8-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c8-117">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="918c8-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="918c8-118">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="918c8-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c8-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-122">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-123">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-125">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-126">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-127">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-130">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="918c8-133">Peer-to-Peer-Client</span><span class="sxs-lookup"><span data-stu-id="918c8-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="918c8-p105">Peer-to-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="918c8-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c8-136">Clientendpunkt 1</span><span class="sxs-lookup"><span data-stu-id="918c8-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="918c8-137">Clientendpunkt 2</span><span class="sxs-lookup"><span data-stu-id="918c8-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c8-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-141">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-142">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-143">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-145">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="918c8-148">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="918c8-148">Conferencing</span></span>

<span data-ttu-id="918c8-149">Konferenz umfasst Audio/Video, Anwendungsfreigabe und Datenzusammenarbeit (Whiteboards und Dateifreigabe).</span><span class="sxs-lookup"><span data-stu-id="918c8-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c8-150">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="918c8-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="918c8-151">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="918c8-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c8-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-155">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-156">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-158">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-159">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-160">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-163">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="918c8-166">Vermittlungsserver/PSTN</span><span class="sxs-lookup"><span data-stu-id="918c8-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="918c8-167">Lync Server 2013 unterstützt keine medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt.</span><span class="sxs-lookup"><span data-stu-id="918c8-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="918c8-168">Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="918c8-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c8-169">Primäre Schnittstelle\*</span><span class="sxs-lookup"><span data-stu-id="918c8-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="918c8-170">PSTN-Schnittstelle (auf dem Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="918c8-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="918c8-171">Einstellung für das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="918c8-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c8-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-173">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-175">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-176">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-178">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-179">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="918c8-181">\*Die primäre Schnittstelle ist die Schnittstelle, die mit den lync Server-Komponenten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="918c8-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="918c8-182">Peer-to-Peer-Kommunikation mit Remotebenutzern</span><span class="sxs-lookup"><span data-stu-id="918c8-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="918c8-183">Peer-to-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="918c8-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c8-184">Netzwerk des Remotebenutzers</span><span class="sxs-lookup"><span data-stu-id="918c8-184">Remote user network</span></span></th>
<th><span data-ttu-id="918c8-185">Edgeserver (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="918c8-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c8-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="918c8-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-188">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="918c8-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-190">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="918c8-191">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-193">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="918c8-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="918c8-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="918c8-196">Konfiguration mit Front-End-Pool und Edgepool</span><span class="sxs-lookup"><span data-stu-id="918c8-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="918c8-197">Die folgende Tabelle zeigt die Support Matrix zwischen dem Front-End-Serverpool und dem internen Edge-Serverpool.</span><span class="sxs-lookup"><span data-stu-id="918c8-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="918c8-198">Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)</span><span class="sxs-lookup"><span data-stu-id="918c8-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="918c8-199"><strong>Edgepool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-200"><strong>Edgepool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-201"><strong>Edgepool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-202"><strong>Front-End-Pool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-203">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-204">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-205">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-206"><strong>Front-End-Pool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-207">Ja </span><span class="sxs-lookup"><span data-stu-id="918c8-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-208">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-209">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-210"><strong>Front-End-Pool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-211">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-211">No</span></span></p></td>
<td><p><span data-ttu-id="918c8-212">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-212">No</span></span></p></td>
<td><p><span data-ttu-id="918c8-213">Ja\*</span><span class="sxs-lookup"><span data-stu-id="918c8-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="918c8-214">\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="918c8-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="918c8-215">Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="918c8-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="918c8-216">Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="918c8-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="918c8-217"><strong>Edgepool (Externer Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-218"><strong>Edgepool (Externer Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-219"><strong>Edgepool (Externer Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-220"><strong>Edgepool (Interner Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-221">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-222">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-223">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c8-224"><strong>Edgepool (Interner Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-225">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-225">No</span></span></p></td>
<td><p><span data-ttu-id="918c8-226">Ja</span><span class="sxs-lookup"><span data-stu-id="918c8-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="918c8-227">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c8-228"><strong>Edgepool (Interner Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="918c8-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="918c8-229">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-229">No</span></span></p></td>
<td><p><span data-ttu-id="918c8-230">Nein</span><span class="sxs-lookup"><span data-stu-id="918c8-230">No</span></span></p></td>
<td><p><span data-ttu-id="918c8-231">Ja\*</span><span class="sxs-lookup"><span data-stu-id="918c8-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="918c8-232">\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="918c8-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="918c8-233">Erweiterte Unterstützung für Enterprise-VoIP für IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="918c8-234">Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="918c8-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="918c8-235">In einer Dual-Stacked-Bereitstellung, auch wenn ein lync-Client eine Verbindung mit einem lync-Server mithilfe von IPv6 herstellt, bemüht sich lync, eine geeignete IPv4-Adresse zuzuordnen, um E9-1-1 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="918c8-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="918c8-236">Der standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="918c8-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="918c8-p107">Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="918c8-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="918c8-240">Andere lync Server 2013-Feature-Unterstützung für IPv6</span><span class="sxs-lookup"><span data-stu-id="918c8-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="918c8-241">Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt lync Server 2013 IPv6 für die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="918c8-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="918c8-242">**Beständiger Chat**</span><span class="sxs-lookup"><span data-stu-id="918c8-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="918c8-243">Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="918c8-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="918c8-244">Details zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation zum Bereitstellen des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="918c8-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="918c8-245">**QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**</span><span class="sxs-lookup"><span data-stu-id="918c8-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="918c8-246">In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="918c8-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

