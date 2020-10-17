---
title: 'Lync Server 2013: Planung der medienumgehung'
description: 'Lync Server 2013: Planung der medienumgehung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549441"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d245a-103">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d245a-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d245a-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d245a-105">Bei der Medienumgehung wird der Vermittlungsserver nach Möglichkeit für Anrufe aus dem Medienpfad entfernt, deren Signaldaten über den Vermittlungsserver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d245a-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="d245a-106">Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="d245a-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="d245a-107">Der Vermittlungsserver muss für Anrufe mit Umgehung keine Mediendatenverarbeitung durchführen, sodass die Vermittlungsserverlast reduziert und die Skalierbarkeit verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="d245a-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="d245a-108">Diese Verringerung der Auslastung ergänzt die Fähigkeit des Vermittlungsserver, mehrere Gateways zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d245a-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="d245a-109">Wenn ein Zweigstellenstandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Zweigstellenstandort direkt an das lokale Gateway übermittelt werden, ohne zuerst über die WAN-Verbindung zu einer Vermittlungsserver am zentralen Standort und zurück weiterzulaufen.</span><span class="sxs-lookup"><span data-stu-id="d245a-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="d245a-110">Durch die Entlastung der Vermittlungsserver von der Medienverarbeitung kann die medienumgehung auch die Anzahl von Vermittlungsservern verringern, die eine Enterprise-VoIP-Infrastruktur benötigt.</span><span class="sxs-lookup"><span data-stu-id="d245a-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="d245a-111">Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.</span><span class="sxs-lookup"><span data-stu-id="d245a-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="d245a-112">**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**</span><span class="sxs-lookup"><span data-stu-id="d245a-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="d245a-113">![VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung")</span><span class="sxs-lookup"><span data-stu-id="d245a-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="d245a-114">Allgemein gilt, dass die Medienumgehung wenn möglich aktiviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d245a-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d245a-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d245a-115">In This Section</span></span>

  - [<span data-ttu-id="d245a-116">Übersicht über die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="d245a-117">Medien Umgehungs Modi in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="d245a-118">Medienumgehung und Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="d245a-119">Technische Anforderungen für die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d245a-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d245a-120">Related Sections</span></span>

[<span data-ttu-id="d245a-121">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d245a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d245a-122">See Also</span></span>


[<span data-ttu-id="d245a-123">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="d245a-124">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d245a-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

