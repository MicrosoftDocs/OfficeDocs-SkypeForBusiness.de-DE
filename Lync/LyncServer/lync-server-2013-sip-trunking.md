---
title: 'Lync Server 2013: SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3ee2efb7f1c392b20bdc6b16ff3c7063ebe4759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="52d40-102">SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d40-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d40-103">_**Letztes Änderungsstand des Themas:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="52d40-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="52d40-p101">SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Instant Messaging, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von *SIP-Trunks*, eine Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="52d40-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="52d40-106">Was ist SIP-Trunking?</span><span class="sxs-lookup"><span data-stu-id="52d40-106">What is SIP Trunking?</span></span>

<span data-ttu-id="52d40-p102">Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. Ein SIP-Trunk wird typischerweise verwendet, um den zentralen Standort Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.</span><span class="sxs-lookup"><span data-stu-id="52d40-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="52d40-110">SIP-Trunks im Vergleich zu direkten SIP-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="52d40-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="52d40-111">Der Begriff *Trunk* wurde aus der leitungsvermittelten Technologie abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="52d40-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="52d40-112">Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen.</span><span class="sxs-lookup"><span data-stu-id="52d40-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="52d40-113">Wie bei ihren Vorgänger-, Time Division Multiplexing (TDM)-Trunks sind SIP-Trunks Verbindungen zwischen zwei getrennten SIP-Netzwerken – dem lync Server 2013 Enterprise und dem ITSP.</span><span class="sxs-lookup"><span data-stu-id="52d40-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="52d40-114">Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="52d40-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="52d40-115">Ausführliche Informationen zu den unterstützten Verbindungstypen finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="52d40-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="52d40-116">Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt).</span><span class="sxs-lookup"><span data-stu-id="52d40-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="52d40-117">Ausführliche Informationen dazu, wie Sie direkte SIP-Verbindungen mit lync Server 2013 verwenden können, finden Sie unter [Direct SIP Connections in lync Server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="52d40-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52d40-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="52d40-118">In This Section</span></span>

  - [<span data-ttu-id="52d40-119">Übersicht über das SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d40-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="52d40-120">Wie kann ich SIP-Trunking in lync Server 2013 implementieren?</span><span class="sxs-lookup"><span data-stu-id="52d40-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="52d40-121">Komponenten und Topologien für SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d40-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="52d40-122">SIP-Trunking für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d40-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="52d40-123">Prüfliste für SIP-Trunk Bereitstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d40-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

