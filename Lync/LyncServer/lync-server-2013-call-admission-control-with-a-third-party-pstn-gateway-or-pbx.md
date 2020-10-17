---
title: Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7abd33af2dd2a7a5858fd8b888201b6471d0cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502812"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="56abf-102">Anrufsteuerung in lync Server 2013 mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="56abf-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56abf-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="56abf-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="56abf-104">In diesem Thema werden Beispiele für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) auf der Verbindung zwischen der Gatewayschnittstelle des Vermittlungsservers und einem Drittanbieter-PSTN-Gateway  (Public Switched Telephone Network) oder einer Festnetztelefonanlage beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56abf-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="56abf-105">Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="56abf-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="56abf-106">Die Anrufsteuerung kann auf der WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers zu einer Drittanbieter-Nebenstellenanlage oder einem PSTN-Gateway bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="56abf-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="56abf-107">**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="56abf-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="56abf-108">![Fall 1: Anrufsteuerung zwischen Vermittlungsserver PSTN-Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Fall 1: Anrufsteuerung zwischen Vermittlungsserver PSTN-Gateway")</span><span class="sxs-lookup"><span data-stu-id="56abf-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="56abf-p101">In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway angewendet. Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway an Netzwerkstandort 2 tätigt, fließen die Medien durch die WAN-Leitung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="56abf-p101">In this example, CAC is applied between the Mediation Server and a PSTN gateway. If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link. Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="56abf-112">Zwischen der Lync-Clientanwendung und dem Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="56abf-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="56abf-113">Zwischen dem Vermittlungsserver und dem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="56abf-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="56abf-114">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="56abf-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56abf-115">Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="56abf-116">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="56abf-117">Ausführliche Informationen finden Sie unter Zuordnen eines Subnetzes <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">zu einem Netzwerkstandort in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56abf-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="56abf-118">Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="56abf-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="56abf-p102">Diese Konfiguration ähnelt Fall 1. In beiden Fällen kennt der Vermittlungsserver das Gerät, das Medien am anderen Ende der WAN-Leitung abschließt, und die IP-Adresse des PSTN-Gateways oder der Nebenstellenanlage mit Medienendpunkt (Media Termination Point, MTP) ist als nächster Hop auf dem Vermittlungsserver konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="56abf-p102">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="56abf-121">**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="56abf-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="56abf-122">![Fall 2: Anrufsteuerung zwischen Vermittlungsserver Nebenstellenanlage mit MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Fall 2: Anrufsteuerung zwischen Vermittlungsserver Nebenstellenanlage mit MTP")</span><span class="sxs-lookup"><span data-stu-id="56abf-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="56abf-p103">In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt angewendet. Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen PSTN-Anruf über die Nebenstellenanlage/den Medienendpunkt an Netzwerkstandort 2 tätigt, fließen die Medien durch die WAN-Leitung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="56abf-p103">In this example, CAC is applied between the Mediation Server and the PBX/MTP. If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link. Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="56abf-126">Zwischen der Lync-Clientanwendung und dem Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="56abf-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="56abf-127">Zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="56abf-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="56abf-128">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="56abf-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56abf-129">Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="56abf-130">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="56abf-131">Ausführliche Informationen finden Sie unter Zuordnen eines Subnetzes <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">zu einem Netzwerkstandort in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56abf-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="56abf-132">Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="56abf-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="56abf-p104">Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn die Drittanbieter-Nebenstellenanlage keinen Medienendpunkt aufweist, kann der Vermittlungsserver bei einer ausgehenden Sitzungsanforderung an die Drittanbieter-Nebenstellenanlage nicht ermitteln, wo Mediendaten innerhalb des Nebenstellensystems terminiert werden. In diesem Fall fließen die Medien direkt zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunktgerät.</span><span class="sxs-lookup"><span data-stu-id="56abf-p104">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="56abf-136">**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="56abf-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="56abf-137">![Fall 3: Anrufsteuerung zwischen Vermittlungsserver Nebenstellenanlage Nr. mtp](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Fall 3: Anrufsteuerung zwischen Vermittlungsserver Nebenstellenanlage Nr. mtp")</span><span class="sxs-lookup"><span data-stu-id="56abf-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="56abf-p105">Wenn ein Lync-Clientbenutzer an Netzwerkstandort 1 einen Anruf an einen Benutzer über die Nebenstellenanlage tätigt, kann der Vermittlungsserver in diesem Beispiel werden Prüfungen in Bezug auf die Anrufsteuerung nur im Proxysegment (zwischen der Lync-Clientanwendung und dem Vermittlungsserver) durchführen. Da der Vermittlungsserver während der Sitzungsanforderung keine Informationen über das Endpunktgerät besitzt, können für die WAN-Verbindung vor Herstellung des Anrufs keine Prüfungen in Bezug auf die Anrufsteuerung durchgeführt werden (zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunkt). Nach dem Einrichten der Sitzung erleichtert der Vermittlungsserver jedoch die Bereitstellung der für den Trunk verwendeten Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="56abf-p105">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server). Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment. After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="56abf-141">Für Anrufe, die vom Drittanbieter-Endpunkt ausgehen, stehen die Informationen über dieses Endpunktgerät zum Zeitpunkt der Sitzungsanforderung zur Verfügung, und Prüfungen in Bezug auf die Anrufsteuerung können auf beiden Seiten des Vermittlungsservers durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="56abf-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56abf-142">Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="56abf-143">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="56abf-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="56abf-144">Ausführliche Informationen finden Sie unter Zuordnen eines Subnetzes <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">zu einem Netzwerkstandort in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56abf-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

