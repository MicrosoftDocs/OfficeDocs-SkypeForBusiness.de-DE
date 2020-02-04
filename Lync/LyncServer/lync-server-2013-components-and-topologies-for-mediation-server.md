---
title: 'Lync Server 2013: Komponenten und Topologien für den Vermittlungsserver'
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
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="b4443-102">Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4443-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4443-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b4443-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b4443-104">In diesem Thema werden die Komponenten beschrieben, auf denen der Vermittlungsserver abhängig ist, und die Topologien, in denen der Vermittlungsserver bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4443-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="b4443-105">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b4443-105">Dependencies</span></span>

<span data-ttu-id="b4443-106">Der Vermittlungs Server weist die folgenden Abhängigkeiten auf:</span><span class="sxs-lookup"><span data-stu-id="b4443-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="b4443-107">**Registrierungsstelle.**</span><span class="sxs-lookup"><span data-stu-id="b4443-107">**Registrar.**</span></span> <span data-ttu-id="b4443-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4443-108">Required.</span></span> <span data-ttu-id="b4443-109">Die Registrierungsstelle ist der nächste Hop zur Signalgebung in den Vermittlungsserver Interaktionen mit dem lync Server 2013-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="b4443-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="b4443-110">Beachten Sie, dass der Vermittlungsserver zusammen mit der Registrierungsstelle auf einem Front-End-Server zusammengestellt werden kann, und zwar nicht nur in einem eigenständigen Pool, bestehend aus Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="b4443-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="b4443-111">Die Registrierungsstelle ist mit einem Vermittlungs Server und einem PSTN-Gateway auf einer Survivable Branch-Appliance in Kontakt.</span><span class="sxs-lookup"><span data-stu-id="b4443-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="b4443-112">**Monitoring Server.**</span><span class="sxs-lookup"><span data-stu-id="b4443-112">**Monitoring Server.**</span></span> <span data-ttu-id="b4443-113">Optional, aber sehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="b4443-113">Optional but highly recommended.</span></span> <span data-ttu-id="b4443-114">Der Überwachungsserver ermöglicht es dem Vermittlungsserver, Qualitäts Metriken aufzuzeichnen, die seinen Mediensitzungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b4443-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="b4443-115">**Edgeserver.**</span><span class="sxs-lookup"><span data-stu-id="b4443-115">**Edge Server.**</span></span> <span data-ttu-id="b4443-116">Für die Unterstützung externer Benutzer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4443-116">Required for external user support.</span></span> <span data-ttu-id="b4443-117">Der Edgeserver ermöglicht es dem Vermittlungsserver, mit Benutzern zu interagieren, die sich hinter einem NAT oder einer Firewall befinden.</span><span class="sxs-lookup"><span data-stu-id="b4443-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="b4443-118">Topologien verfügen</span><span class="sxs-lookup"><span data-stu-id="b4443-118">Topologies</span></span>

<span data-ttu-id="b4443-119">Der lync Server 2013, Mediation Server ist standardmäßig mit einer Instanz der Registrierungsstelle auf einem Standard Edition-Server, einem Front-End-Pool oder einer Survivable Branch-Appliance ausgestattet.</span><span class="sxs-lookup"><span data-stu-id="b4443-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="b4443-120">Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="b4443-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="b4443-121">Wenn die Leistung ein Problem ist, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4443-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="b4443-122">Wenn Sie SIP-Trunking bereitstellen, empfehlen wir, einen eigenständigen Vermittlungs Server Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4443-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b4443-123">Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway bereitstellen, das medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4443-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="b4443-124">Ein eigenständiger Vermittlungs Server Pool ist nicht erforderlich, da qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.</span><span class="sxs-lookup"><span data-stu-id="b4443-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="b4443-125">Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="b4443-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="b4443-126">Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b4443-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="b4443-127">Die IP-PBX unterstützt keine medienumgehung, aber der Front-End-Pool, der den Vermittlungs Server hostet, kann die Sprachübertragung für Anrufe in die medienumgehung anwenden.</span><span class="sxs-lookup"><span data-stu-id="b4443-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="b4443-128">Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b4443-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="b4443-129">Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b4443-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b4443-130">Details zur bereitzustellenden Topologie finden Sie unter [Bereitstellungsrichtlinien für Mediation Server in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4443-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="b4443-131">Die folgende Abbildung zeigt eine einfache Topologie, bestehend aus zwei Websites, die über eine WAN-Verbindung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b4443-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="b4443-132">Der Vermittlungs Server ist mit der Registrierungsstelle an einem Front-End-Pool an Standort 1 zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b4443-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="b4443-133">Die Vermittlungsserver an Standort 1 Steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2.</span><span class="sxs-lookup"><span data-stu-id="b4443-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="b4443-134">In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks für jedes PSTN-Gateway (GW1 und GW2) ist die Umgehungsfunktion aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b4443-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="b4443-135">**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**</span><span class="sxs-lookup"><span data-stu-id="b4443-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="b4443-136">![Sprach Topologie mit dem Vermittlungs Server-WAN-Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Sprach Topologie mit dem Vermittlungs Server-WAN-Gateway")</span><span class="sxs-lookup"><span data-stu-id="b4443-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="b4443-137">Die nächste Abbildung zeigt eine einfache Topologie, in der der Vermittlungs Server mit der Registrierungsstelle im Front-End-Pool von Standort 1 zusammengeführt wird und über eine direkte SIP-Verbindung mit der IP-PBX-Anlage an Standort 1 verfügt.</span><span class="sxs-lookup"><span data-stu-id="b4443-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="b4443-138">In dieser Abbildung steuert der Vermittlungs Server auch ein PSTN-Gateway an Standort 2.</span><span class="sxs-lookup"><span data-stu-id="b4443-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="b4443-139">Angenommen, lync-Benutzer sind an beiden Standorten 1 und 2 vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b4443-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="b4443-140">Gehen Sie auch davon aus, dass die IP-PBX über einen zugeordneten medienprozessor verfügt, der von allen Medien, die von lync-Endpunkten stammen, durchlaufen werden muss, bevor Sie an Medien Endpunkte gesendet werden, die von der IP-Telefonanlage gesteuert</span><span class="sxs-lookup"><span data-stu-id="b4443-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="b4443-141">In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks an die Telefonanlage und das PSTN-Gateway ist die medienumgehung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b4443-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="b4443-142">**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**</span><span class="sxs-lookup"><span data-stu-id="b4443-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="b4443-143">![Vermittlungs Server für sprach Topologie-WAN-PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Vermittlungs Server für sprach Topologie-WAN-PBX")</span><span class="sxs-lookup"><span data-stu-id="b4443-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="b4443-144">Ausführliche Informationen zur Planung von PBX-Topologien finden Sie unter [Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) und [direkte SIP-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="b4443-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="b4443-145">Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungs Server mit dem SBC eines Internet Telefonie-Dienstanbieters verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b4443-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b4443-146">Details zu den SIP-Trunk Topologien finden Sie unter [SIP-Trunking in lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="b4443-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

