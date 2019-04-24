---
title: Komponenten und Topologien für die anrufsteuerung in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planung für die anrufsteuerung (CAC), wenn Sie einem MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder einer Nebenstellenanlage verfügen. Gilt für Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 7022ade98dbd614023a4faaea283b939fa658e73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207952"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="e348c-104">Komponenten und Topologien für die anrufsteuerung in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="e348c-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="e348c-105">Planung für die anrufsteuerung (CAC), wenn Sie einem MPLS-Netzwerk, einen SIP-Trunk oder ein Drittanbieter-PSTN-Gateway oder einer Nebenstellenanlage verfügen.</span><span class="sxs-lookup"><span data-stu-id="e348c-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="e348c-106">Gilt für Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="e348c-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="e348c-107">Die Themen in diesem Abschnitt liefern Informationen zu speziellen Faktoren, die bei der Bereitstellung der Anrufsteuerung mit verschiedenen Typen von Netzwerktopologien berücksichtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="e348c-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="e348c-108">Anrufsteuerung in einem MPLS-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e348c-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="e348c-p103">In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e348c-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="e348c-113">**Beispiel eines MPLS-Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="e348c-113">**Example MPLS network**</span></span>

![Anrufsteuerung mit MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="e348c-p104">Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der Abbildung oben darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, die die MPLS-Cloud darstellt.</span><span class="sxs-lookup"><span data-stu-id="e348c-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="e348c-118">**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="e348c-118">**Network region and network sites for an MPLS network**</span></span>

![Anrufsteuerung mit MPLS (Diagramm)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="e348c-120">Anrufsteuerung für einen SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="e348c-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="e348c-p105">Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e348c-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="e348c-123">Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.</span><span class="sxs-lookup"><span data-stu-id="e348c-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="e348c-124">**Konfiguration der Anrufsteuerung für einen SIP-Trunk**</span><span class="sxs-lookup"><span data-stu-id="e348c-124">**CAC configuration on a SIP trunk**</span></span>

![Anrufsteuerung – SIP-Trunking (Diagramm)](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="e348c-126">Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e348c-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="e348c-p106">Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert. Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video an diesem Netzwerkstandort. Ausführliche Informationen finden Sie unter [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e348c-p106">Create a network site to represent the ITSP. Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site. For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e348c-p107">Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig. Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt 2 angewendet.</span><span class="sxs-lookup"><span data-stu-id="e348c-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="e348c-132">Erstellen Sie eine standortübergreifende Verbindung für den SIP-Trunk mit den entsprechenden Parameterwerten für die Website, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e348c-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="e348c-133">Verwenden Sie beispielsweise den Namen des den Netzwerkstandort in Ihrem Unternehmen als Wert des Parameters NetworkSiteID1 und den Netzwerkstandort ITSP als Wert des Parameters NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="e348c-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="e348c-134">Weitere Informationen hierzu finden Sie unter [Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype für Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in der Dokumentation zur Bereitstellung und [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e348c-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="e348c-135">Die IP-Adresse von der Controller des (SCB) Medienendpunkt aus Ihrem ITSP.</span><span class="sxs-lookup"><span data-stu-id="e348c-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="e348c-136">Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="e348c-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="e348c-137">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="e348c-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="e348c-138">Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="e348c-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="e348c-139">In diesem Thema wird beschrieben, Beispiele, wie die anrufsteuerung (CAC) auf den Link zwischen Gatewayschnittstelle des Vermittlungsservers und einem Gateway Drittanbieter-public switched Telephone Network (Telefonfestnetz PSTN) oder private Branch Exchange, (Nebenstellenanlage PBX) bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e348c-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="e348c-140">Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="e348c-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="e348c-141">CAC bereitgestellt werden kann, über die WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers mit einem Drittanbieter-PBX- oder PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="e348c-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="e348c-142">**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="e348c-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="e348c-144">In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und ein PSTN-Gateway angewendet.</span><span class="sxs-lookup"><span data-stu-id="e348c-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="e348c-145">Wenn eine Skype Business-Client-Benutzers an Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Netzwerkstandort 2 platziert, werden über die WAN-Verbindung das Medium übertragen.</span><span class="sxs-lookup"><span data-stu-id="e348c-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="e348c-146">Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="e348c-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="e348c-147">Zwischen dem Skype für Business-Clientanwendung und dem Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e348c-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="e348c-148">Zwischen dem Vermittlungsserver und PSTN-gateway</span><span class="sxs-lookup"><span data-stu-id="e348c-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="e348c-149">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="e348c-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-150">Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e348c-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-151">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e348c-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-152">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="e348c-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="e348c-153">Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="e348c-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="e348c-154">Diese Konfiguration ähnelt Fall 1.</span><span class="sxs-lookup"><span data-stu-id="e348c-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="e348c-155">In beiden Fällen der Vermittlungsserver weiß, welches Gerät auf dem Installationsdatenträger unter entgegengesetzten Ende der WAN-Verbindung beendet und die IP-Adresse des PSTN-Gateway oder der Nebenstellenanlage mit Media Beendigung Point (MTP) auf dem Vermittlungsserver als Nächster Hop konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e348c-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="e348c-156">**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="e348c-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="e348c-158">In diesem Beispiel wird die Anrufsteuerung zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt angewendet.</span><span class="sxs-lookup"><span data-stu-id="e348c-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="e348c-159">Wenn eine Skype Business-Client-Benutzers an den Netzwerkstandort 1 einen PSTN-Anruf über die Nebenstellenanlage/MTP befindet sich im Netzwerkstandort 2 tätigt, werden die Medien über die WAN-Verbindung übertragen.</span><span class="sxs-lookup"><span data-stu-id="e348c-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="e348c-160">Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="e348c-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="e348c-161">Zwischen dem Skype für Business-Clientanwendung und dem Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e348c-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="e348c-162">Zwischen dem Vermittlungsserver und der Nebenstellenanlage/dem Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="e348c-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="e348c-163">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="e348c-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-164">Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e348c-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-165">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e348c-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-166">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="e348c-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="e348c-167">Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="e348c-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="e348c-168">Fall 3 unterscheidet sich leicht von den ersten beiden Fällen.</span><span class="sxs-lookup"><span data-stu-id="e348c-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="e348c-169">Wenn in der Drittanbieter-Nebenstellenanlage ohne MTP vorhanden ist, für eine ausgehende Sitzung weiß Anforderung an die Drittanbieter-Nebenstellenanlage des Vermittlungsservers nicht, in dem Medien in die Nebenstellenanlage Grenze beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e348c-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="e348c-170">In diesem Fall fließt Mediums direkt zwischen dem Vermittlungsserver und das Gerät Drittanbieter-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="e348c-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="e348c-171">**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="e348c-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="e348c-173">In diesem Beispiel wird ist eine Skype Business-Client-Benutzers an Netzwerkstandort 1 einen Anruf an einen Benutzer über die Nebenstellenanlage platziert der Vermittlungsserver CAC Überprüfungen nur auf Proxy vom Abschnitt zwischen dem (der Skype für Business-Clientanwendung) und Mediation Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="e348c-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="e348c-174">Da der Vermittlungsserver keinen Informationen zu dem Endgerät während die Sitzung angefordert wird, können nicht CAC Überprüfungen ausgeführt werden, über die WAN-Link (zwischen dem Vermittlungsserver und dem Drittanbieter-Endpunkt) vor dem Herstellen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="e348c-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="e348c-175">Nachdem die Sitzung eingerichtet ist, jedoch erleichtert der Vermittlungsserver in der Buchhaltung für die auf dem Trunk verwendete Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="e348c-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="e348c-176">Für Anrufe, die vom Endpunkt von Drittanbietern stammen, die Informationen zu diesem Gerät Endpunkt ist zum Zeitpunkt der sitzungsanforderung und CAC Kontrollkästchen auf beiden Seiten des Vermittlungsservers durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e348c-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-177">Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e348c-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-178">Stellen Sie sicher, dass das IP-Subnetz, dem beide Schnittstellen des Vermittlungsservers angehören, konfiguriert und Netzwerkstandort 1 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e348c-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e348c-179">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="e348c-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


