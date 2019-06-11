---
title: 'Lync Server 2013: Konfigurieren von Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d40a290f75ae48b73a4695e04ea2934b0c4d695
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="12520-102">Konfigurieren von Trunks in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12520-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12520-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12520-104">Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="12520-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="12520-105">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="12520-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="12520-106">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="12520-106">PSTN gateway</span></span>

  - <span data-ttu-id="12520-107">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="12520-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="12520-108">Ausführliche Informationen finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="12520-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12520-109">Bevor Sie die trunk-Konfiguration beginnen, stellen Sie sicher, dass die Topologie erstellt wurde und dass der Vermittlungs Server und sein Peer konfiguriert und miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="12520-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="12520-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="12520-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="12520-111">Als Teil der trunk-Konfiguration können Sie das lync Server 2013-Feature für die medienumgehung aktivieren, mit dem Medien den Vermittlungs Server umgehen können.</span><span class="sxs-lookup"><span data-stu-id="12520-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="12520-112">Trunks kann entweder mit oder ohne aktivierte medienumgehung konfiguriert werden, wir empfehlen jedoch dringend, diese zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12520-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="12520-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planen der medienumgehung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="12520-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12520-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="12520-114">In This Section</span></span>

  - [<span data-ttu-id="12520-115">Mehrere trunk-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="12520-116">Zwischen trunk-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="12520-117">Anzeigen von trunk-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="12520-118">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="12520-119">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="12520-120">Erstellen einer neuen Sammlung von trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="12520-121">Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12520-122">Ändern der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12520-123">Testen der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12520-124">Anzeigen von Informationen zu einzelnen SIP-Stämmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12520-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12520-125">See Also</span></span>


[<span data-ttu-id="12520-126">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="12520-127">Planen der PSTN-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="12520-128">Planung der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12520-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

