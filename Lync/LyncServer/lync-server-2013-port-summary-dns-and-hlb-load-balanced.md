---
title: 'Lync Server 2013: Port Zusammenfassung-DNS-und HLB-Lastenausgleich'
description: 'Lync Server 2013: Port Summary-DNS and HLB Last Balanced.'
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
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543131"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="a44d7-103">Port Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44d7-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44d7-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a44d7-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a44d7-105">Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a44d7-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="a44d7-106">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="a44d7-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="a44d7-107">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a44d7-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="a44d7-108">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="a44d7-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="a44d7-109">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a44d7-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="a44d7-110">Einzelne Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="a44d7-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a44d7-111">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="a44d7-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a44d7-112">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="a44d7-112">Source IP address</span></span></th>
<th><span data-ttu-id="a44d7-113">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="a44d7-113">Destination IP address</span></span></th>
<th><span data-ttu-id="a44d7-114">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a44d7-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a44d7-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="a44d7-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="a44d7-116">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="a44d7-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="a44d7-117">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="a44d7-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="a44d7-118">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="a44d7-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a44d7-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="a44d7-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="a44d7-120">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="a44d7-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="a44d7-121">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="a44d7-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="a44d7-122">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="a44d7-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a44d7-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="a44d7-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="a44d7-124">Director</span><span class="sxs-lookup"><span data-stu-id="a44d7-124">Director</span></span></p></td>
<td><p><span data-ttu-id="a44d7-125">Front-End-Pool oder Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a44d7-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a44d7-126">Kommunikation zwischen Servern zwischen dem Director HLB VIP und dem Front-End-Server-oder Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="a44d7-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a44d7-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="a44d7-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="a44d7-128">Interne Clients</span><span class="sxs-lookup"><span data-stu-id="a44d7-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="a44d7-129">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="a44d7-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="a44d7-130">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="a44d7-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a44d7-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="a44d7-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="a44d7-132">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="a44d7-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="a44d7-133">Director Hardware-Lastenausgleich-VIP</span><span class="sxs-lookup"><span data-stu-id="a44d7-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="a44d7-134">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="a44d7-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a44d7-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="a44d7-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="a44d7-136">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a44d7-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a44d7-137">Director</span><span class="sxs-lookup"><span data-stu-id="a44d7-137">Director</span></span></p></td>
<td><p><span data-ttu-id="a44d7-138">SIP-Kommunikation vom Edgeserver zum Director sowie zu den Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="a44d7-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a44d7-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a44d7-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a44d7-140">Beliebig</span><span class="sxs-lookup"><span data-stu-id="a44d7-140">Any</span></span></p></td>
<td><p><span data-ttu-id="a44d7-141">Director</span><span class="sxs-lookup"><span data-stu-id="a44d7-141">Director</span></span></p></td>
<td><p><span data-ttu-id="a44d7-142">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="a44d7-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a44d7-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a44d7-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a44d7-144">Beliebig</span><span class="sxs-lookup"><span data-stu-id="a44d7-144">Any</span></span></p></td>
<td><p><span data-ttu-id="a44d7-145">Director</span><span class="sxs-lookup"><span data-stu-id="a44d7-145">Director</span></span></p></td>
<td><p><span data-ttu-id="a44d7-146">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="a44d7-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a44d7-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a44d7-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a44d7-148">Beliebig</span><span class="sxs-lookup"><span data-stu-id="a44d7-148">Any</span></span></p></td>
<td><p><span data-ttu-id="a44d7-149">Director</span><span class="sxs-lookup"><span data-stu-id="a44d7-149">Director</span></span></p></td>
<td><p><span data-ttu-id="a44d7-150">Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="a44d7-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

