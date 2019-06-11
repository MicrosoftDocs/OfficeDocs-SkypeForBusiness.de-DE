---
title: 'Lync Server 2013: Übersicht über die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="58bcc-102">Übersicht über die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58bcc-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58bcc-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="58bcc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="58bcc-104">Die medienumgehung ist nützlich, wenn Sie die Anzahl der bereitgestellten Vermittlungsserver minimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="58bcc-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="58bcc-105">In der Regel wird ein Vermittlungs Server Pool an einem zentralen Standort bereitgestellt, und er steuert Gateways an Zweigstellen.</span><span class="sxs-lookup"><span data-stu-id="58bcc-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="58bcc-106">Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="58bcc-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="58bcc-107">Lync Server 2013-ausgehende Anrufrouten und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="58bcc-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="58bcc-p102">In Wi-Fi-Netzwerken treten üblicherweise mehr Paketverluste auf als in verkabelten Netzwerken. Die Wiederherstellung der Daten aus diesen Paketen kann normalerweise nicht mithilfe von Gateways durchgeführt werden. Daher wird empfohlen, die Qualität eines Wi-Fi-Netzwerks auszuwerten, bevor Sie entscheiden, ob die Medienumgehung für ein Funksubnetz aktiviert werden soll. Darüber hinaus muss erwogen werden, ob eine geringere Latenz zu Lasten der Dateiwiederherstellung nach Paketverlusten akzeptabel ist. RTAudio - ein Codec für Anrufe, die den Vermittlungsserver nicht umgehen - eignet sich besser für die Verarbeitung von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="58bcc-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="58bcc-113">Nachdem Ihre Enterprise-VoIP-Struktur vorhanden ist, ist die Planung der medienumgehung einfach.</span><span class="sxs-lookup"><span data-stu-id="58bcc-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="58bcc-114">Wenn Sie über eine zentralisierte Topologie ohne WAN-Verbindungen mit Zweigstellenstandorten verfügen, können Sie die globale Medienumgehung aktivieren, da eine genaue Steuerung nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="58bcc-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="58bcc-115">Wenn Sie dagegen eine verteilte Topologie mit mehreren Netzwerkregionen und zugehörigen Zweigstellenstandorten eingerichtet haben, müssen Sie sich die folgenden Fragen stellen:</span><span class="sxs-lookup"><span data-stu-id="58bcc-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="58bcc-116">Können die Vermittlungsserverpeers die für die Medienumgehung erforderlichen Funktionen unterstützen?</span><span class="sxs-lookup"><span data-stu-id="58bcc-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="58bcc-117">Welche Standorte in den jeweiligen Netzwerkregionen verfügen über eine gute Verbindung?</span><span class="sxs-lookup"><span data-stu-id="58bcc-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="58bcc-118">Welche Kombination aus Medienumgehung und Anrufsteuerung eignet sich für Ihr Netzwerk?</span><span class="sxs-lookup"><span data-stu-id="58bcc-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="58bcc-p103">Wenn Sie die Medienumgehung aktivieren, wird automatisch eine eindeutige Umgehungs-ID für eine Netzwerkregion und für alle Netzwerkstandorte ohne Bandbreiteneinschränkungen innerhalb dieser Region generiert. Standorte mit Bandbreiteneinschränkungen innerhalb der Region und Standorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen mit der Region verbunden sind, erhalten jeweils eine eigene eindeutige Umgehungs-IDs.</span><span class="sxs-lookup"><span data-stu-id="58bcc-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="58bcc-121">Wenn ein Benutzer einen Anruf an das PSTN tätigt, vergleicht der Vermittlungs Server die Bypass-ID des Client-Subnets mit der Bypass-ID des Gateway-Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="58bcc-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="58bcc-122">Wenn die beiden Umgehungs-IDs übereinstimmen, wird für den Anruf die Medienumgehung verwendet.</span><span class="sxs-lookup"><span data-stu-id="58bcc-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="58bcc-123">Wenn die Bypass-IDs nicht übereinstimmen, müssen Medien für den Anruf über den Vermittlungs Server fließen.</span><span class="sxs-lookup"><span data-stu-id="58bcc-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="58bcc-124">Erhält ein Benutzer einen Anruf aus dem PSTN, vergleicht der Client des Benutzers seine Umgehungs-ID mit der des PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="58bcc-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="58bcc-125">Wenn die beiden IDs übereinstimmen, fließt das Medium direkt vom Gateway zum Client, wobei der Vermittlungs Server umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="58bcc-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="58bcc-126">Nur lync 2010 oder höher Clients und Geräte unterstützen Medien Umgehungs Interaktionen mit einem Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="58bcc-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58bcc-p106">Zusätzlich zur globalen Aktivierung der Medienumgehung müssen Sie die Medienumgehung auf jedem PSTN-Trunk einzeln aktivieren. Wenn die Umgehung zwar global, jedoch für einen bestimmten PSTN-Trunk nicht aktiviert wurde, wird sie für Anrufe über diesen PSTN-Trunk nicht ausgelöst. Darüber hinaus müssen Sie alle routingfähigen Subnetze den Standorten zuordnen, in denen sie sich befinden, wenn die Medienumgehung auf <STRONG>Informationen zu Standort und Region verwenden</STRONG> festgelegt ist. Routingfähige Subnetze in einem Standort, für den eine Medienumgehung nicht gewünscht wird, sollten vor Aktivierung der Umgehung in einem neuen Standort gruppiert werden. Auf diese Weise stellen Sie sicher, dass den nicht routingfähigen Subnetzen eine andere Umgehungs-ID zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="58bcc-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58bcc-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58bcc-132">See Also</span></span>


[<span data-ttu-id="58bcc-133">Modi für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58bcc-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="58bcc-134">Medienumgehung und Anrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58bcc-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="58bcc-135">Technische Anforderungen für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58bcc-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

