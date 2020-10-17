---
title: 'Lync Server 2013: Komponenten und Topologien für SIP-Trunking'
description: 'Lync Server 2013: Komponenten und Topologien für das SIP-Trunking.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549521"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="c9bb1-103">Komponenten und Topologien für SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9bb1-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9bb1-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c9bb1-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c9bb1-105">In der folgenden Abbildung ist die SIP-Trunking-Topologie in lync Server dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="c9bb1-106">**SIP-Trunking-Topologie**</span><span class="sxs-lookup"><span data-stu-id="c9bb1-106">**SIP trunking topology**</span></span>

<span data-ttu-id="c9bb1-107">![SIP-Trunking-Topologie](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP-Trunking-Topologie")</span><span class="sxs-lookup"><span data-stu-id="c9bb1-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="c9bb1-108">Wie im Diagramm dargestellt, wird ein IP-virtuelles privates Netzwerk (VPN) für die Konnektivität zwischen dem Unternehmensnetzwerk und dem PSTN-Dienstanbieter (Public Switched Telephone Network) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-108">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="c9bb1-109">Der Zweck dieses privaten Netzwerks besteht darin, IP-Konnektivität bereitzustellen, die Sicherheit zu erhöhen und (optional) Qualitätsgarantien (Quality of Service, QoS) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-109">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="c9bb1-110">Aufgrund der Beschaffenheit eines VPN müssen Sie TLS (Transport Layer Security) für den SIP-Signalisierungs Datenverkehr oder das Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-110">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="c9bb1-111">Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen daher aus einfachen TCP-Verbindungen für SIP und RTP (Plain Real-Time Transport Protocol) (über UDP) für Medien, die über ein IP-VPN getunnelt werden.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-111">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="c9bb1-112">Stellen Sie sicher, dass für alle Firewalls zwischen den VPN-Routern Ports geöffnet sind, damit die VPN-Router kommunizieren können, und dass die IP-Adressen an den externen Rändern der VPN-Router öffentlich geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-112">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9bb1-113">Wenden Sie sich an Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit bietet, einschließlich Failover.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="c9bb1-114">Wenn dies der Fall ist, müssen Sie die Verfahren für die Einrichtung bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="c9bb1-115">Müssen Sie beispielsweise pro Vermittlungsserver nur eine IP-Adresse und einen SIP-Trunk konfigurieren, oder müssen mehrere SIP-Trunks pro Vermittlungsserver konfiguriert werden?</span><span class="sxs-lookup"><span data-stu-id="c9bb1-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="c9bb1-116">Wenn Sie über mehrere zentrale Standorte verfügen, Fragen Sie auch, ob der Dienstanbieter Verbindungen zu und von einem anderen zentralen Standort aus aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c9bb1-117">Für das SIP-Trunking wird dringend empfohlen, eigenständige Vermittlungsserver bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="c9bb1-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Definition Peers in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="c9bb1-119">Sichern des Vermittlungsserver für SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="c9bb1-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="c9bb1-120">Aus Sicherheitsgründen sollten Sie für jede Verbindung zwischen den beiden VPN-Routern ein virtuelles LAN (VLAN) einrichten.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-120">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="c9bb1-121">Der eigentliche Prozess für die Einrichtung eines VLAN variiert von einem Router-Hersteller zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-121">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="c9bb1-122">Weitere Informationen erhalten Sie von Ihrem Router-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-122">For details, contact your router vendor.</span></span>

<span data-ttu-id="c9bb1-123">Es wird empfohlen, folgende Richtlinien zu befolgen:</span><span class="sxs-lookup"><span data-stu-id="c9bb1-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="c9bb1-124">Richten Sie ein virtuelles LAN (VLAN) zwischen dem Vermittlungsserver und dem VPN-Router im Umkreisnetzwerk ein (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="c9bb1-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="c9bb1-125">Lassen Sie keine Übertragung von Broadcast-oder Multicastpaketen vom Router in das VLAN zu.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="c9bb1-126">Blockieren Sie alle Routingregeln, die Datenverkehr vom Router an eine beliebige Stelle weiterleiten, jedoch auf den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="c9bb1-127">Wenn Sie einen VPN-Server verwenden, sollten Sie die folgenden Richtlinien befolgen:</span><span class="sxs-lookup"><span data-stu-id="c9bb1-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="c9bb1-128">Richten Sie ein VLAN zwischen dem VPN-Server und dem Vermittlungsserver ein.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="c9bb1-129">Lassen Sie keine Übertragung von Broadcast-oder Multicastpaketen vom VPN-Server an das VLAN zu.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="c9bb1-130">Blockieren Sie alle Routingregeln, die den VPN-Server Datenverkehr an eine beliebige Stelle weiterleiten, jedoch auf den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="c9bb1-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="c9bb1-131">Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).</span><span class="sxs-lookup"><span data-stu-id="c9bb1-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

