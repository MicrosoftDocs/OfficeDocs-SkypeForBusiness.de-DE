---
title: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d90fdcb368bf6ed9d610f214122900add5b15547
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="38e4d-102">Bereitstellungsoptionen für PSTN-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e4d-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38e4d-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="38e4d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="38e4d-104">PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="38e4d-104">PSTN Gateways</span></span>

<span data-ttu-id="38e4d-105">PSTN-Gateways (Public Switched Telephone Network) sind Drittanbieter-Hardwarekomponenten, die Signal-und Medien Verbindungen zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung mit SIP-Trunks.</span><span class="sxs-lookup"><span data-stu-id="38e4d-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="38e4d-106">In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar.</span><span class="sxs-lookup"><span data-stu-id="38e4d-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="38e4d-107">Das Gateway ist in seinem eigenen Subnetz isoliert und über das Vermittlungsserver mit dem Unternehmensnetzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="38e4d-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="38e4d-108">In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="38e4d-109">Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über ein Survivable Branch Appliance herstellen, der Gateway und Server in einem einzigen Feld kombiniert.</span><span class="sxs-lookup"><span data-stu-id="38e4d-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="38e4d-110">Wenn Zweigstellenstandorte ein Gateway verwenden, sind sowohl eine Registrierungsstelle als auch Vermittlungsserver vor Ort erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig.</span><span class="sxs-lookup"><span data-stu-id="38e4d-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="38e4d-111">Ein oder mehrere Vermittlungsserver, die auf Front-End-Servern zusammengestellt sind, können Anrufe für ein oder mehrere Gateways an jedem Standort weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="38e4d-112">Es wird empfohlen, die für die Website erforderlichen Registrierungsstellen, Vermittlungsserver und Gateways als Survivable Branch Appliance bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="38e4d-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="38e4d-113">Die Ermittlung der Anzahl, Größe und des Speicherorts von PSTN-Gateways ist vielleicht die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="38e4d-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="38e4d-p103">Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="38e4d-p104">Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).</span><span class="sxs-lookup"><span data-stu-id="38e4d-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="38e4d-p105">Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="38e4d-p106">Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="38e4d-122">Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt "Gatewaytopologien" weiter unten in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="38e4d-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="38e4d-123">M:N-Trunkunterstützung</span><span class="sxs-lookup"><span data-stu-id="38e4d-123">M:N Trunk Support</span></span>

<span data-ttu-id="38e4d-124">Die Vermittlungsserver können Anrufe über mehrere Gateways, Session Border Controller (SBCS), die von Internet Telefonie-Dienstanbietern bereitgestellt werden, oder eine Kombination aus beiden weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="38e4d-125">Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren.</span><span class="sxs-lookup"><span data-stu-id="38e4d-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="38e4d-126">Die logische Route, die zwischen einem Vermittlungsserver und einem Gateway definiert wird, wird *trunk*genannt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="38e4d-127">Wenn ein interner Benutzer einen PSTN-Anruf tätigt, wählt die ausgehende Routinglogik auf dem Front-End-Pool aus, welcher trunk alle möglichen Kombinationen weiterleiten soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="38e4d-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="38e4d-128">Wenn beim DNS-Lastenausgleich ein Anruf aufgrund eines Problems mit einer bestimmten Vermittlungsserver im Pool nicht zu einem Gateway gelangt, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="38e4d-129">Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [m:n-trunk trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="38e4d-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="38e4d-130">Ausführliche Informationen zu weiteren Verbesserungen beim ausgehenden Routing finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="38e4d-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="38e4d-131">Gatewaytopologien</span><span class="sxs-lookup"><span data-stu-id="38e4d-131">Gateway Topologies</span></span>

<span data-ttu-id="38e4d-132">Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="38e4d-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="38e4d-133">Zählen Sie die Standorte, an denen Sie die PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="38e4d-134">Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl von Benutzern und durchschnittliche Anzahl von Anrufen pro Stunde und Benutzer).</span><span class="sxs-lookup"><span data-stu-id="38e4d-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="38e4d-135">Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="38e4d-136">Die folgende Abbildung zeigt die verteilte Gatewaytopologie, die Sie auf diese Weise erhalten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="38e4d-137">**Verteilte Gatewaytopologie**</span><span class="sxs-lookup"><span data-stu-id="38e4d-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="38e4d-138">![Topologie-Diagramm für verteilte Gateways](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")</span><span class="sxs-lookup"><span data-stu-id="38e4d-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="38e4d-p108">In dieser Topologie werden alle Anrufe zwischen Mitarbeitern innerhalb jedes Standorts sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind – was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="38e4d-142">Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellungeines oder mehrerer großer Telefonie-zentraler Standorte, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="38e4d-143">**Topologie mit einem zentralen Standort für die Telefonie**</span><span class="sxs-lookup"><span data-stu-id="38e4d-143">**Telephony central site topology**</span></span>

<span data-ttu-id="38e4d-144">![Rechenzentrums-Gateway-Topologie](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Rechenzentrums-Gateway-Topologie")</span><span class="sxs-lookup"><span data-stu-id="38e4d-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="38e4d-145">In dieser Topologie werden an jedem zentralen Standort mehrere große Gateways bereitgestellt, die für die erwartete Benutzerlast ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="38e4d-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="38e4d-146">Alle Anrufe bei Benutzern im Unternehmen werden durch den Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="38e4d-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="38e4d-147">Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="38e4d-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="38e4d-148">Gatewaystandort</span><span class="sxs-lookup"><span data-stu-id="38e4d-148">Gateway Location</span></span>

<span data-ttu-id="38e4d-p110">Auch der Gatewaystandort bestimmt möglicherweise, welche Typen von Gateways Sie auswählen und wie Sie diese konfigurieren können. Es gibt Dutzende von PSTN-Protokollen, von denen jedoch keines weltweiter Standard ist. Wenn sich all Ihre Gateways in einem einzigen Land bzw. einer einzigen Region befinden, stellt dies kein Problem dar. Wenn Sie jedoch Gateways in mehreren Ländern/Regionen platzieren, muss jedes Gateway gemäß den dort verwendeten PSTN-Standards konfiguriert werden. Außerdem sind die Gateways, die beispielsweise für den Betrieb in Kanada zugelassen sind, in Indien, Brasilien oder der Europäischen Union möglicherweise nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="38e4d-153">Größe und Anzahl von Gateways</span><span class="sxs-lookup"><span data-stu-id="38e4d-153">Gateway Size and Number</span></span>

<span data-ttu-id="38e4d-p111">Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports. (Es gibt sogar noch größere Gateways; diese werden jedoch hauptsächlich von Telefonanbietern verwendet.) Um zu schätzen, wie viele Ports in Ihrer Organisation benötigt werden, beachten Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="38e4d-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="38e4d-p112">Wenn in Ihrer Organisation wenig telefoniert wird (ein PSTN-Anruf pro Benutzer und Stunde), sollten Sie einen Port für jeweils 15 Benutzer zuordnen. Wenn beispielsweise 20 Benutzer vorhanden sind, benötigen Sie ein Gateway mit zwei Ports.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="38e4d-p113">Wenn in Ihrer Organisation mäßig viel telefoniert wird (zwei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 10 Benutzer zuordnen. Wenn beispielsweise 100 Benutzer vorhanden sind, benötigen Sie insgesamt 10 Ports, die Sie auf einem oder auf mehreren Gateways zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="38e4d-p114">Wenn in Ihrer Organisation viel telefoniert wird (mindestens drei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 5 Benutzer zuordnen. Wenn beispielsweise 47.000 Benutzer vorhanden sind, benötigen Sie insgesamt 9.400 Ports, die Sie auf mindestens 10 großen Gateways zuordnen sollten.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="38e4d-162">Zusätzliche Ports können erworben werden, wenn die Benutzeranzahl oder der Umfang des Datenverkehrs in Ihrer Organisation steigt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="38e4d-p115">Für jede zu unterstützende Benutzeranzahl können Sie entweder wenige größere Gateways oder mehrere kleine bereitstellen. Prinzipiell werden für jede Organisation mindestens zwei Gateways empfohlen, um die Verfügbarkeit sicherzustellen, falls ein Gateway ausfällt.</span><span class="sxs-lookup"><span data-stu-id="38e4d-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="38e4d-165">Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über eine entsprechende Vermittlungsserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="38e4d-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

