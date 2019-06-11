---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung von SIP-Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="45f15-102">Prüfliste für die Bereitstellung von SIP-Trunks für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45f15-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45f15-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="45f15-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="45f15-104">Bevor Sie einen SIP-Trunk bereitstellen können, müssen Sie und Ihr Dienstanbieter einige grundlegende Verbindungsinformationen zu ihren jeweiligen SIP-Trunk-Endpunkten austauschen.</span><span class="sxs-lookup"><span data-stu-id="45f15-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="45f15-105">Rufen Sie die folgenden Informationen für jedes ITSP-Gateway ab, mit dem Sie eine Verbindung herstellen:</span><span class="sxs-lookup"><span data-stu-id="45f15-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="45f15-106">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="45f15-106">IP address</span></span>

  - <span data-ttu-id="45f15-107">Vollständig qualifizierter Domänenname (FQDN)</span><span class="sxs-lookup"><span data-stu-id="45f15-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45f15-108">Der Dienstanbieter fordert Sie möglicherweise auf, mit mehr als einem ITSP-Gateway zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="45f15-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="45f15-109">In diesem Fall müssen Sie eine Verbindung zwischen jedem ITSP-Gateway und jedem Vermittlungs Server in Ihrem Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="45f15-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="45f15-110">Die Informationen, die Sie Ihrem Dienstanbieter geben, hängen von Ihrem SIP Trunk-Verbindungstyp ab:</span><span class="sxs-lookup"><span data-stu-id="45f15-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="45f15-111">Für Multiprotocol-Label-Switching (MPLS) oder private Netzwerkverbindungen geben Sie der ITSP die öffentlich routingfähige IP-Adresse des Routers in Ihrem Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz).</span><span class="sxs-lookup"><span data-stu-id="45f15-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="45f15-112">Überprüfen Sie, ob der Gateway-oder Session Border Controller (SBC) am ITSP diese Adresse erreichen kann.</span><span class="sxs-lookup"><span data-stu-id="45f15-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="45f15-113">Geben Sie dem ITSP auch den FQDN Ihres Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="45f15-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="45f15-114">Geben Sie für VPN-Verbindungen (virtuelles privates Netzwerk) der ITSP die IP-Adresse Ihres VPN-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="45f15-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="45f15-115">Überlegungen zu Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="45f15-115">Certificate Considerations</span></span>

<span data-ttu-id="45f15-116">Wenn Sie feststellen möchten, ob Sie ein Zertifikat für SIP-Trunking benötigen, erkundigen Sie sich bei Ihrem ITSP zu Protokollunterstützung:</span><span class="sxs-lookup"><span data-stu-id="45f15-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="45f15-117">Wenn Ihr ITSP nur TCP (Transmission Control Protocol) unterstützt, benötigen Sie kein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="45f15-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="45f15-118">Wenn Ihr ITSP TLS (Transport Layer Security) unterstützt, muss Ihnen der ITSP ein Zertifikat zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="45f15-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45f15-119">SIP funktioniert in Verbindung mit RTP (Real-Time Transport Protocol) oder SRTP (Secure Real-Time Transport Protocol), den Protokollen, die die eigentlichen Sprach Daten in VoIP-Anrufen (Voice over Internet Protocol) verwalten.</span><span class="sxs-lookup"><span data-stu-id="45f15-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="45f15-120">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="45f15-120">Deployment Process</span></span>

<span data-ttu-id="45f15-121">Führen Sie die folgenden Schritte aus, um die lync Server-Seite der SIP Trunk-Verbindung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="45f15-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="45f15-122">Erstellen und konfigurieren Sie mithilfe des lync Server Topology Builder die SIP-Domänentopologie.</span><span class="sxs-lookup"><span data-stu-id="45f15-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="45f15-123">Ausführliche Informationen finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45f15-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="45f15-124">Konfigurieren Sie mithilfe der lync Server-Systemsteuerung das VoIP-Routing für die neue SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="45f15-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="45f15-125">Ausführliche Informationen finden Sie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45f15-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="45f15-126">Testen Sie die Konnektivität mithilfe des Cmdlets **Test-CsPstnOutboundCall** .</span><span class="sxs-lookup"><span data-stu-id="45f15-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="45f15-127">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell oder in der Hilfe zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="45f15-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

