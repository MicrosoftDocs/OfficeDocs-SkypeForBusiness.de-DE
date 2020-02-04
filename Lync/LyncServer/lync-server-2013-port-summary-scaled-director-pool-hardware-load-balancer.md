---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)'
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
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1a4fc-102">Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a4fc-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a4fc-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1a4fc-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1a4fc-104">Die Firewall-Portanforderungen für einen Director-Pool bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director aus der internen Schnittstelle des Edge-Servers oder der internen Schnittstelle des Reverse-Proxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="1a4fc-105">Microsoft lync Server 2013 erwartet standardmäßig, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverse-Proxy an den Director sowie den Front-End-Pool und den Front-End-Server geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1a4fc-106">Darüber hinaus muss die SIP-Kommunikation (Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers mit dem Director und dem Front-End-Pool und dem Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1a4fc-107">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver auf dem Front-End-Pool und dem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1a4fc-108">Eine Regel, die die SIP/MTLS/TCP 5061-Kommunikation vom Director, Front-End-Pool und Front-End-Server zur internen Edge-Server-Schnittstelle ermöglicht, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1a4fc-109">Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="1a4fc-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a4fc-110">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="1a4fc-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a4fc-111">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="1a4fc-111">Source IP address</span></span></th>
<th><span data-ttu-id="1a4fc-112">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="1a4fc-112">Destination IP address</span></span></th>
<th><span data-ttu-id="1a4fc-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a4fc-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a4fc-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1a4fc-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-115">Interne Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a4fc-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-116">Director Hardware Load Balancer VIP</span><span class="sxs-lookup"><span data-stu-id="1a4fc-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-117">Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a4fc-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1a4fc-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-119">Interne Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a4fc-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-120">Director Hardware Load Balancer VIP</span><span class="sxs-lookup"><span data-stu-id="1a4fc-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-121">Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a4fc-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1a4fc-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-123">Director</span><span class="sxs-lookup"><span data-stu-id="1a4fc-123">Director</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-124">Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="1a4fc-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-125">Inter-Server-Kommunikation zwischen dem Director HLB VIP und den Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="1a4fc-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a4fc-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1a4fc-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-127">Interne Clients</span><span class="sxs-lookup"><span data-stu-id="1a4fc-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-128">Director Hardware Load Balancer VIP</span><span class="sxs-lookup"><span data-stu-id="1a4fc-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-129">Der Director stellt Webdienste sowohl internen als auch externen Clients zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a4fc-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1a4fc-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-131">Interne Clients</span><span class="sxs-lookup"><span data-stu-id="1a4fc-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-132">Director Hardware Load Balancer VIP</span><span class="sxs-lookup"><span data-stu-id="1a4fc-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-133">Der Director stellt Webdienste sowohl internen als auch externen Clients zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a4fc-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1a4fc-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-135">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a4fc-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-136">Director Hardware Load Balancer VIP</span><span class="sxs-lookup"><span data-stu-id="1a4fc-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-137">SIP-Kommunikation vom Edgeserver an den Director und die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1a4fc-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a4fc-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1a4fc-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1a4fc-139">Any</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-140">Director</span><span class="sxs-lookup"><span data-stu-id="1a4fc-140">Director</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-141">Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="1a4fc-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a4fc-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1a4fc-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-143">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1a4fc-143">Any</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-144">Director</span><span class="sxs-lookup"><span data-stu-id="1a4fc-144">Director</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-145">Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="1a4fc-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a4fc-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1a4fc-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-147">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1a4fc-147">Any</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-148">Director</span><span class="sxs-lookup"><span data-stu-id="1a4fc-148">Director</span></span></p></td>
<td><p><span data-ttu-id="1a4fc-149">Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="1a4fc-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

