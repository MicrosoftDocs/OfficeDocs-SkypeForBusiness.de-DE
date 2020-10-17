---
title: 'Lync Server 2013: Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten'
description: 'Lync Server 2013: Port Summary – Verbindung mit öffentlichen Instant Messaging-Diensten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543061"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="71f2f-103">Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f2f-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f2f-104">_**Letztes Änderungsstand des Themas:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="71f2f-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="71f2f-105">Wenn Sie die Firewall für Ports und Protokolle konfigurieren möchten, die für die Unterstützung von öffentlichen Instant Messaging-Verbindungen erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Fähigkeit von Kontakten im öffentlichen Sofortnachrichtenanbieter zum Kontaktieren von lync-Clients zu berücksichtigen, oder dass lync Kontakt mit öffentlichen Chat Kontakten aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="71f2f-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="71f2f-106">Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="71f2f-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="71f2f-107">Dies berücksichtigt die sehr ähnliche Firewall-Port-und Protokollkonfiguration, die Sie in der Regel für die Firewall zur Unterstützung von lync-Clients als externe Benutzer haben würden.</span><span class="sxs-lookup"><span data-stu-id="71f2f-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71f2f-108">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="71f2f-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="71f2f-109">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="71f2f-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="71f2f-110">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="71f2f-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="71f2f-111">Partnerverbund mit Messenger-Client Kontakten wird offiziell am 15. März 2013 mit Ausnahme des chinesischen Festland enden.</span><span class="sxs-lookup"><span data-stu-id="71f2f-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="71f2f-112">Skype wird zum Verbund Client für Verbundbenutzer, die zuvor Messenger verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="71f2f-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="71f2f-113">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="71f2f-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71f2f-114">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="71f2f-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="71f2f-115">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="71f2f-115">Source IP address</span></span></th>
<th><span data-ttu-id="71f2f-116">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="71f2f-116">Destination IP address</span></span></th>
<th><span data-ttu-id="71f2f-117">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="71f2f-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71f2f-118">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="71f2f-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="71f2f-119">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="71f2f-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="71f2f-120">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-121">Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="71f2f-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f2f-122">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="71f2f-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="71f2f-123">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-124">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="71f2f-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="71f2f-125">Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="71f2f-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f2f-126">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="71f2f-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="71f2f-127">Clients</span><span class="sxs-lookup"><span data-stu-id="71f2f-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="71f2f-128">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-129">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="71f2f-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f2f-130">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="71f2f-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="71f2f-131">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-132">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="71f2f-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="71f2f-133">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="71f2f-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f2f-134">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="71f2f-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="71f2f-135">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-136">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="71f2f-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="71f2f-137">Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="71f2f-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f2f-138">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="71f2f-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="71f2f-139">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="71f2f-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="71f2f-140">Edgeserver Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71f2f-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="71f2f-141">Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="71f2f-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71f2f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71f2f-142">See Also</span></span>


[<span data-ttu-id="71f2f-143">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f2f-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="71f2f-144">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f2f-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

