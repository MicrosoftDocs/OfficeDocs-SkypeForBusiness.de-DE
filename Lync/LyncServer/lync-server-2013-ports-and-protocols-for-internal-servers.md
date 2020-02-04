---
title: 'Lync Server 2013: Ports und Protokolle für interne Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="403c4-102">Ports und Protokolle für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="403c4-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="403c4-103">_**Letztes Änderungsdatum des Themas:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="403c4-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="403c4-104">In diesem Abschnitt werden die Ports und Protokolle zusammengefasst, die von Servern, Load-Balancern und Clients in einer lync Server-Bereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="403c4-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="403c4-105">Lync-und Communicator-Clients werden, wenn Sie an einer 1:1-Kommunikation beteiligt sind, häufig als Peer-to-Peer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="403c4-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="403c4-106">Technisch gesehen kommunizieren die beiden Clients in einer 1:1-Konversation mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte.</span><span class="sxs-lookup"><span data-stu-id="403c4-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="403c4-107">Die IMMCU ist eine Komponente des Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="403c4-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="403c4-108">Wenn Sie den IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Anrufdetailaufzeichnung und andere Features, die der Front-End-Server ermöglicht, aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="403c4-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="403c4-109">Die Kommunikation erfolgt von einem dynamischen Quell Port auf dem Client zum Front-End-Serverport TLS/TCP/5061 (unter der Voraussetzung, dass die empfohlene Transportschichtsicherheit verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="403c4-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="403c4-110">Die Peer-to-Peer-Kommunikation (ebenso wie die Chat Unterhaltung mit mehreren Teilnehmern) ist im Entwurf nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="403c4-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="403c4-111">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="403c4-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="403c4-112">Die Windows-Firewall muss ausgeführt werden, bevor Sie die lync Server-Dienste auf einem Server starten, weil dies der Fall ist, wenn lync Server die erforderlichen Ports in der Firewall öffnet.</span><span class="sxs-lookup"><span data-stu-id="403c4-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="403c4-113">Details zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="403c4-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="403c4-114">In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="403c4-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="403c4-115">Erforderliche Serverports (nach Serverrolle)</span><span class="sxs-lookup"><span data-stu-id="403c4-115">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="403c4-116">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="403c4-116">Server role</span></span></th>
<th><span data-ttu-id="403c4-117">Name des Diensts</span><span class="sxs-lookup"><span data-stu-id="403c4-117">Service name</span></span></th>
<th><span data-ttu-id="403c4-118">Port</span><span class="sxs-lookup"><span data-stu-id="403c4-118">Port</span></span></th>
<th><span data-ttu-id="403c4-119">Protokoll</span><span class="sxs-lookup"><span data-stu-id="403c4-119">Protocol</span></span></th>
<th><span data-ttu-id="403c4-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="403c4-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="403c4-121">Alle Server</span><span class="sxs-lookup"><span data-stu-id="403c4-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-122">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="403c4-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="403c4-123">1434</span><span class="sxs-lookup"><span data-stu-id="403c4-123">1434</span></span></p></td>
<td><p><span data-ttu-id="403c4-124">UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-125">SQL-Browser für die lokale replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="403c4-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-126">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-127">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-128">5060</span><span class="sxs-lookup"><span data-stu-id="403c4-128">5060</span></span></p></td>
<td><p><span data-ttu-id="403c4-129">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-130">Wird optional von Standard Edition- und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-131">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-132">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-133">5061</span><span class="sxs-lookup"><span data-stu-id="403c4-133">5061</span></span></p></td>
<td><p><span data-ttu-id="403c4-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-135">Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="403c4-136">Wird auch für die Kommunikation mit Monitoring Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-137">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-138">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-139">444</span><span class="sxs-lookup"><span data-stu-id="403c4-139">444</span></span></p></td>
<td><p><span data-ttu-id="403c4-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-140">HTTPS</span></span></p>
<p><span data-ttu-id="403c4-141">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-142">Wird für die HTTPS-Kommunikation zwischen dem Fokus (der lync-Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="403c4-143">Dieser Port wird auch für die TCP-Kommunikation zwischen Überlebenden Branch-Appliances und Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-144">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-145">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-146">135</span><span class="sxs-lookup"><span data-stu-id="403c4-146">135</span></span></p></td>
<td><p><span data-ttu-id="403c4-147">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="403c4-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="403c4-148">Wird für DCOM-basierte Vorgänge wie z. B. das Verschieben von Benutzern, die Synchronisierung des Benutzerreplikationsdiensts und die Synchronisierung von Adressbüchern verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-149">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-150">Lync Server im-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-151">5062</span><span class="sxs-lookup"><span data-stu-id="403c4-151">5062</span></span></p></td>
<td><p><span data-ttu-id="403c4-152">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-153">Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-154">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-155">Lync Server-Webkonferenzdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-156">8057</span><span class="sxs-lookup"><span data-stu-id="403c4-156">8057</span></span></p></td>
<td><p><span data-ttu-id="403c4-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-158">Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-159">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-160">Lync Server-Webkonferenz-Kompatibilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-161">8058</span><span class="sxs-lookup"><span data-stu-id="403c4-161">8058</span></span></p></td>
<td><p><span data-ttu-id="403c4-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-163">Wird verwendet, um auf Persistent Shared Object Model (PSOM)-Verbindungen vom Live Meeting-Client und früheren Versionen von lync Server zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="403c4-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-164">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-165">Lync Server-Audio/Video Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-166">5063</span><span class="sxs-lookup"><span data-stu-id="403c4-166">5063</span></span></p></td>
<td><p><span data-ttu-id="403c4-167">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-168">Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-169">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-170">Lync Server-Audio/Video Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="403c4-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="403c4-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-173">Für Videokonferenzen verwendeter Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="403c4-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-174">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-175">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-176">80</span><span class="sxs-lookup"><span data-stu-id="403c4-176">80</span></span></p></td>
<td><p><span data-ttu-id="403c4-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="403c4-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="403c4-178">Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet, wenn kein HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="403c4-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-179">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-180">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-181">443</span><span class="sxs-lookup"><span data-stu-id="403c4-181">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="403c4-183">Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-184">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-185">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-186">8080</span><span class="sxs-lookup"><span data-stu-id="403c4-186">8080</span></span></p></td>
<td><p><span data-ttu-id="403c4-187">TCP und HTTP</span><span class="sxs-lookup"><span data-stu-id="403c4-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="403c4-188">Wird von Webkomponenten für den externen Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-189">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-190">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="403c4-191">4443</span><span class="sxs-lookup"><span data-stu-id="403c4-191">4443</span></span></p></td>
<td><p><span data-ttu-id="403c4-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="403c4-193">HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Servern für die AutoErmittlungsanmeldung.</span><span class="sxs-lookup"><span data-stu-id="403c4-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-194">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-195">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="403c4-196">8060</span><span class="sxs-lookup"><span data-stu-id="403c4-196">8060</span></span></p></td>
<td><p><span data-ttu-id="403c4-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-198">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-199">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="403c4-200">8061</span><span class="sxs-lookup"><span data-stu-id="403c4-200">8061</span></span></p></td>
<td><p><span data-ttu-id="403c4-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-202">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-203">Mobilitätsdienstekomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="403c4-204">5086</span><span class="sxs-lookup"><span data-stu-id="403c4-204">5086</span></span></p></td>
<td><p><span data-ttu-id="403c4-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-206">Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port</span><span class="sxs-lookup"><span data-stu-id="403c4-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-207">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-208">Mobilitätsdienstekomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="403c4-209">5087</span><span class="sxs-lookup"><span data-stu-id="403c4-209">5087</span></span></p></td>
<td><p><span data-ttu-id="403c4-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-211">Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port</span><span class="sxs-lookup"><span data-stu-id="403c4-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-212">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-213">Mobilitätsdienstekomponente</span><span class="sxs-lookup"><span data-stu-id="403c4-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="403c4-214">443</span><span class="sxs-lookup"><span data-stu-id="403c4-214">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-216">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-217">Lync Server Conferencing Attendant-Dienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="403c4-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="403c4-218">5064</span><span class="sxs-lookup"><span data-stu-id="403c4-218">5064</span></span></p></td>
<td><p><span data-ttu-id="403c4-219">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-220">Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-221">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-222">Lync Server Conferencing Attendant-Dienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="403c4-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="403c4-223">5072</span><span class="sxs-lookup"><span data-stu-id="403c4-223">5072</span></span></p></td>
<td><p><span data-ttu-id="403c4-224">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-225">Wird für eingehende SIP-Anforderungen für Attendant (Dial in Conferencing) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-226">Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="403c4-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-227">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-228">5070</span><span class="sxs-lookup"><span data-stu-id="403c4-228">5070</span></span></p></td>
<td><p><span data-ttu-id="403c4-229">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-230">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-231">Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="403c4-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-232">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-233">5067</span><span class="sxs-lookup"><span data-stu-id="403c4-233">5067</span></span></p></td>
<td><p><span data-ttu-id="403c4-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-235">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-236">Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="403c4-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-237">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-238">5068</span><span class="sxs-lookup"><span data-stu-id="403c4-238">5068</span></span></p></td>
<td><p><span data-ttu-id="403c4-239">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-240">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-241">Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="403c4-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-242">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-243">5081</span><span class="sxs-lookup"><span data-stu-id="403c4-243">5081</span></span></p></td>
<td><p><span data-ttu-id="403c4-244">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-245">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-246">Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="403c4-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-247">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-248">5082</span><span class="sxs-lookup"><span data-stu-id="403c4-248">5082</span></span></p></td>
<td><p><span data-ttu-id="403c4-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-250">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-251">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-252">Lync Server-Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-253">5065</span><span class="sxs-lookup"><span data-stu-id="403c4-253">5065</span></span></p></td>
<td><p><span data-ttu-id="403c4-254">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-255">Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-256">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-257">Lync Server-Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="403c4-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="403c4-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="403c4-259">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-260">Für die Anwendungsfreigabe verwendeter Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="403c4-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-261">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-262">Ankündigungsdienst für lync Server-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="403c4-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="403c4-263">5073</span><span class="sxs-lookup"><span data-stu-id="403c4-263">5073</span></span></p></td>
<td><p><span data-ttu-id="403c4-264">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-265">Wird für eingehende SIP-Anforderungen für den lync Server Conferencing-Ankündigungsdienst (also für Einwahlkonferenzen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-266">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-267">Lync Server-Dienst zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="403c4-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="403c4-268">5075</span><span class="sxs-lookup"><span data-stu-id="403c4-268">5075</span></span></p></td>
<td><p><span data-ttu-id="403c4-269">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-270">Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-271">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-272">Lync Server-audiotestdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="403c4-273">5076</span><span class="sxs-lookup"><span data-stu-id="403c4-273">5076</span></span></p></td>
<td><p><span data-ttu-id="403c4-274">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-275">Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-276">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-277">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="403c4-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="403c4-278">5066</span><span class="sxs-lookup"><span data-stu-id="403c4-278">5066</span></span></p></td>
<td><p><span data-ttu-id="403c4-279">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-280">Wird für das ausgehende E9-1-1-Gateway (9-1-1 [erweitert]) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-281">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-282">Lync Server-Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="403c4-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="403c4-283">5071</span><span class="sxs-lookup"><span data-stu-id="403c4-283">5071</span></span></p></td>
<td><p><span data-ttu-id="403c4-284">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-285">Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-286">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-287">Lync Server-Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="403c4-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="403c4-288">8404</span><span class="sxs-lookup"><span data-stu-id="403c4-288">8404</span></span></p></td>
<td><p><span data-ttu-id="403c4-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-290">Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-291">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-292">Lync Server-bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="403c4-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="403c4-293">5080</span><span class="sxs-lookup"><span data-stu-id="403c4-293">5080</span></span></p></td>
<td><p><span data-ttu-id="403c4-294">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-295">Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-296">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-297">Lync Server-bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="403c4-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="403c4-298">448</span><span class="sxs-lookup"><span data-stu-id="403c4-298">448</span></span></p></td>
<td><p><span data-ttu-id="403c4-299">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-300">Wird für die Anrufsteuerung vom lync Server-bandbreitenrichtliniendienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-301">Front-End-Server, auf denen sich der zentrale Verwaltungsspeicher befindet</span><span class="sxs-lookup"><span data-stu-id="403c4-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="403c4-302">Lync Server-Master-Replicator-Agent-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="403c4-303">445</span><span class="sxs-lookup"><span data-stu-id="403c4-303">445</span></span></p></td>
<td><p><span data-ttu-id="403c4-304">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-305">Wird verwendet, um Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit lync Server zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="403c4-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-306">Alle Server</span><span class="sxs-lookup"><span data-stu-id="403c4-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-307">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="403c4-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="403c4-308">1434</span><span class="sxs-lookup"><span data-stu-id="403c4-308">1434</span></span></p></td>
<td><p><span data-ttu-id="403c4-309">UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-310">SQL-Browser für lokale replizierte Kopie von Daten des zentralen Verwaltungsspeichers in einer lokalen SQL Server-Instanz</span><span class="sxs-lookup"><span data-stu-id="403c4-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-311">Alle internen Server</span><span class="sxs-lookup"><span data-stu-id="403c4-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-312">Verschiedene</span><span class="sxs-lookup"><span data-stu-id="403c4-312">Various</span></span></p></td>
<td><p><span data-ttu-id="403c4-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="403c4-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="403c4-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-315">Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="403c4-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="403c4-316">Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für den lync Server Conferencing Attendant-Dienst, lync Server Conferencing Announcement Service und lync Server-Audio/Video Konferenzdienst) und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="403c4-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-317">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="403c4-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="403c4-318">443</span><span class="sxs-lookup"><span data-stu-id="403c4-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="403c4-319">Wird von lync Server 2013 zum Herstellen einer Verbindung mit Office Web Apps Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-320">Directors</span><span class="sxs-lookup"><span data-stu-id="403c4-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="403c4-321">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-322">5060</span><span class="sxs-lookup"><span data-stu-id="403c4-322">5060</span></span></p></td>
<td><p><span data-ttu-id="403c4-323">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-324">Wird optional für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-325">Directors</span><span class="sxs-lookup"><span data-stu-id="403c4-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="403c4-326">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-327">444</span><span class="sxs-lookup"><span data-stu-id="403c4-327">444</span></span></p></td>
<td><p><span data-ttu-id="403c4-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-328">HTTPS</span></span></p>
<p><span data-ttu-id="403c4-329">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-330">Serverübergreifende Kommunikation zwischen Front-End und Director.</span><span class="sxs-lookup"><span data-stu-id="403c4-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="403c4-331">Darüber hinaus veröffentlichen Clientzertifikate (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="403c4-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-332">Directors</span><span class="sxs-lookup"><span data-stu-id="403c4-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="403c4-333">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-334">80</span><span class="sxs-lookup"><span data-stu-id="403c4-334">80</span></span></p></td>
<td><p><span data-ttu-id="403c4-335">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-p105">Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="403c4-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-338">Directors</span><span class="sxs-lookup"><span data-stu-id="403c4-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="403c4-339">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="403c4-340">443</span><span class="sxs-lookup"><span data-stu-id="403c4-340">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="403c4-342">Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-343">Directors</span><span class="sxs-lookup"><span data-stu-id="403c4-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="403c4-344">Lync Server-Front-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="403c4-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="403c4-345">5061</span><span class="sxs-lookup"><span data-stu-id="403c4-345">5061</span></span></p></td>
<td><p><span data-ttu-id="403c4-346">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-347">Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-348">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="403c4-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-349">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-350">5070</span><span class="sxs-lookup"><span data-stu-id="403c4-350">5070</span></span></p></td>
<td><p><span data-ttu-id="403c4-351">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-352">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-353">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="403c4-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-354">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-355">5067</span><span class="sxs-lookup"><span data-stu-id="403c4-355">5067</span></span></p></td>
<td><p><span data-ttu-id="403c4-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-357">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-358">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="403c4-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-359">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-360">5068</span><span class="sxs-lookup"><span data-stu-id="403c4-360">5068</span></span></p></td>
<td><p><span data-ttu-id="403c4-361">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-362">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-363">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="403c4-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="403c4-364">Lync Server-Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="403c4-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="403c4-365">5070</span><span class="sxs-lookup"><span data-stu-id="403c4-365">5070</span></span></p></td>
<td><p><span data-ttu-id="403c4-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-367">Wird für SIP-Anforderungen von den Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-368">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-369">SIP für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="403c4-370">5041</span><span class="sxs-lookup"><span data-stu-id="403c4-370">5041</span></span></p></td>
<td><p><span data-ttu-id="403c4-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-372">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-373">Windows Communication Foundation (WCF) für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="403c4-374">881</span><span class="sxs-lookup"><span data-stu-id="403c4-374">881</span></span></p></td>
<td><p><span data-ttu-id="403c4-375">TCP (TLS) und TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-376">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="403c4-377">Dateiübertragungsdienst für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="403c4-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="403c4-378">443</span><span class="sxs-lookup"><span data-stu-id="403c4-378">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="403c4-380">In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich.</span><span class="sxs-lookup"><span data-stu-id="403c4-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="403c4-381">Obwohl der TCP-Port 5060 von lync Server nicht mehr verwendet wird, erstellen Sie während der Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director für die Verbindung mit dem PBX-System verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="403c4-382">Ausführliche Informationen finden Sie im <STRONG>CsTrustedApplicationComputer</STRONG> -Cmdlet in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="403c4-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="403c4-383">Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="403c4-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="403c4-384">Ports für Hardwaregeräte zum Lastenausgleich, wenn nur ein Hardwarelastenausgleich verwendet wird</span><span class="sxs-lookup"><span data-stu-id="403c4-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="403c4-385">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-385">Load Balancer</span></span></th>
<th><span data-ttu-id="403c4-386">Port</span><span class="sxs-lookup"><span data-stu-id="403c4-386">Port</span></span></th>
<th><span data-ttu-id="403c4-387">Protokoll</span><span class="sxs-lookup"><span data-stu-id="403c4-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="403c4-388">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-389">5061</span><span class="sxs-lookup"><span data-stu-id="403c4-389">5061</span></span></p></td>
<td><p><span data-ttu-id="403c4-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-391">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-392">444</span><span class="sxs-lookup"><span data-stu-id="403c4-392">444</span></span></p></td>
<td><p><span data-ttu-id="403c4-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-394">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-395">135</span><span class="sxs-lookup"><span data-stu-id="403c4-395">135</span></span></p></td>
<td><p><span data-ttu-id="403c4-396">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="403c4-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-397">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-398">80</span><span class="sxs-lookup"><span data-stu-id="403c4-398">80</span></span></p></td>
<td><p><span data-ttu-id="403c4-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="403c4-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-400">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-401">8080</span><span class="sxs-lookup"><span data-stu-id="403c4-401">8080</span></span></p></td>
<td><p><span data-ttu-id="403c4-402">TCP – Abruf des Stammzertifikats für Clients und Geräte über den Front-End-Server – NTLM-Authentifizierung der Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="403c4-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-403">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-404">443</span><span class="sxs-lookup"><span data-stu-id="403c4-404">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-406">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-407">4443</span><span class="sxs-lookup"><span data-stu-id="403c4-407">4443</span></span></p></td>
<td><p><span data-ttu-id="403c4-408">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="403c4-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-409">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-410">5072</span><span class="sxs-lookup"><span data-stu-id="403c4-410">5072</span></span></p></td>
<td><p><span data-ttu-id="403c4-411">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-412">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-413">5073</span><span class="sxs-lookup"><span data-stu-id="403c4-413">5073</span></span></p></td>
<td><p><span data-ttu-id="403c4-414">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-415">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-416">5075</span><span class="sxs-lookup"><span data-stu-id="403c4-416">5075</span></span></p></td>
<td><p><span data-ttu-id="403c4-417">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-418">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-419">5076</span><span class="sxs-lookup"><span data-stu-id="403c4-419">5076</span></span></p></td>
<td><p><span data-ttu-id="403c4-420">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-421">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-422">5071</span><span class="sxs-lookup"><span data-stu-id="403c4-422">5071</span></span></p></td>
<td><p><span data-ttu-id="403c4-423">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-424">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-425">5080</span><span class="sxs-lookup"><span data-stu-id="403c4-425">5080</span></span></p></td>
<td><p><span data-ttu-id="403c4-426">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-427">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-428">448</span><span class="sxs-lookup"><span data-stu-id="403c4-428">448</span></span></p></td>
<td><p><span data-ttu-id="403c4-429">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-430">Vermittlungsserver-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-431">5070</span><span class="sxs-lookup"><span data-stu-id="403c4-431">5070</span></span></p></td>
<td><p><span data-ttu-id="403c4-432">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-433">Front-End-Server-Lastenausgleichssystem (wenn im Pool auch ein Vermittlungsserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="403c4-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="403c4-434">5070</span><span class="sxs-lookup"><span data-stu-id="403c4-434">5070</span></span></p></td>
<td><p><span data-ttu-id="403c4-435">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-436">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-437">443</span><span class="sxs-lookup"><span data-stu-id="403c4-437">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-439">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-440">444</span><span class="sxs-lookup"><span data-stu-id="403c4-440">444</span></span></p></td>
<td><p><span data-ttu-id="403c4-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-442">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-443">5061</span><span class="sxs-lookup"><span data-stu-id="403c4-443">5061</span></span></p></td>
<td><p><span data-ttu-id="403c4-444">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-445">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-446">4443</span><span class="sxs-lookup"><span data-stu-id="403c4-446">4443</span></span></p></td>
<td><p><span data-ttu-id="403c4-447">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="403c4-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="403c4-p107">Für die Front-End- und Director-Pools, die DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle werden die Ports aufgeführt, die auf diesen Hardwaregeräten geöffnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="403c4-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="403c4-450">Ports für Hardwaregeräte zum Lastenausgleich, wenn DNS-Lastenausgleich verwendet wird</span><span class="sxs-lookup"><span data-stu-id="403c4-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="403c4-451">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-451">Load Balancer</span></span></th>
<th><span data-ttu-id="403c4-452">Port</span><span class="sxs-lookup"><span data-stu-id="403c4-452">Port</span></span></th>
<th><span data-ttu-id="403c4-453">Protokoll</span><span class="sxs-lookup"><span data-stu-id="403c4-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="403c4-454">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-455">80</span><span class="sxs-lookup"><span data-stu-id="403c4-455">80</span></span></p></td>
<td><p><span data-ttu-id="403c4-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="403c4-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-457">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-458">443</span><span class="sxs-lookup"><span data-stu-id="403c4-458">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-460">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-461">8080</span><span class="sxs-lookup"><span data-stu-id="403c4-461">8080</span></span></p></td>
<td><p><span data-ttu-id="403c4-462">TCP – Abruf des Stammzertifikats für Clients und Geräte über den Front-End-Server – NTLM-Authentifizierung der Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="403c4-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-463">Front-End-Server-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-464">4443</span><span class="sxs-lookup"><span data-stu-id="403c4-464">4443</span></span></p></td>
<td><p><span data-ttu-id="403c4-465">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="403c4-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-466">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-467">443</span><span class="sxs-lookup"><span data-stu-id="403c4-467">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="403c4-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-469">Director-Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="403c4-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="403c4-470">4443</span><span class="sxs-lookup"><span data-stu-id="403c4-470">4443</span></span></p></td>
<td><p><span data-ttu-id="403c4-471">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="403c4-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="403c4-472">Erforderliche Clientports</span><span class="sxs-lookup"><span data-stu-id="403c4-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="403c4-473">Komponente</span><span class="sxs-lookup"><span data-stu-id="403c4-473">Component</span></span></th>
<th><span data-ttu-id="403c4-474">Port</span><span class="sxs-lookup"><span data-stu-id="403c4-474">Port</span></span></th>
<th><span data-ttu-id="403c4-475">Protokoll</span><span class="sxs-lookup"><span data-stu-id="403c4-475">Protocol</span></span></th>
<th><span data-ttu-id="403c4-476">Hinweise</span><span class="sxs-lookup"><span data-stu-id="403c4-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="403c4-477">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-478">67/68</span><span class="sxs-lookup"><span data-stu-id="403c4-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="403c4-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="403c4-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-480">Wird von lync Server verwendet, um den FQDN der Registrierungsstelle zu finden (das heißt, wenn DNS SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).</span><span class="sxs-lookup"><span data-stu-id="403c4-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-481">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-482">443</span><span class="sxs-lookup"><span data-stu-id="403c4-482">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-484">Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-485">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-486">443</span><span class="sxs-lookup"><span data-stu-id="403c4-486">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-488">Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-489">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-490">443</span><span class="sxs-lookup"><span data-stu-id="403c4-490">443</span></span></p></td>
<td><p><span data-ttu-id="403c4-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="403c4-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="403c4-492">Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).</span><span class="sxs-lookup"><span data-stu-id="403c4-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-493">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-494">3478</span><span class="sxs-lookup"><span data-stu-id="403c4-494">3478</span></span></p></td>
<td><p><span data-ttu-id="403c4-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="403c4-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="403c4-496">Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).</span><span class="sxs-lookup"><span data-stu-id="403c4-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-497">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-498">5061</span><span class="sxs-lookup"><span data-stu-id="403c4-498">5061</span></span></p></td>
<td><p><span data-ttu-id="403c4-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="403c4-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="403c4-500">Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-501">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="403c4-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="403c4-503">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-504">Wird für die Dateiübertragung zwischen lync-Clients und vorherigen Clients (Clients von Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 und Live Communications Server 2005) verwendet.</span><span class="sxs-lookup"><span data-stu-id="403c4-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-505">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="403c4-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="403c4-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-508">Audioportbereich (mindestens 20 Ports erforderlich).</span><span class="sxs-lookup"><span data-stu-id="403c4-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-509">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="403c4-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="403c4-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="403c4-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="403c4-512">Videoportbereich (mindestens 20 Ports erforderlich).</span><span class="sxs-lookup"><span data-stu-id="403c4-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-513">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="403c4-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="403c4-515">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-516">Peer-zu-Peer-Dateiübertragungen (zur Übertragung von Konferenzdateien verwenden Clients PSOM-Verbindungen).</span><span class="sxs-lookup"><span data-stu-id="403c4-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="403c4-517">Clients</span><span class="sxs-lookup"><span data-stu-id="403c4-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="403c4-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="403c4-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="403c4-519">TCP</span><span class="sxs-lookup"><span data-stu-id="403c4-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-520">Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="403c4-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="403c4-521">Aastra 6721ip (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="403c4-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="403c4-522">Telefonapparat Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="403c4-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="403c4-523">IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="403c4-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="403c4-524">IP-Telefon HP 4120 (Telefonapparat)</span><span class="sxs-lookup"><span data-stu-id="403c4-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="403c4-525">IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="403c4-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="403c4-526">IP-Telefonapparat Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="403c4-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="403c4-527">IP-Telefonapparat Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="403c4-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="403c4-528">IP-Konferenztelefon Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="403c4-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="403c4-529">67/68</span><span class="sxs-lookup"><span data-stu-id="403c4-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="403c4-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="403c4-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="403c4-531">Wird von den aufgelisteten Geräten verwendet, um das lync Server-Zertifikat, den Bereitstellungs-FQDN und den FQDN der Registrierungsstelle zu finden.</span><span class="sxs-lookup"><span data-stu-id="403c4-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="403c4-532">**\*** Wenn Sie bestimmte Ports für diese Medientypen konfigurieren möchten, verwenden Sie das CsConferencingConfiguration-Cmdlet (ClientMediaPortRangeEnabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).</span><span class="sxs-lookup"><span data-stu-id="403c4-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="403c4-533">Mit den Einstellungen für lync-Clients werden die erforderlichen Ausnahmen für das Betriebssystem auf dem Clientcomputer automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="403c4-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="403c4-534">Die für den externen Benutzerzugriff verwendeten Ports werden für jedes Szenario benötigt, in dem der Client die Firewall der Organisation durchqueren muss (z. B. bei externer Kommunikation oder bei Besprechungen, die von anderen Organisationen gehostet werden).</span><span class="sxs-lookup"><span data-stu-id="403c4-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

