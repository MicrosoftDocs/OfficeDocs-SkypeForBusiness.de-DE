---
title: 'Lync Server 2013: Port Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72d059cc32015409377ab0b12bbe8c3ebc7da7d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="56139-102">Port Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56139-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56139-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="56139-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="56139-104">Firewall-Portanforderungen für eine Directorpool bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle des Edgeserver oder der internen Schnittstelle des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="56139-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="56139-105">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="56139-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="56139-106">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="56139-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="56139-107">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="56139-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="56139-108">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="56139-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="56139-109">Director-Ports und -Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="56139-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56139-110">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="56139-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="56139-111">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="56139-111">Source IP address</span></span></th>
<th><span data-ttu-id="56139-112">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="56139-112">Destination IP address</span></span></th>
<th><span data-ttu-id="56139-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56139-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56139-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="56139-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="56139-115">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="56139-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="56139-116">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="56139-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="56139-117">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="56139-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56139-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="56139-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="56139-119">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="56139-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="56139-120">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="56139-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="56139-121">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="56139-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56139-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="56139-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="56139-123">Director</span><span class="sxs-lookup"><span data-stu-id="56139-123">Director</span></span></p></td>
<td><p><span data-ttu-id="56139-124">Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="56139-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="56139-125">Inter-Server-Kommunikation zwischen dem Director HLB VIP und den Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="56139-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56139-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="56139-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="56139-127">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="56139-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="56139-128">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="56139-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="56139-129">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="56139-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56139-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="56139-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="56139-131">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="56139-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="56139-132">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="56139-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="56139-133">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="56139-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56139-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="56139-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="56139-135">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="56139-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="56139-136">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="56139-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="56139-137">SIP-Kommunikation vom Edgeserver zum Director und zu den Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="56139-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56139-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="56139-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="56139-139">Any</span><span class="sxs-lookup"><span data-stu-id="56139-139">Any</span></span></p></td>
<td><p><span data-ttu-id="56139-140">Director</span><span class="sxs-lookup"><span data-stu-id="56139-140">Director</span></span></p></td>
<td><p><span data-ttu-id="56139-141">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="56139-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56139-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="56139-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="56139-143">Any</span><span class="sxs-lookup"><span data-stu-id="56139-143">Any</span></span></p></td>
<td><p><span data-ttu-id="56139-144">Director</span><span class="sxs-lookup"><span data-stu-id="56139-144">Director</span></span></p></td>
<td><p><span data-ttu-id="56139-145">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="56139-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56139-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="56139-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="56139-147">Any</span><span class="sxs-lookup"><span data-stu-id="56139-147">Any</span></span></p></td>
<td><p><span data-ttu-id="56139-148">Director</span><span class="sxs-lookup"><span data-stu-id="56139-148">Director</span></span></p></td>
<td><p><span data-ttu-id="56139-149">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="56139-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

