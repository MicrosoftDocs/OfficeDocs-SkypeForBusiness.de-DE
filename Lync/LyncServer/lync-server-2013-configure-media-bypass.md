---
title: 'Lync Server 2013: Konfigurieren der Medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465a949ca1581933f96f18cfe2977d400fa7a152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4d6f4-102">Konfigurieren der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d6f4-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d6f4-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4d6f4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4d6f4-104">In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver veröffentlicht und konfiguriert haben (wie unter [Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) beschrieben und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)oder in [Definieren und konfigurieren Sie einen Front-End-Pool oder Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) , und [veröffentlichen Sie die Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md), jeweils in der Bereitstellungsdokumentation).</span><span class="sxs-lookup"><span data-stu-id="4d6f4-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="4d6f4-105">In diesem Abschnitt wird auch davon ausgegangen, dass Sie mindestens einen Gateway-Peer für die Bereitstellung von PSTN-Konnektivität definiert haben, wie unter [Definieren eines Gateways im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="4d6f4-106">Wenn es sich bei dem Peer, mit dem Sie sich verbinden, um den SBC eines SIP-Trunkinganbieters handelt, sollten Sie sich vergewissern, dass dieser ein qualifizierter Anbieter ist und die Medienumgehung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="4d6f4-107">Viele SIP-Trunkinganbieter lassen für den SBC nur den Empfang von Datenverkehr vom Vermittlungsserver zu.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="4d6f4-108">In diesem Fall darf die Medienumgehung für den betreffenden Trunk nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="4d6f4-109">Darüber hinaus können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation dem SIP-Trunkinganbieter ihre internen Netzwerk-IP-Adressen offenlegt.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d6f4-110">Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="4d6f4-111">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="4d6f4-112">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>lync Server unter aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="4d6f4-113">In diesem Abschnitt wird beschrieben, wie Sie die medienumgehung aktivieren, um die für den Vermittlungs Server erforderliche Verarbeitung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="4d6f4-114">Bevor Sie die medienumgehung aktivieren, müssen Sie sicherstellen, dass Ihre Umgebung die für die Unterstützung der medienumgehung erforderlichen Bedingungen erfüllt, wie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planning-Dokumentation beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="4d6f4-115">Stellen Sie außerdem sicher, dass Sie die Informationen unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) verwendet haben, um zu entscheiden, ob die globalen Einstellungen für die medienumgehung aktiviert werden sollen, um den Vermittlungs Server immer zu umgehen oder um Website-und Regionsinformationen zu verwenden, um festzustellen, ob umgehen Sie den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="4d6f4-p104">Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) – eine andere erweiterte Enterprise-VoIP-Funktion – bereits optional konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung der Anrufsteuerung nicht für Anrufe gilt, für welche die Medienumgehung aktiviert ist. Bei einem Anruf wird zuerst überprüft, ob die Medienumgehung angewendet werden soll. Wenn dies der Fall ist, wird die Anrufsteuerung nicht angewendet. Nur wenn die Medienumgehung nicht aktiviert ist, wird geprüft, ob die Anrufsteuerung angewendet werden soll. Diese beiden Funktionen schließen sich für alle Anrufe, die an das PSTN weitergeleitet werden, gegenseitig aus. Dies ist ein logisches Verhalten, denn die Medienumgehung setzt voraus, dass bei einem Anruf keine Bandbreitenbeschränkungen zwischen den Medienendpunkten vorhanden sind. In Verbindungen mit eingeschränkter Bandbreite kann keine Medienumgehung stattfinden. Demzufolge trifft auf einen PSTN-Anruf nur eine der beiden folgenden Verhaltensweisen zu: a) die Medien umgehen den Vermittlungsserver und die Anrufsteuerung reserviert keine Bandbreite für den Anruf oder b) die Anrufsteuerung reserviert Bandbreite für den Anruf und die Medien werden vom betroffenen Vermittlungsserver verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4d6f4-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="4d6f4-121">Nächste Schritte: Aktivieren der medienumgehung für die trunk-Verbindung</span><span class="sxs-lookup"><span data-stu-id="4d6f4-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="4d6f4-122">Nachdem Sie die anfänglichen Einstellungen für PSTN-Konnektivität (Wählpläne, VoIP-Richtlinien, PSTN-Verwendungsdaten Sätze, ausgehende Anrufrouten und Übersetzungsregeln) konfiguriert haben, beginnen Sie mit dem Verfahren zum Aktivieren der medienumgehung mithilfe der Schritte unter [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4d6f4-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d6f4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d6f4-123">See Also</span></span>


[<span data-ttu-id="4d6f4-124">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d6f4-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="4d6f4-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="4d6f4-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="4d6f4-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="4d6f4-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="4d6f4-127">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d6f4-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="4d6f4-128">Planung der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d6f4-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

