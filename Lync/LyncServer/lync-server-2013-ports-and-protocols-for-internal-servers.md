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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513402"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="a23ba-102">Ports und Protokolle für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a23ba-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a23ba-103">_**Letztes Änderungsstand des Themas:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="a23ba-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="a23ba-104">In diesem Abschnitt werden die von Servern, Lastenausgleichssystemen und Clients in einer lync Server-Bereitstellung verwendeten Ports und Protokolle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="a23ba-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a23ba-105">Lync-und Communicator-Clients werden, wenn Sie an einer Kommunikation mit einem einzelnen beteiligt sind, häufig als Peer-to-Peer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="a23ba-106">Technisch gesehen kommunizieren die beiden Clients in einer eins-zu-eins-Unterhaltung mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte.</span><span class="sxs-lookup"><span data-stu-id="a23ba-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="a23ba-107">IMMCU ist eine Komponente von Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="a23ba-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="a23ba-108">Wenn Sie die IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Aufzeichnung von Anrufdetails und andere Features, die der Front-End-Server aktiviert, aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a23ba-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="a23ba-109">Die Kommunikation erfolgt über einen dynamischen Quell Port auf dem Client zum Front-End-Server Port TLS/TCP/5061 (vorausgesetzt, dass die empfohlene Transportschichtsicherheit verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="a23ba-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="a23ba-110">Die Peer-zu-Peer-Kommunikation (sowie mehr Parteien-Chat) ist nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a23ba-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a23ba-111">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="a23ba-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a23ba-112">Die Windows-Firewall muss gestartet werden, bevor Sie die lync Server Dienste auf einem Server starten, da lync Server die erforderlichen Ports in der Firewall öffnet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="a23ba-113">Ausführliche Informationen zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a23ba-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="a23ba-114">In der folgenden Tabelle sind die Ports aufgeführt, die für jede interne Serverrolle geöffnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a23ba-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="a23ba-115">Erforderliche Serverports (nach Server Rolle)</span><span class="sxs-lookup"><span data-stu-id="a23ba-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="a23ba-116">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="a23ba-116">Server role</span></span></th>
<th><span data-ttu-id="a23ba-117">Dienstname</span><span class="sxs-lookup"><span data-stu-id="a23ba-117">Service name</span></span></th>
<th><span data-ttu-id="a23ba-118">Port</span><span class="sxs-lookup"><span data-stu-id="a23ba-118">Port</span></span></th>
<th><span data-ttu-id="a23ba-119">Protokoll</span><span class="sxs-lookup"><span data-stu-id="a23ba-119">Protocol</span></span></th>
<th><span data-ttu-id="a23ba-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a23ba-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-121">Alle Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-122">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="a23ba-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="a23ba-123">1434</span><span class="sxs-lookup"><span data-stu-id="a23ba-123">1434</span></span></p></td>
<td><p><span data-ttu-id="a23ba-124">UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-125">SQL-Browser für die lokale replizierte Kopie der zentraler Verwaltungsspeicher Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a23ba-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-126">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-127">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-128">5060</span><span class="sxs-lookup"><span data-stu-id="a23ba-128">5060</span></span></p></td>
<td><p><span data-ttu-id="a23ba-129">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-130">Optional von Standard Edition-Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-131">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-132">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-133">5061</span><span class="sxs-lookup"><span data-stu-id="a23ba-133">5061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-135">Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="a23ba-136">Wird auch für die Kommunikation mit Monitoring Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-137">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-138">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-139">444</span><span class="sxs-lookup"><span data-stu-id="a23ba-139">444</span></span></p></td>
<td><p><span data-ttu-id="a23ba-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-140">HTTPS</span></span></p>
<p><span data-ttu-id="a23ba-141">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-142">Wird für die HTTPS-Kommunikation zwischen dem Fokus (der lync Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="a23ba-143">Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-144">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-145">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-146">135</span><span class="sxs-lookup"><span data-stu-id="a23ba-146">135</span></span></p></td>
<td><p><span data-ttu-id="a23ba-147">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="a23ba-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-148">Wird für DCOM-basierte Vorgänge wie das Verschieben von Benutzern, die Benutzer Replikationssynchronisierung und die Adressbuchsynchronisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-149">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-150">Lync Server Sofortnachrichten-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-151">5062</span><span class="sxs-lookup"><span data-stu-id="a23ba-151">5062</span></span></p></td>
<td><p><span data-ttu-id="a23ba-152">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-153">Wird für eingehende SIP-Anforderungen für Chat Konferenzen (Instant Messaging) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-154">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-155">Lync Server Webkonferenzdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-156">8057</span><span class="sxs-lookup"><span data-stu-id="a23ba-156">8057</span></span></p></td>
<td><p><span data-ttu-id="a23ba-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-158">Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-159">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-160">Lync Server Webkonferenz-Kompatibilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-161">8058</span><span class="sxs-lookup"><span data-stu-id="a23ba-161">8058</span></span></p></td>
<td><p><span data-ttu-id="a23ba-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-163">Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) aus dem Live Meeting-Client und früheren Versionen von lync Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-164">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-165">Lync Server Audio/Video-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-166">5063</span><span class="sxs-lookup"><span data-stu-id="a23ba-166">5063</span></span></p></td>
<td><p><span data-ttu-id="a23ba-167">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-168">Wird für eingehende SIP-Anforderungen für Audio/Video-Konferenzen (A/V) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-169">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-170">Lync Server Audio/Video-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="a23ba-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="a23ba-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-173">Für Videokonferenzen verwendeter Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="a23ba-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-174">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-175">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-176">80</span><span class="sxs-lookup"><span data-stu-id="a23ba-176">80</span></span></p></td>
<td><p><span data-ttu-id="a23ba-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="a23ba-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-178">Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet, wenn kein HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a23ba-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-179">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-180">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-181">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-181">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a23ba-183">Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-184">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-185">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-186">8080</span><span class="sxs-lookup"><span data-stu-id="a23ba-186">8080</span></span></p></td>
<td><p><span data-ttu-id="a23ba-187">TCP und http</span><span class="sxs-lookup"><span data-stu-id="a23ba-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-188">Wird von Webkomponenten für den externen Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-189">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-190">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="a23ba-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-191">4443</span><span class="sxs-lookup"><span data-stu-id="a23ba-191">4443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a23ba-193">HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Pools für die Auto Ermittlungs Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="a23ba-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-194">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-195">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="a23ba-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-196">8060</span><span class="sxs-lookup"><span data-stu-id="a23ba-196">8060</span></span></p></td>
<td><p><span data-ttu-id="a23ba-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-198">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-199">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="a23ba-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-200">8061</span><span class="sxs-lookup"><span data-stu-id="a23ba-200">8061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-202">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-203">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="a23ba-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-204">5086</span><span class="sxs-lookup"><span data-stu-id="a23ba-204">5086</span></span></p></td>
<td><p><span data-ttu-id="a23ba-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-206">SIP-Port für interne Prozesse der Mobilitätsdienste</span><span class="sxs-lookup"><span data-stu-id="a23ba-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-207">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-208">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="a23ba-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-209">5087</span><span class="sxs-lookup"><span data-stu-id="a23ba-209">5087</span></span></p></td>
<td><p><span data-ttu-id="a23ba-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-211">SIP-Port für interne Prozesse der Mobilitätsdienste</span><span class="sxs-lookup"><span data-stu-id="a23ba-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-212">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-213">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="a23ba-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a23ba-214">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-214">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-216">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-217">Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="a23ba-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-218">5064</span><span class="sxs-lookup"><span data-stu-id="a23ba-218">5064</span></span></p></td>
<td><p><span data-ttu-id="a23ba-219">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-220">Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-221">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-222">Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="a23ba-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-223">5072</span><span class="sxs-lookup"><span data-stu-id="a23ba-223">5072</span></span></p></td>
<td><p><span data-ttu-id="a23ba-224">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-225">Wird für eingehende SIP-Anforderungen für Attendant (Einwahlkonferenzen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-226">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a23ba-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-227">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-228">5070</span><span class="sxs-lookup"><span data-stu-id="a23ba-228">5070</span></span></p></td>
<td><p><span data-ttu-id="a23ba-229">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-230">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-231">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a23ba-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-232">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-233">5067</span><span class="sxs-lookup"><span data-stu-id="a23ba-233">5067</span></span></p></td>
<td><p><span data-ttu-id="a23ba-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-235">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-236">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a23ba-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-237">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-238">5068</span><span class="sxs-lookup"><span data-stu-id="a23ba-238">5068</span></span></p></td>
<td><p><span data-ttu-id="a23ba-239">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-240">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-241">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a23ba-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-242">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-243">5081</span><span class="sxs-lookup"><span data-stu-id="a23ba-243">5081</span></span></p></td>
<td><p><span data-ttu-id="a23ba-244">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-245">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-246">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a23ba-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-247">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-248">5082</span><span class="sxs-lookup"><span data-stu-id="a23ba-248">5082</span></span></p></td>
<td><p><span data-ttu-id="a23ba-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-250">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-251">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-252">Lync Server Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-253">5065</span><span class="sxs-lookup"><span data-stu-id="a23ba-253">5065</span></span></p></td>
<td><p><span data-ttu-id="a23ba-254">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-255">Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-256">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-257">Lync Server Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="a23ba-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="a23ba-259">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-260">Für die Anwendungsfreigabe verwendete Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="a23ba-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-261">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-262">Lync Server Konferenz Ansagedienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-263">5073</span><span class="sxs-lookup"><span data-stu-id="a23ba-263">5073</span></span></p></td>
<td><p><span data-ttu-id="a23ba-264">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-265">Wird für eingehende SIP-Anforderungen für den lync Server Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-266">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-267">Lync Server Dienst zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="a23ba-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-268">5075</span><span class="sxs-lookup"><span data-stu-id="a23ba-268">5075</span></span></p></td>
<td><p><span data-ttu-id="a23ba-269">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-270">Wird für eingehende SIP-Anforderungen für den Anwendung zum Parken von Anrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-271">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-272">Lync Server Audio-Test Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-273">5076</span><span class="sxs-lookup"><span data-stu-id="a23ba-273">5076</span></span></p></td>
<td><p><span data-ttu-id="a23ba-274">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-275">Wird für eingehende SIP-Anforderungen für den Audio-Test Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-276">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-277">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a23ba-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="a23ba-278">5066</span><span class="sxs-lookup"><span data-stu-id="a23ba-278">5066</span></span></p></td>
<td><p><span data-ttu-id="a23ba-279">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-280">Wird für das ausgehende Enhanced 9-1-1 (E9-1-1)-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-281">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-282">Lync Server Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-283">5071</span><span class="sxs-lookup"><span data-stu-id="a23ba-283">5071</span></span></p></td>
<td><p><span data-ttu-id="a23ba-284">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-285">Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-286">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-287">Lync Server Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-288">8404</span><span class="sxs-lookup"><span data-stu-id="a23ba-288">8404</span></span></p></td>
<td><p><span data-ttu-id="a23ba-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-290">Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-291">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-292">Lync Server bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-293">5080</span><span class="sxs-lookup"><span data-stu-id="a23ba-293">5080</span></span></p></td>
<td><p><span data-ttu-id="a23ba-294">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-295">Wird für die Anrufsteuerung durch den bandbreitenrichtliniendienst für A/V-Edge-Umdrehungs Datenverkehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-296">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-297">Lync Server bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-298">448</span><span class="sxs-lookup"><span data-stu-id="a23ba-298">448</span></span></p></td>
<td><p><span data-ttu-id="a23ba-299">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-300">Wird für die Anrufsteuerung vom lync Server bandbreitenrichtliniendienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-301">Front-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet</span><span class="sxs-lookup"><span data-stu-id="a23ba-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="a23ba-302">Lync Server des Master Replicator-Agent-Diensts</span><span class="sxs-lookup"><span data-stu-id="a23ba-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-303">445</span><span class="sxs-lookup"><span data-stu-id="a23ba-303">445</span></span></p></td>
<td><p><span data-ttu-id="a23ba-304">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-305">Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit lync Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-306">Alle Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-307">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="a23ba-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="a23ba-308">1434</span><span class="sxs-lookup"><span data-stu-id="a23ba-308">1434</span></span></p></td>
<td><p><span data-ttu-id="a23ba-309">UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-310">SQL-Browser für lokale replizierte Kopie der Daten des zentralen Verwaltungsspeichers in der lokalen SQL Server Instanz</span><span class="sxs-lookup"><span data-stu-id="a23ba-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-311">Alle internen Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-312">Verschiedene</span><span class="sxs-lookup"><span data-stu-id="a23ba-312">Various</span></span></p></td>
<td><p><span data-ttu-id="a23ba-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="a23ba-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="a23ba-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-315">Medienportbereich, der für Audiokonferenzen auf allen internen Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a23ba-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="a23ba-316">Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für lync Server Konferenz Aufsichtsdienst, lync Server Konferenzankündigungsdienst und lync Server Audio/Video-Konferenzdienst) und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="a23ba-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-317">Office-webapps-Server</span><span class="sxs-lookup"><span data-stu-id="a23ba-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a23ba-318">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a23ba-319">Wird von lync Server 2013 verwendet, um eine Verbindung mit Office-webapps Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a23ba-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-320">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="a23ba-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="a23ba-321">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-322">5060</span><span class="sxs-lookup"><span data-stu-id="a23ba-322">5060</span></span></p></td>
<td><p><span data-ttu-id="a23ba-323">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-324">Optional für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-325">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="a23ba-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="a23ba-326">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-327">444</span><span class="sxs-lookup"><span data-stu-id="a23ba-327">444</span></span></p></td>
<td><p><span data-ttu-id="a23ba-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-328">HTTPS</span></span></p>
<p><span data-ttu-id="a23ba-329">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-330">Kommunikation zwischen Servern zwischen Front-End und Director.</span><span class="sxs-lookup"><span data-stu-id="a23ba-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="a23ba-331">Darüber hinaus veröffentlichen Clientzertifikate (an Front-End-Server) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="a23ba-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-332">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="a23ba-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="a23ba-333">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-334">80</span><span class="sxs-lookup"><span data-stu-id="a23ba-334">80</span></span></p></td>
<td><p><span data-ttu-id="a23ba-335">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-336">Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="a23ba-337">Im normalen Betrieb wechselt zum HTTPS-Datenverkehr unter Verwendung von Port 443 und Protokolltyp TCP.</span><span class="sxs-lookup"><span data-stu-id="a23ba-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-338">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="a23ba-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="a23ba-339">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-340">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-340">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a23ba-342">Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-343">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="a23ba-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="a23ba-344">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-345">5061</span><span class="sxs-lookup"><span data-stu-id="a23ba-345">5061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-346">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-347">Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-348">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a23ba-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-349">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-350">5070</span><span class="sxs-lookup"><span data-stu-id="a23ba-350">5070</span></span></p></td>
<td><p><span data-ttu-id="a23ba-351">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-352">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-353">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a23ba-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-354">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-355">5067</span><span class="sxs-lookup"><span data-stu-id="a23ba-355">5067</span></span></p></td>
<td><p><span data-ttu-id="a23ba-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-357">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-358">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a23ba-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-359">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-360">5068</span><span class="sxs-lookup"><span data-stu-id="a23ba-360">5068</span></span></p></td>
<td><p><span data-ttu-id="a23ba-361">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-362">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-363">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a23ba-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a23ba-364">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a23ba-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-365">5070</span><span class="sxs-lookup"><span data-stu-id="a23ba-365">5070</span></span></p></td>
<td><p><span data-ttu-id="a23ba-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-367">Wird für SIP-Anforderungen von den Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-368">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-369">SIP für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-370">5041</span><span class="sxs-lookup"><span data-stu-id="a23ba-370">5041</span></span></p></td>
<td><p><span data-ttu-id="a23ba-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-372">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-373">Windows Communication Foundation (WCF) für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-374">881</span><span class="sxs-lookup"><span data-stu-id="a23ba-374">881</span></span></p></td>
<td><p><span data-ttu-id="a23ba-375">TCP (TLS) und TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-376">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a23ba-377">Dateiübertragungsdienst für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a23ba-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="a23ba-378">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-378">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a23ba-380">Einige Szenarien für die Remoteanrufsteuerung erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="a23ba-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="a23ba-381">Obwohl lync Server TCP-Port 5060 nicht mehr verwendet, erstellen Sie während der Bereitstellung von Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem PBX-System verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="a23ba-382">Ausführliche Informationen finden Sie im <STRONG>CsTrustedApplicationComputer</STRONG> -Cmdlet in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a23ba-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="a23ba-383">Für Ihre Pools, in denen nur Hardwarelastenausgleich (nicht DNS-Lastenausgleich) verwendet wird, werden in der folgenden Tabelle die Ports aufgeführt, die zum Öffnen der Hardwarelastenausgleichs-Geräte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a23ba-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="a23ba-384">Hardware Lastenausgleichs-Ports bei Verwendung von nur Hardwarelastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a23ba-385">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="a23ba-385">Load Balancer</span></span></th>
<th><span data-ttu-id="a23ba-386">Port</span><span class="sxs-lookup"><span data-stu-id="a23ba-386">Port</span></span></th>
<th><span data-ttu-id="a23ba-387">Protokoll</span><span class="sxs-lookup"><span data-stu-id="a23ba-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-388">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-389">5061</span><span class="sxs-lookup"><span data-stu-id="a23ba-389">5061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-391">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-392">444</span><span class="sxs-lookup"><span data-stu-id="a23ba-392">444</span></span></p></td>
<td><p><span data-ttu-id="a23ba-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-394">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-395">135</span><span class="sxs-lookup"><span data-stu-id="a23ba-395">135</span></span></p></td>
<td><p><span data-ttu-id="a23ba-396">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="a23ba-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-397">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-398">80</span><span class="sxs-lookup"><span data-stu-id="a23ba-398">80</span></span></p></td>
<td><p><span data-ttu-id="a23ba-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="a23ba-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-400">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-401">8080</span><span class="sxs-lookup"><span data-stu-id="a23ba-401">8080</span></span></p></td>
<td><p><span data-ttu-id="a23ba-402">TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="a23ba-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-403">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-404">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-404">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-406">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-407">4443</span><span class="sxs-lookup"><span data-stu-id="a23ba-407">4443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-408">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="a23ba-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-409">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-410">5072</span><span class="sxs-lookup"><span data-stu-id="a23ba-410">5072</span></span></p></td>
<td><p><span data-ttu-id="a23ba-411">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-412">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-413">5073</span><span class="sxs-lookup"><span data-stu-id="a23ba-413">5073</span></span></p></td>
<td><p><span data-ttu-id="a23ba-414">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-415">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-416">5075</span><span class="sxs-lookup"><span data-stu-id="a23ba-416">5075</span></span></p></td>
<td><p><span data-ttu-id="a23ba-417">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-418">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-419">5076</span><span class="sxs-lookup"><span data-stu-id="a23ba-419">5076</span></span></p></td>
<td><p><span data-ttu-id="a23ba-420">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-421">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-422">5071</span><span class="sxs-lookup"><span data-stu-id="a23ba-422">5071</span></span></p></td>
<td><p><span data-ttu-id="a23ba-423">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-424">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-425">5080</span><span class="sxs-lookup"><span data-stu-id="a23ba-425">5080</span></span></p></td>
<td><p><span data-ttu-id="a23ba-426">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-427">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-428">448</span><span class="sxs-lookup"><span data-stu-id="a23ba-428">448</span></span></p></td>
<td><p><span data-ttu-id="a23ba-429">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-430">Vermittlungsserver Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-431">5070</span><span class="sxs-lookup"><span data-stu-id="a23ba-431">5070</span></span></p></td>
<td><p><span data-ttu-id="a23ba-432">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-433">Front-End-Server Lastenausgleich (wenn der Pool auch Vermittlungsserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="a23ba-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-434">5070</span><span class="sxs-lookup"><span data-stu-id="a23ba-434">5070</span></span></p></td>
<td><p><span data-ttu-id="a23ba-435">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-436">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-437">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-437">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-439">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-440">444</span><span class="sxs-lookup"><span data-stu-id="a23ba-440">444</span></span></p></td>
<td><p><span data-ttu-id="a23ba-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-442">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-443">5061</span><span class="sxs-lookup"><span data-stu-id="a23ba-443">5061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-444">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-445">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-446">4443</span><span class="sxs-lookup"><span data-stu-id="a23ba-446">4443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-447">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="a23ba-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a23ba-448">Für die Front-End-Pools und Director-Pools, die den DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a23ba-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="a23ba-449">In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwarelastenausgleichs-Geräte geöffnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a23ba-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="a23ba-450">Hardware Lastenausgleichs-Ports bei Verwendung des DNS-Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="a23ba-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a23ba-451">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="a23ba-451">Load Balancer</span></span></th>
<th><span data-ttu-id="a23ba-452">Port</span><span class="sxs-lookup"><span data-stu-id="a23ba-452">Port</span></span></th>
<th><span data-ttu-id="a23ba-453">Protokoll</span><span class="sxs-lookup"><span data-stu-id="a23ba-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-454">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-455">80</span><span class="sxs-lookup"><span data-stu-id="a23ba-455">80</span></span></p></td>
<td><p><span data-ttu-id="a23ba-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="a23ba-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-457">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-458">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-458">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-460">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-461">8080</span><span class="sxs-lookup"><span data-stu-id="a23ba-461">8080</span></span></p></td>
<td><p><span data-ttu-id="a23ba-462">TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="a23ba-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-463">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-464">4443</span><span class="sxs-lookup"><span data-stu-id="a23ba-464">4443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-465">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="a23ba-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-466">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-467">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-467">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a23ba-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-469">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a23ba-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a23ba-470">4443</span><span class="sxs-lookup"><span data-stu-id="a23ba-470">4443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-471">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="a23ba-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="a23ba-472">Erforderliche Client-Ports</span><span class="sxs-lookup"><span data-stu-id="a23ba-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a23ba-473">Komponente</span><span class="sxs-lookup"><span data-stu-id="a23ba-473">Component</span></span></th>
<th><span data-ttu-id="a23ba-474">Port</span><span class="sxs-lookup"><span data-stu-id="a23ba-474">Port</span></span></th>
<th><span data-ttu-id="a23ba-475">Protokoll</span><span class="sxs-lookup"><span data-stu-id="a23ba-475">Protocol</span></span></th>
<th><span data-ttu-id="a23ba-476">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a23ba-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-477">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-478">67/68</span><span class="sxs-lookup"><span data-stu-id="a23ba-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="a23ba-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-480">Wird von lync Server verwendet, um den FQDN des Registrars zu finden (wenn DNS-SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).</span><span class="sxs-lookup"><span data-stu-id="a23ba-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-481">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-482">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-482">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-484">Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-485">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-486">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-486">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-488">Wird für den Zugriff durch externe Benutzer auf Webkonferenz Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-489">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-490">443</span><span class="sxs-lookup"><span data-stu-id="a23ba-490">443</span></span></p></td>
<td><p><span data-ttu-id="a23ba-491">TCP (Stun/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="a23ba-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-492">Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (TCP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-493">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-494">3478</span><span class="sxs-lookup"><span data-stu-id="a23ba-494">3478</span></span></p></td>
<td><p><span data-ttu-id="a23ba-495">UDP (Stun/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="a23ba-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-496">Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (UDP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-497">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-498">5061</span><span class="sxs-lookup"><span data-stu-id="a23ba-498">5061</span></span></p></td>
<td><p><span data-ttu-id="a23ba-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a23ba-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a23ba-500">Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-501">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="a23ba-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="a23ba-503">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-504">Wird für die Dateiübertragung zwischen lync-Clients und vorherigen Clients (Clients von Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 und Live Communications Server 2005) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a23ba-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-505">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a23ba-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a23ba-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-508">Audioport Bereich (mindestens 20 Ports erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a23ba-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-509">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a23ba-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a23ba-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a23ba-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-512">Video Portbereich (mindestens 20 Ports erforderlich).</span><span class="sxs-lookup"><span data-stu-id="a23ba-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-513">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a23ba-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a23ba-515">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-516">Peer-zu-Peer-Dateiübertragung (für die Übertragung von Konferenz Dateien verwenden Clients PSOM).</span><span class="sxs-lookup"><span data-stu-id="a23ba-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23ba-517">Clients</span><span class="sxs-lookup"><span data-stu-id="a23ba-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="a23ba-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a23ba-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a23ba-519">TCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-520">Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="a23ba-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23ba-521">Aastra 6721ip (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="a23ba-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="a23ba-522">Telefonapparat Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="a23ba-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="a23ba-523">IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="a23ba-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="a23ba-524">IP-Telefon HP 4120 (Telefonapparat)</span><span class="sxs-lookup"><span data-stu-id="a23ba-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="a23ba-525">IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="a23ba-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="a23ba-526">IP-Telefonapparat Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="a23ba-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="a23ba-527">Polycom CX700-IP-Tischtelefon</span><span class="sxs-lookup"><span data-stu-id="a23ba-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="a23ba-528">IP-Konferenztelefon
Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="a23ba-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="a23ba-529">67/68</span><span class="sxs-lookup"><span data-stu-id="a23ba-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="a23ba-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="a23ba-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="a23ba-531">Wird von den aufgelisteten Geräten verwendet, um das lync Server Zertifikat, den FQDN der Feststellung und den FQDN der Registrierung zu finden.</span><span class="sxs-lookup"><span data-stu-id="a23ba-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a23ba-532">**\*** Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das CsConferencingConfiguration-Cmdlet (Parameter clientmediaportrangeenabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).</span><span class="sxs-lookup"><span data-stu-id="a23ba-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a23ba-533">Die festgelegten Programme für lync-Clients erstellen automatisch die erforderlichen Betriebssystem-Firewall-Ausnahmen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="a23ba-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a23ba-534">Die Ports, die für den Zugriff durch externe Benutzer verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (beispielsweise externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden).</span><span class="sxs-lookup"><span data-stu-id="a23ba-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

