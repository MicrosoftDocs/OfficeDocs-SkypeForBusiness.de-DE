---
title: 'Lync Server 2013: Prüfliste für SIP-Trunk Bereitstellung'
description: 'Lync Server 2013: Prüfliste für SIP-Trunk Bereitstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559041"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="180ba-103">Prüfliste für SIP-Trunk Bereitstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180ba-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180ba-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="180ba-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="180ba-105">Bevor Sie einen SIP-Trunk bereitstellen können, müssen Sie und Ihr Dienstanbieter einige grundlegende Verbindungsinformationen zu ihren jeweiligen Endpunkten des SIP-Trunks austauschen.</span><span class="sxs-lookup"><span data-stu-id="180ba-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="180ba-106">Für jedes ITSP-Gateway, mit dem Sie eine Verbindung herstellen, benötigen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="180ba-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="180ba-107">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="180ba-107">IP address</span></span>

  - <span data-ttu-id="180ba-108">Vollqualifizierter Domänenname (FQDN)</span><span class="sxs-lookup"><span data-stu-id="180ba-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="180ba-109">Der Dienstanbieter bittet Sie möglicherweise, eine Verbindung mit mehreren ITSP-Gateways herzustellen.</span><span class="sxs-lookup"><span data-stu-id="180ba-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="180ba-110">In diesem Fall müssen Sie eine Verbindung zwischen jedem ITSP-Gateway und jedem Vermittlungsserver in Ihrem Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="180ba-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="180ba-111">Die Informationen, die Sie für Ihren Dienstanbieter bereitstellen, hängen vom Verbindungstyp Ihres SIP-Trunks ab:</span><span class="sxs-lookup"><span data-stu-id="180ba-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="180ba-112">Für MPLS (Multiprotocol Label Switching)- oder private Netzwerkverbindungen stellen Sie dem ITSP die öffentlich routingfähige IP-Adresse des Routers in Ihrem Umkreisnetzwerk (auch als Demilitarized Zone, DMZ, und überwachtes Subnetz bezeichnet) bereit.</span><span class="sxs-lookup"><span data-stu-id="180ba-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="180ba-113">Stellen Sie sicher, dass diese Adresse vom Gateway oder Session Border Controller (SBC) auf der ITSP-Seite kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="180ba-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="180ba-114">Geben Sie dem ITSP auch den FQDN ihrer Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="180ba-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="180ba-115">Für VPN-Verbindungen (Virtual Private Network) teilen Sie dem ITSP die IP-Adresse Ihres VPN-Servers mit.</span><span class="sxs-lookup"><span data-stu-id="180ba-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="180ba-116">Überlegungen zu Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="180ba-116">Certificate Considerations</span></span>

<span data-ttu-id="180ba-117">Fragen Sie Ihren ITSP nach den unterstützten Protokollen, um zu ermitteln, ob Sie ein Zertifikat für das SIP-Trunking benötigen:</span><span class="sxs-lookup"><span data-stu-id="180ba-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="180ba-118">Wenn Ihr ITSP nur TCP unterstützt, benötigen Sie kein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="180ba-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="180ba-119">Wenn Ihr ITSP Unterstützung für TLS (Transport Layer Security) bietet, muss Ihnen der ITSP ein Zertifikat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="180ba-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="180ba-120">SIP wird mit RTP (Real-time Transport Protocol) oder SRTP (Secure Real-time Transport Protocol) eingesetzt, den Protokollen für die eigentlichen VoIP-Daten in VoIP-Anrufen.</span><span class="sxs-lookup"><span data-stu-id="180ba-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="180ba-121">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="180ba-121">Deployment Process</span></span>

<span data-ttu-id="180ba-122">Führen Sie die folgenden Schritte aus, um die lync Server Seite der SIP-trunkverbindung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="180ba-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="180ba-123">Erstellen und konfigurieren Sie mithilfe des lync Server Topologie-Generators die SIP-Domänentopologie.</span><span class="sxs-lookup"><span data-stu-id="180ba-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="180ba-124">Ausführliche Informationen finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="180ba-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="180ba-125">Konfigurieren Sie mithilfe der lync Server-Systemsteuerung das VoIP-Routing für die neue SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="180ba-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="180ba-126">Ausführliche Informationen finden Sie unter [Configuring Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="180ba-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="180ba-127">Testen Sie die Konnektivität mithilfe des Cmdlets **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="180ba-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="180ba-128">Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation oder in der Hilfe zu lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="180ba-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

