---
title: 'Lync Server 2013: Planung der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5729989334297d4a6b368808079b0a7b0f4cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6d6fc-102">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d6fc-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6d6fc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6d6fc-104">Für UC-Anwendungen (Unified Communications), die IP-basiert sind, wie Telefonie, Video und Anwendungsfreigabe, wird die verfügbare Bandbreite von Unternehmensnetzwerken im Allgemeinen nicht als limitierender Faktor in LAN-Umgebungen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="6d6fc-105">Bei WAN-Verbindungen, die Standorte miteinander verbinden, kann die Netzwerkbandbreite jedoch eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="6d6fc-106">Wenn ein Zustrom von Netzwerkdatenverkehr eine WAN-Verbindung überzeichnet, werden aktuelle Mechanismen wie Warteschlangen, Pufferung und das Herunterfahren von Paketen verwendet, um die Überlastung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="6d6fc-107">Der zusätzliche Datenverkehr wird in der Regel verzögert, bis die Überlastung des Netzwerks oder, falls erforderlich, der Datenverkehr gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="6d6fc-108">Für konventionellen Datenverkehr in solchen Situationen kann der empfangende Client wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="6d6fc-109">Für echtzeitdatenverkehr wie Unified Communications kann die Netzwerküberlastung auf diese Weise nicht aufgelöst werden, da der Unified Communications-Datenverkehr sowohl auf Wartezeit als auch auf Paketverlust reagiert.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="6d6fc-110">Überlastung im WAN kann zu einer schlechten Qualität der Benutzerfreundlichkeit (QoE) führen.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="6d6fc-111">Für den echtzeitdatenverkehr in überlasteten Bedingungen ist es besser, Anrufe zu verweigern, als Verbindungen mit schlechter Qualität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="6d6fc-112">Anrufsteuerung (Call Admission Control, CAC) bestimmt, ob genügend Netzwerkbandbreite vorhanden ist, um eine Echtzeitsitzung mit akzeptabler Qualität einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="6d6fc-113">In lync Server 2013 steuert die Anrufsteuerung den echtzeitdatenverkehr nur für Audio und Video, wirkt sich jedoch nicht auf den Datenverkehr aus.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="6d6fc-114">Wenn der standardmäßige WAN-Pfad nicht über die erforderliche Bandbreite verfügt, kann CAC versuchen, den Anruf über einen Internet Pfad oder das Telefon Festnetz (Public Switched Telephone Network, PSTN) weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6d6fc-115">Die Anrufsteuerung ist nur in lync Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="6d6fc-116">In diesem Abschnitt wird die Funktion zur Anrufsteuerung beschrieben und erläutert, wie die Anrufsteuerung geplant wird.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d6fc-117">Lync Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="6d6fc-118">Eine Übersicht über die Planungsinformationen, die für alle drei dieser Features verwendet werden, finden Sie unter <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6d6fc-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d6fc-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6d6fc-119">In This Section</span></span>

  - [<span data-ttu-id="6d6fc-120">Übersicht über die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="6d6fc-121">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="6d6fc-122">Beispiel: Sammeln der Anforderungen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="6d6fc-123">Komponenten und Topologien für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="6d6fc-124">Bewährte Methoden für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="6d6fc-125">Prüfliste für die Bereitstellung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d6fc-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

