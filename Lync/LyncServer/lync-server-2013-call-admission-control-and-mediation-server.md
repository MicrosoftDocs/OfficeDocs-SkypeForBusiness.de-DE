---
title: 'Lync Server 2013: Anrufsteuerung und Vermittlungsserver'
description: 'Lync Server 2013: Anrufsteuerung und Vermittlungsserver.'
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
ms.openlocfilehash: 77e4b12a11f941923d50f3ffcab7a8f9b6a9edc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569221"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="d3c57-103">Anrufsteuerung und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3c57-103">Call admission control and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3c57-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d3c57-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d3c57-105">Die Anrufsteuerung (Call Admission Control, CAC), die erstmals in lync Server 2010 eingeführt wurde, verwaltet die Einrichtung einer Echtzeitsitzung basierend auf der verfügbaren Bandbreite, um zu verhindern, dass Benutzer in überlasteten Netzwerken eine schlechte Qualität (QoE) erzielen.</span><span class="sxs-lookup"><span data-stu-id="d3c57-105">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="d3c57-106">Zur Unterstützung dieser Funktion ist die Vermittlungsserver, die die Signal-und Medienübersetzung zwischen der Enterprise-VoIP-Infrastruktur und einem Gateway-oder SIP-Trunking-Anbieter bereitstellt, für die Bandbreitenverwaltung für die beiden Interaktionen auf der lync Server Seite und auf der Gatewayseite verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="d3c57-106">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="d3c57-107">Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung.</span><span class="sxs-lookup"><span data-stu-id="d3c57-107">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="d3c57-108">Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), auf die der Vermittlungsserver auf der Gatewayseite interagiert, unterstützen lync Server 2013 Anrufsteuerung nicht.</span><span class="sxs-lookup"><span data-stu-id="d3c57-108">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="d3c57-109">Daher muss der Vermittlungsserver Bandbreiten Interaktionen im Namen seines Gateway-Peers verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3c57-109">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="d3c57-110">Wann immer möglich, reserviert der Vermittlungsserver Bandbreite im Voraus ab.</span><span class="sxs-lookup"><span data-stu-id="d3c57-110">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="d3c57-111">Ist dies nicht möglich (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert.</span><span class="sxs-lookup"><span data-stu-id="d3c57-111">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="d3c57-112">Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d3c57-112">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="d3c57-113">Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="d3c57-113">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="d3c57-114">Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d3c57-114">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="d3c57-115">Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c57-115">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="d3c57-116">Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der die Vermittlungsserver umfasst, kann dieser Anruf keine medienumgehung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3c57-116">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="d3c57-117">Ausführliche Informationen zur medienumgehung oder Anrufsteuerung finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) oder [Planning for Call Admission Control in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d3c57-117">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

