---
title: 'Lync Server 2013: Port Zusammenfassung-DNS-und HLB-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6175f83e1cea20e21ed25c372849c0e6b80b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="e5222-102">Port Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5222-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5222-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e5222-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e5222-104">Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e5222-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="e5222-105">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e5222-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="e5222-106">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e5222-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e5222-107">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e5222-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e5222-108">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e5222-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="e5222-109">Einzelne Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="e5222-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5222-110">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e5222-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e5222-111">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e5222-111">Source IP address</span></span></th>
<th><span data-ttu-id="e5222-112">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e5222-112">Destination IP address</span></span></th>
<th><span data-ttu-id="e5222-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5222-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5222-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="e5222-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="e5222-115">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="e5222-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e5222-116">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="e5222-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e5222-117">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5222-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5222-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="e5222-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="e5222-119">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="e5222-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e5222-120">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="e5222-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e5222-121">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5222-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5222-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="e5222-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="e5222-123">Director</span><span class="sxs-lookup"><span data-stu-id="e5222-123">Director</span></span></p></td>
<td><p><span data-ttu-id="e5222-124">Front-End-Pool oder Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e5222-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e5222-125">Kommunikation zwischen Servern zwischen dem Director HLB VIP und dem Front-End-Server-oder Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="e5222-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5222-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="e5222-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="e5222-127">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="e5222-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e5222-128">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="e5222-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e5222-129">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="e5222-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5222-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="e5222-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="e5222-131">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="e5222-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e5222-132">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="e5222-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e5222-133">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="e5222-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5222-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="e5222-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="e5222-135">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5222-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e5222-136">Director</span><span class="sxs-lookup"><span data-stu-id="e5222-136">Director</span></span></p></td>
<td><p><span data-ttu-id="e5222-137">SIP-Kommunikation vom Edgeserver zum Director sowie zu den Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="e5222-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5222-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e5222-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e5222-139">Any</span><span class="sxs-lookup"><span data-stu-id="e5222-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e5222-140">Director</span><span class="sxs-lookup"><span data-stu-id="e5222-140">Director</span></span></p></td>
<td><p><span data-ttu-id="e5222-141">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e5222-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5222-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e5222-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e5222-143">Any</span><span class="sxs-lookup"><span data-stu-id="e5222-143">Any</span></span></p></td>
<td><p><span data-ttu-id="e5222-144">Director</span><span class="sxs-lookup"><span data-stu-id="e5222-144">Director</span></span></p></td>
<td><p><span data-ttu-id="e5222-145">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e5222-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5222-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e5222-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e5222-147">Any</span><span class="sxs-lookup"><span data-stu-id="e5222-147">Any</span></span></p></td>
<td><p><span data-ttu-id="e5222-148">Director</span><span class="sxs-lookup"><span data-stu-id="e5222-148">Director</span></span></p></td>
<td><p><span data-ttu-id="e5222-149">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e5222-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

