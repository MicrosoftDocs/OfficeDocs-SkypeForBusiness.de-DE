---
title: 'Lync Server 2013: Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="716a5-102">Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="716a5-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="716a5-103">_**Letztes Änderungsdatum des Themas:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="716a5-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="716a5-104">Um Ihre Firewall für Ports und Protokolle zu konfigurieren, die für die Unterstützung öffentlicher Instant Messaging-Konnektivität erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Möglichkeit von Kontakten im öffentlichen Chat-Anbieter zu berücksichtigen, lync-Clients zu kontaktieren, oder lync Kontakt mit öffentlichen Chat Kontakten aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="716a5-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="716a5-105">Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="716a5-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="716a5-106">Damit wird die sehr ähnliche Firewall-Port-und-Protokollkonfiguration berücksichtigt, die Sie normalerweise auf der Firewall haben, um lync-Clients als externe Benutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="716a5-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="716a5-107">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="716a5-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="716a5-108">Für den Verbund mit Windows Live Messenger sind keine weiteren Benutzer-und Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="716a5-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="716a5-109">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="716a5-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="716a5-110">Die Föderation mit Messenger-Client Kontakten endet am 15. März 2013, mit Ausnahme des chinesischen Festlandes.</span><span class="sxs-lookup"><span data-stu-id="716a5-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="716a5-111">Skype wird zum Verbund Client für Föderationsbenutzer, die Messenger zuvor verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="716a5-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="716a5-112">Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="716a5-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="716a5-113">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="716a5-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="716a5-114">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="716a5-114">Source IP address</span></span></th>
<th><span data-ttu-id="716a5-115">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="716a5-115">Destination IP address</span></span></th>
<th><span data-ttu-id="716a5-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="716a5-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="716a5-117">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="716a5-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="716a5-118">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="716a5-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="716a5-119">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-120">Für Verbund-und öffentliche Chat Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="716a5-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716a5-121">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="716a5-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="716a5-122">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-123">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="716a5-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="716a5-124">Für Verbund-und öffentliche Chat Verbindungen, die SIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="716a5-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="716a5-125">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="716a5-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="716a5-126">Clients</span><span class="sxs-lookup"><span data-stu-id="716a5-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="716a5-127">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-128">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="716a5-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716a5-129">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="716a5-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="716a5-130">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-131">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="716a5-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="716a5-132">Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="716a5-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="716a5-133">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="716a5-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="716a5-134">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-135">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="716a5-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="716a5-136">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="716a5-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716a5-137">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="716a5-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="716a5-138">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="716a5-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="716a5-139">Edge-Server-Zugriffs Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716a5-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="716a5-140">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="716a5-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="716a5-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="716a5-141">See Also</span></span>


[<span data-ttu-id="716a5-142">Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="716a5-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="716a5-143">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="716a5-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

