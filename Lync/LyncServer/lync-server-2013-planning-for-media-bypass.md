---
title: 'Lync Server 2013: Planung der Medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4bb44-102">Planung der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bb44-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4bb44-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4bb44-104">Medienumgehung bezieht sich auf das Entfernen des Vermittlungsservers aus dem Medienpfad, wenn möglich, für Anrufe, deren Signalisierung den Vermittlungsserver durchquert.</span><span class="sxs-lookup"><span data-stu-id="4bb44-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="4bb44-105">Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="4bb44-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="4bb44-106">Die Skalierbarkeit kann verbessert werden, da durch die Eliminierung der Medienverarbeitung für Umgehungs Anrufe die Belastung des Vermittlungsservers verringert wird.</span><span class="sxs-lookup"><span data-stu-id="4bb44-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="4bb44-107">Diese Verringerung der Auslastung ergänzt die Möglichkeit des Vermittlungsservers, mehrere Gateways zu steuern.</span><span class="sxs-lookup"><span data-stu-id="4bb44-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="4bb44-108">Wenn eine Verzweigungs Website ohne einen Vermittlungs Server über eine oder mehrere WAN-Links mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, senkt die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einer Zweigstelle direkt an sein lokales Gateway fließen können, ohne Zunächst müssen Sie über die WAN-Verbindung zu einem Vermittlungs Server am zentralen Standort und zurückfließen.</span><span class="sxs-lookup"><span data-stu-id="4bb44-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="4bb44-109">Durch die Entlastung des Vermittlungsservers von der Medienverarbeitung kann die medienumgehung auch die Anzahl der Vermittlungsserver verringern, die für eine Enterprise-VoIP-Infrastruktur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4bb44-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="4bb44-110">Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.</span><span class="sxs-lookup"><span data-stu-id="4bb44-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="4bb44-111">**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**</span><span class="sxs-lookup"><span data-stu-id="4bb44-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="4bb44-112">![Voice CAC Media Bypass-Verbindungserzwingung] (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass-Verbindungserzwingung")</span><span class="sxs-lookup"><span data-stu-id="4bb44-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="4bb44-113">Generell gilt, dass die Medienumgehung möglichst immer aktiviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="4bb44-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4bb44-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4bb44-114">In This Section</span></span>

  - [<span data-ttu-id="4bb44-115">Übersicht über die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="4bb44-116">Modi für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="4bb44-117">Medienumgehung und Anrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="4bb44-118">Technische Anforderungen für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="4bb44-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4bb44-119">Related Sections</span></span>

[<span data-ttu-id="4bb44-120">Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bb44-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bb44-121">See Also</span></span>


[<span data-ttu-id="4bb44-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="4bb44-123">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bb44-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

