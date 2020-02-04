---
title: 'Lync Server 2013: Vermittlungsserver Komponente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="a14ef-102">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a14ef-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a14ef-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a14ef-104">Sie müssen lync Server 2013, Mediation Server bereitstellen, wenn Sie die Enterprise-VoIP-Arbeitsauslastung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a14ef-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="a14ef-105">In diesem Abschnitt werden grundlegende Funktionen, Abhängigkeiten, grundlegende Topologien und Planungsrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a14ef-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="a14ef-106">Der Vermittlungs Server übersetzt Signalisierungen und in einigen Konfigurationen Medien zwischen dem internen lync Server 2013, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Stamm (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="a14ef-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="a14ef-107">Auf der lync Server 2013-Seite lauscht Mediation Server an einer einzelnen MTLS-Transportadresse (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="a14ef-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="a14ef-108">Auf der Gatewayseite überwacht der Mediation Server alle zugehörigen Abhör-Ports, die mit Trunks verknüpft sind, die im Topologie-Dokument definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a14ef-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="a14ef-109">Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden.</span><span class="sxs-lookup"><span data-stu-id="a14ef-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="a14ef-110">TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.</span><span class="sxs-lookup"><span data-stu-id="a14ef-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="a14ef-111">Wenn Sie auch über eine vorhandene öffentliche Branch Exchange (PBX) in Ihrer Umgebung verfügen, verarbeitet der Vermittlungs Server Anrufe zwischen Enterprise-VoIP-Benutzern und der Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="a14ef-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="a14ef-112">Wenn es sich bei Ihrer Telefonanlage um eine IP-Telefonanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Telefonanlage und dem Vermittlungs Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="a14ef-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="a14ef-113">Wenn es sich bei Ihrer Telefonanlage um eine TDM-Telefonanlage (Time Division Multiplex) handelt, müssen Sie auch ein PSTN-Gateway zwischen dem Vermittlungs Server und der Telefonanlage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a14ef-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="a14ef-114">Der Vermittlungsserver befindet sich standardmäßig mit dem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="a14ef-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="a14ef-115">Der Vermittlungs Server kann auch aus Leistungsgründen in einem eigenständigen Pool bereitgestellt werden, oder wenn Sie SIP-Trunking bereitstellen, wird in diesem Fall der eigenständige Pool dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a14ef-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="a14ef-116">Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway bereitstellen, das medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a14ef-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="a14ef-117">Ein eigenständiger Vermittlungs Server Pool ist nicht erforderlich, da qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.</span><span class="sxs-lookup"><span data-stu-id="a14ef-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="a14ef-118">Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="a14ef-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="a14ef-119">Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="a14ef-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="a14ef-120">Die IP-PBX unterstützt keine medienumgehung, aber der Front-End-Pool, der den Vermittlungs Server hostet, kann die Sprachübertragung für Anrufe in die medienumgehung anwenden.</span><span class="sxs-lookup"><span data-stu-id="a14ef-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="a14ef-121">Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a14ef-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="a14ef-122">Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a14ef-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a14ef-123">Die wichtigsten Funktionen des Vermittlungsservers lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a14ef-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="a14ef-124">Verschlüsseln und Entschlüsseln von SRTP auf der lync Server-Seite</span><span class="sxs-lookup"><span data-stu-id="a14ef-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="a14ef-125">Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) für SIP über Mutual TLS</span><span class="sxs-lookup"><span data-stu-id="a14ef-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="a14ef-126">Übersetzen von Mediendatenströmen zwischen lync Server und dem Gateway-Peer des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="a14ef-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="a14ef-127">Verbinden von Clients außerhalb des Netzwerks mit internen ICE-Komponenten, die den Medien Durchlauf von NAT und Firewalls ermöglichen</span><span class="sxs-lookup"><span data-stu-id="a14ef-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="a14ef-128">Als Vermittler für Anruf Flüsse fungieren, die von einem Gateway nicht unterstützt werden, beispielsweise Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Client</span><span class="sxs-lookup"><span data-stu-id="a14ef-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="a14ef-129">In Bereitstellungen, die SIP-Trunking umfassen, arbeiten mit dem SIP-Trunking-Dienstanbieter, um PSTN-Unterstützung bereitzustellen, wodurch kein PSTN-Gateway erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="a14ef-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="a14ef-130">Die folgende Abbildung zeigt die Signalisierungs-und Medienprotokolle, die vom Vermittlungs Server bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a14ef-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="a14ef-131">**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**</span><span class="sxs-lookup"><span data-stu-id="a14ef-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="a14ef-132">![Vermittlungsserverprotokolle (Diagramm)](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Vermittlungsserverprotokolle (Diagramm)")</span><span class="sxs-lookup"><span data-stu-id="a14ef-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a14ef-133">Wenn Sie im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungs Server TCP-oder RTP-RTCP (statt SRTP oder SRTCP) verwenden, empfiehlt es sich, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a14ef-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a14ef-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a14ef-134">In This Section</span></span>

  - [<span data-ttu-id="a14ef-135">M:N trunk in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="a14ef-136">Anrufsteuerung und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="a14ef-137">9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="a14ef-138">Medienumgehung und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="a14ef-139">Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="a14ef-140">Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14ef-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

