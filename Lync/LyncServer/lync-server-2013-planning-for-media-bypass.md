---
title: 'Lync Server 2013: Planung der medienumgehung'
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
ms.openlocfilehash: b5d9687069e82cde803f7a01873db482ea2afa2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521992"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="f745e-102">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-102">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f745e-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f745e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f745e-104">Bei der Medienumgehung wird der Vermittlungsserver nach Möglichkeit für Anrufe aus dem Medienpfad entfernt, deren Signaldaten über den Vermittlungsserver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f745e-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="f745e-105">Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="f745e-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="f745e-106">Der Vermittlungsserver muss für Anrufe mit Umgehung keine Mediendatenverarbeitung durchführen, sodass die Vermittlungsserverlast reduziert und die Skalierbarkeit verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="f745e-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="f745e-107">Diese Verringerung der Auslastung ergänzt die Fähigkeit des Vermittlungsserver, mehrere Gateways zu steuern.</span><span class="sxs-lookup"><span data-stu-id="f745e-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="f745e-108">Wenn ein Zweigstellenstandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Zweigstellenstandort direkt an das lokale Gateway übermittelt werden, ohne zuerst über die WAN-Verbindung zu einer Vermittlungsserver am zentralen Standort und zurück weiterzulaufen.</span><span class="sxs-lookup"><span data-stu-id="f745e-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="f745e-109">Durch die Entlastung der Vermittlungsserver von der Medienverarbeitung kann die medienumgehung auch die Anzahl von Vermittlungsservern verringern, die eine Enterprise-VoIP-Infrastruktur benötigt.</span><span class="sxs-lookup"><span data-stu-id="f745e-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="f745e-110">Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.</span><span class="sxs-lookup"><span data-stu-id="f745e-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="f745e-111">**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**</span><span class="sxs-lookup"><span data-stu-id="f745e-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="f745e-112">![VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung")</span><span class="sxs-lookup"><span data-stu-id="f745e-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="f745e-113">Allgemein gilt, dass die Medienumgehung wenn möglich aktiviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="f745e-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f745e-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f745e-114">In This Section</span></span>

  - [<span data-ttu-id="f745e-115">Übersicht über die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="f745e-116">Medien Umgehungs Modi in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="f745e-117">Medienumgehung und Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="f745e-118">Technische Anforderungen für die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f745e-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f745e-119">Related Sections</span></span>

[<span data-ttu-id="f745e-120">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f745e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f745e-121">See Also</span></span>


[<span data-ttu-id="f745e-122">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="f745e-123">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f745e-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

