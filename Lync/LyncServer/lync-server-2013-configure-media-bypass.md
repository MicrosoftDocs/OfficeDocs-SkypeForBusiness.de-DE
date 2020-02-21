---
title: 'Lync Server 2013: Konfigurieren der medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fe9bb93ad32c0871dd51d3818d2ca788327dc5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="afe73-102">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afe73-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afe73-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="afe73-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="afe73-104">In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver veröffentlicht und konfiguriert haben (wie unter [define a Vermittlungsserver in Topology Builder in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)oder in [definieren und Konfigurieren einer Front-End-Pool oder Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)jeweils in der Bereitstellungsdokumentation beschrieben).</span><span class="sxs-lookup"><span data-stu-id="afe73-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="afe73-105">In diesem Abschnitt wird auch davon ausgegangen, dass Sie mindestens einen Gateway-Peer für die Bereitstellung der PSTN-Konnektivität definiert haben, wie unter [define a Gateway in Topology Builder in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afe73-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="afe73-106">Wenn es sich bei dem Peer, mit dem Sie eine Verbindung herstellen, um den SBC eines SIP-Trunking-Anbieters handelt, stellen Sie sicher, dass der Anbieter ein qualifizierter Anbieter ist und dass der Anbieter die medienumgehung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afe73-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="afe73-107">Beispielsweise können viele SIP-Trunking-Anbieter nur deren SBC Datenverkehr vom Vermittlungsserver empfangen.</span><span class="sxs-lookup"><span data-stu-id="afe73-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="afe73-108">Wenn dies der Fall ist, muss Bypass für den betreffenden trunk nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="afe73-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="afe73-109">Außerdem können Sie die medienumgehung nur aktivieren, wenn Ihre Organisation die internen Netzwerk-IP-Adressen dem SIP-Trunking-Anbieter offenbart.</span><span class="sxs-lookup"><span data-stu-id="afe73-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afe73-110">Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren.</span><span class="sxs-lookup"><span data-stu-id="afe73-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="afe73-111">Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="afe73-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="afe73-112">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>– lync Server unter aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="afe73-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="afe73-113">In diesem Abschnitt wird beschrieben, wie Sie die medienumgehung aktivieren, um die für den Vermittlungsserver erforderliche Verarbeitung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="afe73-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="afe73-114">Bevor Sie die medienumgehung aktivieren, müssen Sie sicherstellen, dass Ihre Umgebung die Bedingungen erfüllt, die zur Unterstützung der medienumgehung erforderlich sind, wie in [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afe73-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="afe73-115">Stellen Sie außerdem sicher, dass Sie die Informationen in [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) verwendet haben, um zu entscheiden, ob die globalen Einstellungen für die medienumgehung aktiviert werden sollen, um die Vermittlungsserver zu umgehen oder Standort-und Regionsinformationen zu verwenden, wenn Sie bestimmen, ob die Vermittlungsserver umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="afe73-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="afe73-116">Wenn Sie die Anrufsteuerung (Call Admission Control, CAC), eine andere erweiterte Enterprise-VoIP-Funktion, bereits konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung, die von der Anrufsteuerung durchgeführt wird, nicht für Anrufe gilt, für die die medienumgehung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="afe73-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="afe73-117">Die Überprüfung, ob die medienumgehung verwendet wird, wird zuerst durchgeführt, und wenn die medienumgehung eingesetzt wird, wird die Anrufsteuerung für den Anruf nicht verwendet. nur wenn die Medien Umgehungs Überprüfung fehlschlägt, wird die Überprüfung für die Anrufsteuerung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="afe73-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="afe73-118">Die beiden Features schließen sich somit gegenseitig für einen bestimmten Anruf aus, der an das PSTN weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="afe73-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="afe73-119">Dies ist die Logik, da die medienumgehung davon ausgeht, dass Bandbreiteneinschränkungen zwischen den Medien Endpunkten eines Anrufs nicht vorhanden sind. die medienumgehung kann für Links mit eingeschränkter Bandbreite nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="afe73-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="afe73-120">Als Ergebnis gilt eine der folgenden Optionen für einen PSTN-Anruf: a) Medien umgehen die Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf; oder b) Anrufsteuerung wendet Bandbreiten Reservierungen für den Anruf an, und Medien werden von dem Vermittlungsserver verarbeitet, die an dem Anruf beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="afe73-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="afe73-121">Nächste Schritte: Aktivieren der medienumgehung für die trunk Verbindung</span><span class="sxs-lookup"><span data-stu-id="afe73-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="afe73-122">Nachdem Sie die anfänglichen Einstellungen für die PSTN-Konnektivität (Wählpläne, VoIP-Richtlinien, PSTN-Verwendungsdaten Sätze, ausgehende Anrufrouten und Übersetzungsregeln) konfiguriert haben, beginnen Sie mit der Aktivierung der medienumgehung mithilfe der Schritte unter [Configure a trunk with Media Bypass in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="afe73-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afe73-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afe73-123">See Also</span></span>


[<span data-ttu-id="afe73-124">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afe73-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="afe73-125">Konfigurieren der medienumgehung in lync Server 2013, um die Vermittlungsserver immer zu umgehen</span><span class="sxs-lookup"><span data-stu-id="afe73-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="afe73-126">Konfigurieren der globalen Einstellungen für die medienumgehung in lync Server 2013 zur Verwendung von Standort-und Regionsinformationen</span><span class="sxs-lookup"><span data-stu-id="afe73-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="afe73-127">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afe73-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="afe73-128">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afe73-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

