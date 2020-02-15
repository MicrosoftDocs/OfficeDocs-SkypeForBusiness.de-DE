---
title: Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5aaa6-102">Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5aaa6-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5aaa6-103">_**Letztes Änderungsstand des Themas:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="5aaa6-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="5aaa6-104">Port-, Protokoll-und Firewall-Anforderungen für den Verbund mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server ähneln denen für die bereitgestellte Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="5aaa6-105">Clients initiieren die Kommunikation mit dem Zugriffs-Edgedienst über TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="5aaa6-106">Verbundpartner initiieren jedoch die Kommunikation mit dem Zugriffs-Edgedienst über MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="5aaa6-107">Wenn Sie die Firewall für Ports und Protokolle konfigurieren möchten, die für die Unterstützung von öffentlichen Instant Messaging-Verbindungen erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Fähigkeit von Kontakten im öffentlichen Sofortnachrichtenanbieter zum Kontaktieren von lync-Clients zu berücksichtigen, oder dass lync Kontakt mit öffentlichen Chat Kontakten aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="5aaa6-108">Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="5aaa6-109">Dies berücksichtigt die sehr ähnliche Firewall-Port-und Protokollkonfiguration, die Sie in der Regel für die Firewall zur Unterstützung von lync-Clients als externe Benutzer haben würden.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5aaa6-110">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5aaa6-111">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="5aaa6-112">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="5aaa6-113">Partnerverbund mit Messenger-Client Kontakten wird offiziell am 15. März 2013 mit Ausnahme des chinesischen Festland enden.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="5aaa6-114">Skype wird zum Verbund Client für Verbundbenutzer, die zuvor Messenger verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="5aaa6-115">Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation vom XMPP-Verbundpartner zum Edgeserver und erlauben auch die Kommunikation von Ihrem Edgeserver zur xmpp. Verbundpartner.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="5aaa6-116">Eine Regel wird auch in der internen Firewall aus dem Front-End-Server oder Front-End-Pool zum Edgeserver oder Edgepool definiert.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="5aaa6-117">Firewall-Zusammenfassung-SIP-Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="5aaa6-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aaa6-118">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5aaa6-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5aaa6-119">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5aaa6-119">Source IP address</span></span></th>
<th><span data-ttu-id="5aaa6-120">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5aaa6-120">Destination IP address</span></span></th>
<th><span data-ttu-id="5aaa6-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5aaa6-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-122">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5aaa6-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-123">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="5aaa6-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-124">Any</span><span class="sxs-lookup"><span data-stu-id="5aaa6-124">Any</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-125">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="5aaa6-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5aaa6-126">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="5aaa6-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aaa6-127">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5aaa6-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5aaa6-128">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5aaa6-128">Source IP address</span></span></th>
<th><span data-ttu-id="5aaa6-129">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5aaa6-129">Destination IP address</span></span></th>
<th><span data-ttu-id="5aaa6-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5aaa6-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-131">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5aaa6-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-132">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="5aaa6-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-133">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-134">Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aaa6-135">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5aaa6-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-136">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-137">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="5aaa6-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-138">Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-139">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5aaa6-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-140">Clients</span><span class="sxs-lookup"><span data-stu-id="5aaa6-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-141">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-142">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aaa6-143">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5aaa6-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-144">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-145">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5aaa6-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-146">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-147">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5aaa6-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-148">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-149">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5aaa6-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-150">Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aaa6-151">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5aaa6-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-152">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5aaa6-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-153">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-154">Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="5aaa6-155">Zusammenfassung der Firewall – xmpp (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="5aaa6-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aaa6-156">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5aaa6-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5aaa6-157">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5aaa6-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="5aaa6-158">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5aaa6-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="5aaa6-159">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="5aaa6-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5aaa6-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-161">Any</span><span class="sxs-lookup"><span data-stu-id="5aaa6-161">Any</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-162">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-163">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5aaa6-164">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="5aaa6-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aaa6-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5aaa6-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-166">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5aaa6-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-167">Any</span><span class="sxs-lookup"><span data-stu-id="5aaa6-167">Any</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-168">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5aaa6-169">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="5aaa6-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aaa6-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="5aaa6-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-171">Any</span><span class="sxs-lookup"><span data-stu-id="5aaa6-171">Any</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-172">Interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="5aaa6-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="5aaa6-173">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zum Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5aaa6-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5aaa6-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aaa6-174">See Also</span></span>


[<span data-ttu-id="5aaa6-175">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5aaa6-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="5aaa6-176">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5aaa6-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="5aaa6-177">Verwalten von XMPP-Verbundpartnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5aaa6-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

