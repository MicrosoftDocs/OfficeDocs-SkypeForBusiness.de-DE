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

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen. In either topology, the gateway terminates the PSTN. Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.

An enterprise with multiple sites would typically deploy one or more gateways at each site. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig. Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden. Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.

Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent

  - How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).

  - What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.

  - Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.

 You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).

<div>

## <a name="mn-trunk-support"></a>M:N Trunk Support

Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als *trunk*bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind. Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [M:N trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).

Details zu weiteren Verbesserungen des ausgehenden Routings finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Gateway Topologies

When you consider the fundamental questions of gateway deployment, follow these steps:

1.  Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2.  Estimate the traffic at each site (number of users and average number of calls per hour per user).

3.  Deploy one or more gateways at each site to handle the anticipated traffic.

Die resultierende verteilte Gateway-Topologie wird in der folgenden Abbildung gezeigt.

**Topologie des verteilten Gateways**

![Topologie-Diagramm für verteilte Gateways] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")

With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen, wie in der nachstehenden Abbildung zu sehen, ein oder einige wenige große Telefonie-Zentrale Standorte bereitzustellen.

**Topologie des zentralen Telefonie-Standorts**

![Datencenter-Gateway-Topologie] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Datencenter-Gateway-Topologie")

In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt. All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site. Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.

</div>

<div>

## <a name="gateway-location"></a>Gateway Location

Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.

</div>

<div>

## <a name="gateway-size-and-number"></a>Gateway Size and Number

The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:

  - Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.

  - Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.

  - Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.

  - Additional ports can be acquired as the number of users or amount of traffic in your organization increases.

For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails. 

Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

