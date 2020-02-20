---
title: 'Lync Server 2013: Konfigurieren von Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="1fa73-102">Konfigurieren von Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa73-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1fa73-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1fa73-104">Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um eine PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="1fa73-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="1fa73-105">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="1fa73-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="1fa73-106">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="1fa73-106">PSTN gateway</span></span>

  - <span data-ttu-id="1fa73-107">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="1fa73-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="1fa73-108">Ausführliche Informationen finden Sie unter [Planning for PSTN Connectivity in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1fa73-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1fa73-109">Bevor Sie mit der Trunkkonfiguration beginnen, überprüfen Sie, ob die Topologie erstellt und der Vermittlungsserver und der Peer konfiguriert und einander zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="1fa73-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="1fa73-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a Gateway in Topology Builder in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1fa73-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1fa73-111">Im Rahmen der trunkkonfiguration können Sie die lync Server 2013 medienumgehung aktivieren, die es Medien ermöglicht, das Vermittlungsserver zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="1fa73-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="1fa73-112">Trunks können mit oder ohne Medienumgehung konfiguriert werden, die Aktivierung dieser Funktion wird jedoch dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1fa73-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="1fa73-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1fa73-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1fa73-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1fa73-114">In This Section</span></span>

  - [<span data-ttu-id="1fa73-115">Unterstützung mehrerer Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="1fa73-116">Zwischen trunk Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="1fa73-117">Anzeigen von trunk Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="1fa73-118">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="1fa73-119">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="1fa73-120">Erstellen Sie in lync Server 2013 eine neue Auflistung von trunkkonfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1fa73-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fa73-121">Löschen einer vorhandenen Auflistung von SIP-trunkkonfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fa73-122">Ändern von SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fa73-123">Testen von Konfigurationseinstellungen für SIP-Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fa73-124">Anzeigen von Informationen zu einzelnen SIP-Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1fa73-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fa73-125">See Also</span></span>


[<span data-ttu-id="1fa73-126">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="1fa73-127">Planen der PSTN-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="1fa73-128">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa73-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

