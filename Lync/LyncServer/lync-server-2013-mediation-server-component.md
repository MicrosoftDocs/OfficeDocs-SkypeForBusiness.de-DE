---
title: 'Lync Server 2013: Vermittlungsserver-Komponente'
description: 'Lync Server 2013: Vermittlungsserver-Komponente.'
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
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568641"
---
# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="05da5-103">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-103">Mediation Server component in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05da5-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="05da5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="05da5-105">Sie müssen lync Server 2013 bereitstellen, Vermittlungsserver, wenn Sie die Enterprise-VoIP-Arbeitsauslastung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="05da5-105">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="05da5-106">In diesem Abschnitt werden die grundlegende Funktionalität, Abhängigkeiten, grundlegende Topologien sowie Richtlinien für die Planung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05da5-106">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="05da5-107">Das Vermittlungsserver übersetzt das signalisieren und in einigen Konfigurationen Medien zwischen dem internen lync Server 2013, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Trunk (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="05da5-107">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="05da5-108">Auf der lync Server 2013 Seite überwacht Vermittlungsserver eine einzelne MTLS-Transportadresse (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="05da5-108">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="05da5-109">Aufseiten des Gateways überwacht der Vermittlungsserver alle zugehörigen Überwachungsports für die Trunks, die im Topologiedokument definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05da5-109">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="05da5-110">Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden.</span><span class="sxs-lookup"><span data-stu-id="05da5-110">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="05da5-111">TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.</span><span class="sxs-lookup"><span data-stu-id="05da5-111">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="05da5-112">Wenn in Ihrer Umgebung auch eine Nebenstellenanlage vorhanden ist, verarbeitet Vermittlungsserver Anrufe zwischen Enterprise-VoIP-Benutzern und der Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="05da5-112">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="05da5-113">Wenn es sich bei Ihrer Nebenstellenanlage um eine IP-Nebenstellenanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und der Vermittlungsserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="05da5-113">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="05da5-114">Wenn es sich bei Ihrer Nebenstellenanlage um eine TDM-Nebenstellenanlage (Time Division Multiplex) handelt, müssen Sie auch ein PSTN-Gateway zwischen Vermittlungsserver und der Nebenstellenanlage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="05da5-114">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="05da5-115">Das Vermittlungsserver wird standardmäßig mit dem Front-End-Server zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="05da5-115">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="05da5-116">Das Vermittlungsserver kann auch aus Leistungsgründen in einem eigenständigen Pool bereitgestellt werden, oder wenn Sie das SIP-Trunking bereitstellen, wird der eigenständige Pool in diesem Fall dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="05da5-116">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="05da5-117">Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05da5-117">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="05da5-118">Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.</span><span class="sxs-lookup"><span data-stu-id="05da5-118">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="05da5-119">Die Verbindung des Vermittlungsservers mit einem Front-End-Pool wird auch empfohlen, wenn Sie IP-Nebenstellenanlagen oder einen von einem Internettelefoniedienstanbieter bereitgestellten SBC (Session Border Controller) verwenden, sofern eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="05da5-119">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="05da5-120">Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="05da5-120">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="05da5-121">Die IP-Nebenstellenanlage unterstützt keine medienumgehung, aber die Front-End-Pool, die die Vermittlungsserver hostet, kann die Sprachübertragung für Anrufe verarbeiten, für die die medienumgehung nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="05da5-121">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="05da5-122">Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="05da5-122">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="05da5-123">Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="05da5-123">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="05da5-124">Die Hauptfunktionen des Vermittlungsserver lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="05da5-124">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="05da5-125">Verschlüsseln und Entschlüsseln von SRTP auf der lync Server Seite</span><span class="sxs-lookup"><span data-stu-id="05da5-125">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="05da5-126">Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über Mutual TLS</span><span class="sxs-lookup"><span data-stu-id="05da5-126">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="05da5-127">Übersetzen von Mediendatenströmen zwischen lync Server und dem Gateway-Peer des Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="05da5-127">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="05da5-128">Herstellen von Verbindungen zwischen Clients außerhalb des Netzwerks und internen ICE-Komponenten, damit Medien NAT und Firewalls passieren können</span><span class="sxs-lookup"><span data-stu-id="05da5-128">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="05da5-129">Fungieren als Vermittler für Anruf Flüsse, die von einem Gateway nicht unterstützt werden, beispielsweise Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Client</span><span class="sxs-lookup"><span data-stu-id="05da5-129">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="05da5-130">Verwenden des SIP-Trunking-Dienstanbieters für das Telefonfestnetz, sodass kein PSTN-Gateway erforderlich ist (gilt für Bereitstellungen mit SIP-Trunking)</span><span class="sxs-lookup"><span data-stu-id="05da5-130">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="05da5-131">In der folgenden Abbildung sind die Signalisierungs-und Medienprotokolle dargestellt, die vom Vermittlungsserver bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05da5-131">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="05da5-132">**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**</span><span class="sxs-lookup"><span data-stu-id="05da5-132">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="05da5-133">![Diagramm für Vermittlungsserver Protokolle](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramm für Vermittlungsserver Protokolle")</span><span class="sxs-lookup"><span data-stu-id="05da5-133">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05da5-134">Wenn Sie TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungsserver verwenden, wird empfohlen, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="05da5-134">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05da5-135">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="05da5-135">In This Section</span></span>

  - [<span data-ttu-id="05da5-136">M:n-trunk trunk in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-136">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="05da5-137">Anrufsteuerung und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-137">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="05da5-138">Enhanced 9-1-1 (E9-1-1) und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-138">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="05da5-139">Medienumgehung und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-139">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="05da5-140">Komponenten und Topologien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-140">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="05da5-141">Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05da5-141">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

