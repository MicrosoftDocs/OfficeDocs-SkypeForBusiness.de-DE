---
title: 'Lync Server 2013: Anrufsteuerung und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="93bf7-102">Anrufsteuerung und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93bf7-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93bf7-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="93bf7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="93bf7-104">Die Anrufannahme Steuerung (CAC), die erstmals in lync Server 2010 eingeführt wurde, verwaltet die Echtzeit-Sitzungseinrichtung auf der Grundlage der verfügbaren Bandbreite, um zu verhindern, dass Benutzer in überlasteten Netzwerken eine schlechte Arbeitsqualität (QoE) erzielen.</span><span class="sxs-lookup"><span data-stu-id="93bf7-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="93bf7-105">Zur Unterstützung dieser Funktion ist der Vermittlungs Server, der eine Signalisierungs-und Medienübersetzung zwischen der Enterprise-VoIP-Infrastruktur und einem Gateway-oder SIP-Trunking-Anbieter bereitstellt, für die Bandbreitenverwaltung für die beiden Interaktionen in lync verantwortlich. Server seitig und auf der Einstiegsseite.</span><span class="sxs-lookup"><span data-stu-id="93bf7-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="93bf7-106">Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung.</span><span class="sxs-lookup"><span data-stu-id="93bf7-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="93bf7-107">Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), mit denen der Vermittlungsserver auf der Einstiegsseite interagiert, unterstützen keine lync Server 2013-Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="93bf7-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="93bf7-108">Daher muss der Vermittlungs Server Bandbreiten Interaktionen im Auftrag seines Gateway-Peers verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="93bf7-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="93bf7-109">Wenn möglich, reserviert der Vermittlungs Server im Voraus eine Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="93bf7-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="93bf7-110">Wenn dies nicht möglich ist (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert.</span><span class="sxs-lookup"><span data-stu-id="93bf7-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="93bf7-111">Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="93bf7-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="93bf7-112">Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="93bf7-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="93bf7-113">Wenn für einen Anruf eine medienumgehung verwendet wird, wird für diesen Anruf keine Anrufsteuerung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="93bf7-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="93bf7-114">Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93bf7-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="93bf7-115">Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungs Server einbezieht, kann dieser Anruf keine medienumgehung verwenden.</span><span class="sxs-lookup"><span data-stu-id="93bf7-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="93bf7-116">Details zur medienumgehung oder zur Anrufsteuerung finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) oder [Planen der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="93bf7-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

