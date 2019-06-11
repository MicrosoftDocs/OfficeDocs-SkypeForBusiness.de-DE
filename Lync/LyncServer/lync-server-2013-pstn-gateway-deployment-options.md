---
title: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="a3de4-102">Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3de4-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3de4-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a3de4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="a3de4-104">PSTN Gateways</span><span class="sxs-lookup"><span data-stu-id="a3de4-104">PSTN Gateways</span></span>

<span data-ttu-id="a3de4-105">PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen.</span><span class="sxs-lookup"><span data-stu-id="a3de4-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="a3de4-106">In either topology, the gateway terminates the PSTN.</span><span class="sxs-lookup"><span data-stu-id="a3de4-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="a3de4-107">Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="a3de4-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="a3de4-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span><span class="sxs-lookup"><span data-stu-id="a3de4-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="a3de4-109">Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert.</span><span class="sxs-lookup"><span data-stu-id="a3de4-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="a3de4-110">Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig.</span><span class="sxs-lookup"><span data-stu-id="a3de4-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="a3de4-111">Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a3de4-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="a3de4-112">Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a3de4-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="a3de4-113">Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="a3de4-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="a3de4-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span><span class="sxs-lookup"><span data-stu-id="a3de4-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="a3de4-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span><span class="sxs-lookup"><span data-stu-id="a3de4-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="a3de4-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="a3de4-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="a3de4-122"> You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span><span class="sxs-lookup"><span data-stu-id="a3de4-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="a3de4-123">M:N Trunk Support</span><span class="sxs-lookup"><span data-stu-id="a3de4-123">M:N Trunk Support</span></span>

<span data-ttu-id="a3de4-124">Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten.</span><span class="sxs-lookup"><span data-stu-id="a3de4-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="a3de4-125">Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren.</span><span class="sxs-lookup"><span data-stu-id="a3de4-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="a3de4-126">Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als *trunk*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a3de4-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="a3de4-127">Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a3de4-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="a3de4-128">Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.</span><span class="sxs-lookup"><span data-stu-id="a3de4-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="a3de4-129">Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [M:N trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="a3de4-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="a3de4-130">Details zu weiteren Verbesserungen des ausgehenden Routings finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="a3de4-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="a3de4-131">Gateway Topologies</span><span class="sxs-lookup"><span data-stu-id="a3de4-131">Gateway Topologies</span></span>

<span data-ttu-id="a3de4-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span><span class="sxs-lookup"><span data-stu-id="a3de4-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="a3de4-133">Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a3de4-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="a3de4-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span><span class="sxs-lookup"><span data-stu-id="a3de4-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="a3de4-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span><span class="sxs-lookup"><span data-stu-id="a3de4-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="a3de4-136">Die resultierende verteilte Gateway-Topologie wird in der folgenden Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3de4-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="a3de4-137">**Topologie des verteilten Gateways**</span><span class="sxs-lookup"><span data-stu-id="a3de4-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="a3de4-138">![Topologie-Diagramm für verteilte Gateways] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")</span><span class="sxs-lookup"><span data-stu-id="a3de4-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="a3de4-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="a3de4-142">Um dieses Problem zu beheben, bevorzugen viele große Unternehmen, wie in der nachstehenden Abbildung zu sehen, ein oder einige wenige große Telefonie-Zentrale Standorte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3de4-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="a3de4-143">**Topologie des zentralen Telefonie-Standorts**</span><span class="sxs-lookup"><span data-stu-id="a3de4-143">**Telephony central site topology**</span></span>

<span data-ttu-id="a3de4-144">![Datencenter-Gateway-Topologie] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Datencenter-Gateway-Topologie")</span><span class="sxs-lookup"><span data-stu-id="a3de4-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="a3de4-145">In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a3de4-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="a3de4-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span><span class="sxs-lookup"><span data-stu-id="a3de4-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="a3de4-147">Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3de4-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="a3de4-148">Gateway Location</span><span class="sxs-lookup"><span data-stu-id="a3de4-148">Gateway Location</span></span>

<span data-ttu-id="a3de4-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="a3de4-153">Gateway Size and Number</span><span class="sxs-lookup"><span data-stu-id="a3de4-153">Gateway Size and Number</span></span>

<span data-ttu-id="a3de4-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span><span class="sxs-lookup"><span data-stu-id="a3de4-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="a3de4-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="a3de4-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="a3de4-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span><span class="sxs-lookup"><span data-stu-id="a3de4-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="a3de4-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span><span class="sxs-lookup"><span data-stu-id="a3de4-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="a3de4-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails. </span><span class="sxs-lookup"><span data-stu-id="a3de4-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="a3de4-165">Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="a3de4-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

