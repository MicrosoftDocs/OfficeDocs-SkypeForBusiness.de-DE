---
title: Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="de9b6-102">Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de9b6-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de9b6-103">_**Letztes Änderungsdatum des Themas:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="de9b6-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="de9b6-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="de9b6-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="de9b6-105">Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="de9b6-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="de9b6-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="de9b6-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="de9b6-107">Neben IPv4 unterstützt der Edgeserver nun IPv6.</span><span class="sxs-lookup"><span data-stu-id="de9b6-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="de9b6-108">Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="de9b6-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="de9b6-109">**Skalierter konsolidierter Edge mithilfe des Hardware Lastenausgleichs**</span><span class="sxs-lookup"><span data-stu-id="de9b6-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="de9b6-110">![Edge-Server-Umkreisnetzwerk-Ports und-Protokolle] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge-Server-Umkreisnetzwerk-Ports und-Protokolle")</span><span class="sxs-lookup"><span data-stu-id="de9b6-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="de9b6-111">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="de9b6-111">Port and Protocol Details</span></span>

<span data-ttu-id="de9b6-112">Es wird empfohlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="de9b6-113">Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional wie in der Abbildung des eingehenden/ausgehenden Edge-Traffics durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="de9b6-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="de9b6-114">Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.</span><span class="sxs-lookup"><span data-stu-id="de9b6-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="de9b6-115">Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="de9b6-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de9b6-116">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="de9b6-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="de9b6-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-117">Source IP address</span></span></th>
<th><span data-ttu-id="de9b6-118">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-118">Destination IP address</span></span></th>
<th><span data-ttu-id="de9b6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de9b6-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-120">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="de9b6-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="de9b6-121">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="de9b6-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-122">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-122">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-123">Zertifikatsperrung/CRL-Prüfung und-Abruf</span><span class="sxs-lookup"><span data-stu-id="de9b6-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="de9b6-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="de9b6-125">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="de9b6-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-126">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-127">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="de9b6-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="de9b6-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="de9b6-129">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="de9b6-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-130">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-130">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-131">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="de9b6-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="de9b6-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="de9b6-133">Edge-Server-A/V-Edgedienst-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-134">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-135">Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="de9b6-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="de9b6-137">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-138">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-139">Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de9b6-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="de9b6-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="de9b6-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-141">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-142">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-143">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="de9b6-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="de9b6-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="de9b6-145">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-145">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-146">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-147">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="de9b6-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-148">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="de9b6-149">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-150">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-151">3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="de9b6-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="de9b6-152">Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="de9b6-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-153">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="de9b6-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-154">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-155">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-156">Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-157">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-158">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-158">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-159">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-160">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-161">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-162">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-163">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-164">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="de9b6-165">Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: internes Interface, Knoten 1 und Knoten 2</span><span class="sxs-lookup"><span data-stu-id="de9b6-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de9b6-166">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="de9b6-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="de9b6-167">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-167">Source IP address</span></span></th>
<th><span data-ttu-id="de9b6-168">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-168">Destination IP address</span></span></th>
<th><span data-ttu-id="de9b6-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de9b6-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="de9b6-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="de9b6-171">Any (kann als Front-End-Server Adresse oder virtuelle IP-Adresse des Front-End-Pools definiert werden, auf der der XMPP-Gatewayserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="de9b6-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-172">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-173">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="de9b6-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="de9b6-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-175">Any (kann als Front-End-Server-IP oder-Pool definiert werden, der den zentralen Verwaltungsspeicher enthält)</span><span class="sxs-lookup"><span data-stu-id="de9b6-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-176">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-177">Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="de9b6-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="de9b6-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="de9b6-179">Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-180">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-181">Webkonferenzen-Datenverkehr von interner Bereitstellung zu interner Edge-Server Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-182">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="de9b6-183">Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-184">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-185">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="de9b6-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-186">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-187">Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-188">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-189">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="de9b6-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="de9b6-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="de9b6-191">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-191">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-192">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-193">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="de9b6-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="de9b6-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="de9b6-195">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-195">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-196">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-197">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="de9b6-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="de9b6-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="de9b6-199">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-199">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-200">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de9b6-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-201">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="de9b6-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="de9b6-202">Hardware Lastenausgleichs haben bestimmte Anforderungen, wenn Sie bereitgestellt werden, um Verfügbarkeit und Lastenausgleich für lync Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="de9b6-203">Die Anforderungen sind in der folgenden Abbildung und in den Tabellen definiert.</span><span class="sxs-lookup"><span data-stu-id="de9b6-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="de9b6-204">Drittanbieter verwenden möglicherweise unterschiedliche Terminologie für die hier festgelegten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="de9b6-205">Es ist erforderlich, die Anforderungen von lync Server den Features und Konfigurationsoptionen zuzuordnen, die vom Hersteller Ihres Hardwarelastenausgleichs bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="de9b6-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="de9b6-206">Bei der Konfiguration von Hardware-Lastenausgleichsgeräten sollten Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="de9b6-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="de9b6-207">Quell-Netzwerkadressübersetzung (SNAT) kann auf dem Hardware Load Balancer (HLB) für Access Edge Service und Web Conferencing Edge Service konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="de9b6-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="de9b6-208">SNAT kann nicht auf dem a/v-Edgedienst konfiguriert werden – der a/v-Edgedienst muss mit der Adresse des realen Servers und nicht mit der virtuellen HLB-IP (VIP) Antworten, um eine einfache Durchquerung von UDP über NAT (Stun)-/Traversal mit Relay-NAT (Turn)/Federation Turn (FTURN) zu verwenden, um ordnungsgemäß zu funktionieren</span><span class="sxs-lookup"><span data-stu-id="de9b6-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="de9b6-209">Wenn der Client eine Anforderung an die HLB sendet, muss die Antwort vom HLB-VIP zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="de9b6-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="de9b6-210">Wenn der Client eine Anforderung an den Edge sendet, muss die Antwort von der Edge-IP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="de9b6-211">Öffentliche IP-Adressen werden auf jeder Server Schnittstelle und auf den VIPs der HLB verwendet, und Ihre Anforderungen an die öffentliche IP-Adresse sind N + 1, wobei für jede echte Server Schnittstelle eine öffentliche IP-Adresse und eine für jedes HLB-VIP vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="de9b6-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="de9b6-212">Wenn im Pool zwei Edgeserver vorhanden sind, werden in 9 öffentliche IP-Adressen, wobei 3 für die HLB-VIPs und eine für jede Edgeserver-Schnittstelle verwendet werden (insgesamt sechs für die Server) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de9b6-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="de9b6-213">Bei Access Edge Service und Web Conferencing Edge Service (und Verwendung von NAT auf der HLB) kontaktiert der Client den VIP, der VIP ändert die Quell-IP-Adresse vom Client in seine eigene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="de9b6-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="de9b6-214">Die Server Schnittstelle adressiert die Absenderadresse an den VIP, der VIP ändert die Quelladresse von der IP-Adresse der Server Schnittstelle und sendet das Paket an den Client.</span><span class="sxs-lookup"><span data-stu-id="de9b6-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="de9b6-215">Für den A/V-Edgedienst darf der VIP die Quell-IP-Adresse nicht ändern, und die Adresse des realen Servers wird direkt an den Client zurückgegeben – Sie können NAT auf der HLB für AV-Datenverkehr nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="de9b6-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="de9b6-216">Wenn der Client eine Anfrage an das HLB-VIP sendet, muss die Antwort vom HLB-VIP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="de9b6-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="de9b6-217">Wenn der Client eine Anforderung an die Edge-IP-Adresse sendet, muss die Antwort von der Edge-IP-Adresse zurückgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="de9b6-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="de9b6-218">Bei AV behält die externe Firewall die öffentliche IP-Adresse des realen Servers für alle Pakete bei.</span><span class="sxs-lookup"><span data-stu-id="de9b6-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="de9b6-219">Nach der festgelegten Kommunikation des Client-zu-A/V-Edge-Diensts erfolgt die Kommunikation mit dem echten Server und nicht mit der HLB</span><span class="sxs-lookup"><span data-stu-id="de9b6-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="de9b6-220">Interner Edge-Server und-Clients müssen weitergeleitet werden, und für alle internen Netzwerke, die Server oder Clients hosten, werden permanente Routen festgesetzt.</span><span class="sxs-lookup"><span data-stu-id="de9b6-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="de9b6-221">Der HLB Access Edge Service VIP fungiert als Standardgateway für jede Edge-Server-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="de9b6-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="de9b6-222">Weitere Informationen zur NAT-Planung und-Funktionalität finden Sie unter <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware Load Balancer Requirements for lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="de9b6-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="de9b6-223">![Details zu Edge-Server-Ports und-Protokollen] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edge-Server-Ports und-Protokollen")</span><span class="sxs-lookup"><span data-stu-id="de9b6-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="de9b6-224">Externe Port Einstellungen für skalierten konsolidierten Edge, Hardware Lastenausgleich: externe Schnittstelle, Virtuelles IPS</span><span class="sxs-lookup"><span data-stu-id="de9b6-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de9b6-225">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="de9b6-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="de9b6-226">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-226">Source IP address</span></span></th>
<th><span data-ttu-id="de9b6-227">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-227">Destination IP address</span></span></th>
<th><span data-ttu-id="de9b6-228">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de9b6-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="de9b6-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="de9b6-230">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-230">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-231">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="de9b6-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-232">Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="de9b6-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="de9b6-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="de9b6-234">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="de9b6-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-235">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-235">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-236">Der XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="de9b6-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-237">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-238">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-238">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-239">Access Edge Service Public VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-240">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="de9b6-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-241">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="de9b6-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="de9b6-242">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-242">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-243">Access Edge Service Public VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-244">SIP-Signalisierungs-, Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="de9b6-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-245">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="de9b6-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="de9b6-246">Access Edge Service Public VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-247">Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="de9b6-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="de9b6-248">SIP-Signalisierungs-, Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="de9b6-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-249">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-250">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-250">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-251">Edge-Server-Webkonferenz-Edgedienst, öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-252">Web-Konferenzmedien</span><span class="sxs-lookup"><span data-stu-id="de9b6-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-253">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="de9b6-254">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-254">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-255">Edge-Server A/V Edge Service Public VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-256">Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-257">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-258">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-258">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-259">Edge-Server A/V Edge Service Public VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="de9b6-260">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="de9b6-261">Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: internes Interface, Virtuelles IPS</span><span class="sxs-lookup"><span data-stu-id="de9b6-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de9b6-262">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="de9b6-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="de9b6-263">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-263">Source IP address</span></span></th>
<th><span data-ttu-id="de9b6-264">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="de9b6-264">Destination IP address</span></span></th>
<th><span data-ttu-id="de9b6-265">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de9b6-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-266">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="de9b6-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="de9b6-267">Any (kann als Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-268">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-269">Ausgehender SIP-Datenverkehr (von Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools) zu interner Edge-VIP</span><span class="sxs-lookup"><span data-stu-id="de9b6-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-270">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="de9b6-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="de9b6-271">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-272">Any (kann als Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-273">Eingehende SIP-Datenverkehr (an Director, Virtual IP address des Director-Pools, virtuelle IP-Adresse des Front-End-Servers oder virtuelle IP-Adresse des Front-End-Pools) aus der internen</span><span class="sxs-lookup"><span data-stu-id="de9b6-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="de9b6-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="de9b6-275">Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="de9b6-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="de9b6-276">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-277">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="de9b6-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-278">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="de9b6-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="de9b6-279">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-279">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-280">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-281">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="de9b6-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de9b6-282">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-283">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-283">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-284">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-285">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern wenn keine UDP-Kommunikation eingerichtet werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="de9b6-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de9b6-286">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="de9b6-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="de9b6-287">Edge-Server-interne VIP-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="de9b6-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="de9b6-288">Beliebig</span><span class="sxs-lookup"><span data-stu-id="de9b6-288">Any</span></span></p></td>
<td><p><span data-ttu-id="de9b6-289">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern wenn keine UDP-Kommunikation eingerichtet werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="de9b6-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

