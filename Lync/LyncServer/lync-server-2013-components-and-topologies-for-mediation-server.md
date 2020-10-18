---
title: 'Lync Server 2013: Komponenten und Topologien für Vermittlungsserver'
description: 'Lync Server 2013: Komponenten und Topologien für Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: befd244508db9c98d565a76301e150da98708522
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576851"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="13c4b-103">Komponenten und Topologien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c4b-103">Components and topologies for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c4b-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="13c4b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="13c4b-105">In diesem Thema werden die Komponenten beschrieben, von denen die Vermittlungsserver abhängig ist, und die Topologien, in denen der Vermittlungsserver bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="13c4b-105">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="13c4b-106">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="13c4b-106">Dependencies</span></span>

<span data-ttu-id="13c4b-107">Die Vermittlungsserver hat die folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="13c4b-107">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="13c4b-108">**Registrierungsstelle.**</span><span class="sxs-lookup"><span data-stu-id="13c4b-108">**Registrar.**</span></span> <span data-ttu-id="13c4b-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13c4b-109">Required.</span></span> <span data-ttu-id="13c4b-110">Die Registrierungsstelle ist der nächste Hop für die Signalisierung im Vermittlungsserver Interaktionen mit dem lync Server 2013 Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="13c4b-110">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="13c4b-111">Beachten Sie, dass Vermittlungsserver auf einem Front-End-Server zusammen mit der Registrierungsstelle zusammengestellt werden können und nicht nur in einem eigenständigen Pool installiert sind, der nur aus Vermittlungsservern besteht.</span><span class="sxs-lookup"><span data-stu-id="13c4b-111">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="13c4b-112">Die Registrierungsstelle wird mit einem Vermittlungsserver und einem PSTN-Gateway auf einem Survivable Branch Appliance zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="13c4b-112">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="13c4b-113">**Monitoring Server.**</span><span class="sxs-lookup"><span data-stu-id="13c4b-113">**Monitoring Server.**</span></span> <span data-ttu-id="13c4b-114">Optional, wird jedoch dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="13c4b-114">Optional but highly recommended.</span></span> <span data-ttu-id="13c4b-115">Mit dem Monitoring Server kann der Vermittlungsserver Qualitäts Metriken aufzeichnen, die seinen Mediensitzungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="13c4b-115">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="13c4b-116">**Edgeserver.**</span><span class="sxs-lookup"><span data-stu-id="13c4b-116">**Edge Server.**</span></span> <span data-ttu-id="13c4b-117">Für die Unterstützung externer Benutzer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13c4b-117">Required for external user support.</span></span> <span data-ttu-id="13c4b-118">Die Edgeserver ermöglicht es dem Vermittlungsserver, mit Benutzern zu interagieren, die sich hinter einer NAT oder Firewall befinden.</span><span class="sxs-lookup"><span data-stu-id="13c4b-118">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="13c4b-119">Topologien</span><span class="sxs-lookup"><span data-stu-id="13c4b-119">Topologies</span></span>

<span data-ttu-id="13c4b-120">Die lync Server 2013, Vermittlungsserver ist standardmäßig mit einer Instanz der Registrierungsstelle auf einem Standard Edition-Server, einem Front-End-Pool oder Survivable Branch Appliance verbunden.</span><span class="sxs-lookup"><span data-stu-id="13c4b-120">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="13c4b-121">Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="13c4b-121">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="13c4b-122">Wenn es sich bei der Leistung um ein Problem handelt, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="13c4b-122">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="13c4b-123">Wenn Sie SIP-Trunking bereitstellen, wird empfohlen, einen eigenständigen Vermittlungsserver Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="13c4b-123">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="13c4b-124">Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13c4b-124">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="13c4b-125">Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.</span><span class="sxs-lookup"><span data-stu-id="13c4b-125">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="13c4b-126">Die Verbindung des Vermittlungsservers mit einem Front-End-Pool wird auch empfohlen, wenn Sie IP-Nebenstellenanlagen oder einen von einem Internettelefoniedienstanbieter bereitgestellten SBC (Session Border Controller) verwenden, sofern eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="13c4b-126">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="13c4b-127">Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="13c4b-127">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="13c4b-128">Die IP-Nebenstellenanlage unterstützt keine medienumgehung, aber die Front-End-Pool, die die Vermittlungsserver hostet, kann die Sprachübertragung für Anrufe verarbeiten, für die die medienumgehung nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="13c4b-128">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="13c4b-129">Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="13c4b-129">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="13c4b-130">Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="13c4b-130">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="13c4b-131">Ausführliche Informationen zur bereitzustellenden Topologie finden Sie unter [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-131">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="13c4b-132">Die folgende Abbildung zeigt eine einfache Topologie aus zwei Standorten, die über eine WAN-Verbindung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="13c4b-132">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="13c4b-133">Vermittlungsserver wird mit der Registrierungsstelle auf einem Front-End-Pool an Standort 1 zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="13c4b-133">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="13c4b-134">Die Vermittlungsserver an Standort 1 Steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2.</span><span class="sxs-lookup"><span data-stu-id="13c4b-134">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="13c4b-135">In dieser Topologie ist die medienumgehung Global für die Verwendung von Standort-und Regionsinformationen aktiviert, und für die Trunks zu jedem PSTN-Gateway (GW1 und GW2) ist die Umgehung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13c4b-135">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="13c4b-136">**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**</span><span class="sxs-lookup"><span data-stu-id="13c4b-136">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="13c4b-137">![VoIP-Topologie mit Vermittlungsserver WAN-Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "VoIP-Topologie mit Vermittlungsserver WAN-Gateway")</span><span class="sxs-lookup"><span data-stu-id="13c4b-137">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="13c4b-138">Die folgende Abbildung zeigt eine einfache Topologie, in der der Vermittlungsserver mit der Registrierungsstelle auf Front-End-Pool an Standort 1 zusammenhängt und über eine direkte SIP-Verbindung mit der IP-Nebenstellenanlage an Standort 1 verfügt.</span><span class="sxs-lookup"><span data-stu-id="13c4b-138">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="13c4b-139">In dieser Abbildung steuert der Vermittlungsserver auch ein PSTN-Gateway an Standort 2.</span><span class="sxs-lookup"><span data-stu-id="13c4b-139">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="13c4b-140">Es wird davon ausgegangen, dass lync-Benutzer an beiden Standorten 1 und 2 vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="13c4b-140">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="13c4b-141">Nehmen Sie außerdem an, dass die IP-Nebenstellenanlage über einen zugeordneten medienprozessor verfügt, der von allen Medien aus lync-Endpunkten durchlaufen werden muss, bevor Sie an Medien Endpunkte gesendet werden, die von der IP-Nebenstellenanlage gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="13c4b-141">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="13c4b-142">In dieser Topologie ist die medienumgehung Global für die Verwendung von Standort-und Regionsinformationen aktiviert, und für die Trunks für die Nebenstellenanlage und das PSTN-Gateway ist die medienumgehung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13c4b-142">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="13c4b-143">**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**</span><span class="sxs-lookup"><span data-stu-id="13c4b-143">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="13c4b-144">![VoIP-Topologie Vermittlungsserver WAN-Nebenstellenanlage](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "VoIP-Topologie Vermittlungsserver WAN-Nebenstellenanlage")</span><span class="sxs-lookup"><span data-stu-id="13c4b-144">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="13c4b-145">Ausführliche Informationen zur Planung von PBX-Topologien finden Sie unter [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) und [direkte SIP-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-145">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="13c4b-146">Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der die Vermittlungsserver mit dem SBC eines Internet Telefonie-Dienstanbieters verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="13c4b-146">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="13c4b-147">Ausführliche Informationen zu SIP-Trunk Topologien finden Sie unter [SIP-Trunking in lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-147">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

