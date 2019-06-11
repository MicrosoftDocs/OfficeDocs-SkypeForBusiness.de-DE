---
title: Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="9e032-102">Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e032-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e032-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9e032-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9e032-104">In diesem Thema werden Beispiele für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) auf der Verbindung zwischen der Gatewayschnittstelle des Vermittlungsservers und einem Drittanbieter-PSTN-Gateway  (Public Switched Telephone Network) oder einer Festnetztelefonanlage beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e032-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="9e032-105">Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="9e032-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="9e032-106">Die Anrufsteuerung kann auf der WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers zu einer Drittanbieter-Nebenstellenanlage oder einem PSTN-Gateway bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="9e032-107">**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="9e032-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="9e032-108">![Fall 1: CAC zwischen dem PSTN-Gateway des Vermittlungsservers] (images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Fall 1: CAC zwischen dem PSTN-Gateway des Vermittlungsservers")</span><span class="sxs-lookup"><span data-stu-id="9e032-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="9e032-109">In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und einem PSTN-Gateway angewendet.</span><span class="sxs-lookup"><span data-stu-id="9e032-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="9e032-110">Wenn ein lync-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9e032-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="9e032-111">Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="9e032-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="9e032-112">Zwischen der lync-Clientanwendung und dem Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="9e032-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="9e032-113">Zwischen dem Vermittlungs Server und dem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="9e032-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="9e032-114">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e032-115">Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="9e032-116">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="9e032-117">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e032-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="9e032-118">Fall 2: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage mit medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="9e032-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="9e032-119">Diese Konfiguration ähnelt Fall 1.</span><span class="sxs-lookup"><span data-stu-id="9e032-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="9e032-120">In beiden Fällen weiß der Vermittlungsserver, welches Gerät Medien am gegenüberliegenden Ende der WAN-Verbindung beendet, und die IP-Adresse des PSTN-Gateways oder der Telefonanlage mit Media Termination Point (MTP) wird auf dem Vermittlungsserver als nächster Hop konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9e032-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="9e032-121">**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="9e032-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="9e032-122">![Fall 2: CAC zwischen Vermittlungs Server-PBX mit MTP] (images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Fall 2: CAC zwischen Vermittlungs Server-PBX mit MTP")</span><span class="sxs-lookup"><span data-stu-id="9e032-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="9e032-123">In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und der PBX/MTP angewendet.</span><span class="sxs-lookup"><span data-stu-id="9e032-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="9e032-124">Wenn ein lync-Clientbenutzer an der Netzwerk Website 1 einen PSTN-Anruf über die Telefonanlage/MTP in der Netzwerk Website 2 platziert, fließt das Medium über die WAN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9e032-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="9e032-125">Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="9e032-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="9e032-126">Zwischen der lync-Clientanwendung und dem Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="9e032-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="9e032-127">Zwischen dem Vermittlungs Server und der PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="9e032-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="9e032-128">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e032-129">Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="9e032-130">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="9e032-131">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e032-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="9e032-132">Fall 3: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage ohne medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="9e032-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="9e032-133">Fall 3 unterscheidet sich leicht von den ersten beiden Fällen.</span><span class="sxs-lookup"><span data-stu-id="9e032-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="9e032-134">Wenn kein MTP auf der Drittanbieter-Telefonanlage vorhanden ist, kann der Vermittlungs Server für eine ausgehende Sitzungs Anfrage an die Drittanbieter-PBX-Anlage nicht wissen, wo Medien in der PBX-Grenze beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="9e032-135">In diesem Fall fließt das Medium direkt zwischen dem Vermittlungs Server und dem Endpunktgerät eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="9e032-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="9e032-136">**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="9e032-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="9e032-137">![Fall 3: CAC zwischen Vermittlungs Server-PBX No MTP] (images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Fall 3: CAC zwischen Vermittlungs Server-PBX No MTP")</span><span class="sxs-lookup"><span data-stu-id="9e032-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="9e032-138">Wenn in diesem Beispiel ein lync-Clientbenutzer am Netzwerkstandort 1 einen Benutzer über die Telefonanlage anruft, kann der Vermittlungsserver CAC-Prüfungen nur auf dem Proxy-Leg durchführen (zwischen der lync-Clientanwendung und dem Vermittlungsserver).</span><span class="sxs-lookup"><span data-stu-id="9e032-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="9e032-139">Da der Vermittlungsserver keine Informationen über das Endpunktgerät aufweist, während die Sitzung angefordert wird, können keine CAC-Prüfungen für die WAN-Verbindung (zwischen dem Vermittlungsserver und dem Endpunkt des Drittanbieters) vor der Einrichtung des Anrufs durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="9e032-140">Nach dem Einrichten der Sitzung vereinfacht der Vermittlungs Server jedoch die Berechnung der im trunk verwendeten Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="9e032-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="9e032-141">Bei Anrufen, die vom Endpunkt eines Drittanbieters stammen, sind die Informationen zu diesem Endpunktgerät zum Zeitpunkt der Sitzungsanforderung verfügbar, und die CAC-Prüfung kann sowohl auf den Seiten des Vermittlungsservers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e032-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e032-142">Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="9e032-143">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e032-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="9e032-144">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e032-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

