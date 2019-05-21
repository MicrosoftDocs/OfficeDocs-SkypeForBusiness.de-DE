---
title: Komponenten und Topologien für die Anrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planen der Anrufannahme Steuerung (CAC), wenn Sie über ein MPLS-Netzwerk, einen SIP-Stamm oder ein PSTN-Gateway oder eine Telefonanlage eines Drittanbieters verfügen. Gilt für Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 326387b7b0794b3cbd027d539880f8c4b40f42d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277013"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="40b6d-104">Komponenten und Topologien für die Anrufsteuerung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40b6d-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="40b6d-105">Planen der Anrufannahme Steuerung (CAC), wenn Sie über ein MPLS-Netzwerk, einen SIP-Stamm oder ein PSTN-Gateway oder eine Telefonanlage eines Drittanbieters verfügen.</span><span class="sxs-lookup"><span data-stu-id="40b6d-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="40b6d-106">Gilt für Skype for Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="40b6d-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="40b6d-107">Die Themen in diesem Abschnitt liefern Informationen zu speziellen Faktoren, die bei der Bereitstellung der Anrufsteuerung mit verschiedenen Typen von Netzwerktopologien berücksichtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="40b6d-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="40b6d-108">Anrufsteuerung in einem MPLS-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="40b6d-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="40b6d-p103">In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="40b6d-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="40b6d-113">**Beispiel eines MPLS-Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="40b6d-113">**Example MPLS network**</span></span>

![Anrufsteuerung mit MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="40b6d-p104">Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der Abbildung oben darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, die die MPLS-Cloud darstellt.</span><span class="sxs-lookup"><span data-stu-id="40b6d-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="40b6d-118">**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="40b6d-118">**Network region and network sites for an MPLS network**</span></span>

![Anrufsteuerung mit MPLS (Diagramm)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="40b6d-120">Anrufsteuerung für einen SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="40b6d-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="40b6d-p105">Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="40b6d-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="40b6d-123">Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.</span><span class="sxs-lookup"><span data-stu-id="40b6d-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="40b6d-124">**Konfiguration der Anrufsteuerung für einen SIP-Trunk**</span><span class="sxs-lookup"><span data-stu-id="40b6d-124">**CAC configuration on a SIP trunk**</span></span>

![Anrufsteuerung – SIP-Trunking (Diagramm)](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="40b6d-126">Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="40b6d-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="40b6d-p106">Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert. Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video an diesem Netzwerkstandort. Ausführliche Informationen finden Sie unter [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="40b6d-p106">Create a network site to represent the ITSP. Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site. For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40b6d-p107">Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig. Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt 2 angewendet.</span><span class="sxs-lookup"><span data-stu-id="40b6d-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="40b6d-132">Erstellen Sie einen Inter-Site-Link für den SIP-Trunk unter Verwendung der relevanten Parameterwerte für die Website, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="40b6d-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="40b6d-133">Verwenden Sie beispielsweise den Namen der Netzwerk Website in Ihrem Unternehmen als Wert des NetworkSiteID1-Parameters und die ITSP-Netzwerk Website als Wert des NetworkSiteID2-Parameters.</span><span class="sxs-lookup"><span data-stu-id="40b6d-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="40b6d-134">Ausführliche Informationen finden Sie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in der Bereitstellungsdokumentation und [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="40b6d-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="40b6d-135">Rufen Sie die IP-Adresse des SCB-medienendpunkt (Session Border Controller) von Ihrem ITSP.</span><span class="sxs-lookup"><span data-stu-id="40b6d-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="40b6d-136">Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="40b6d-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="40b6d-137">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b6d-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="40b6d-138">Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="40b6d-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="40b6d-139">In diesem Thema werden Beispiele für die Bereitstellung der Anrufannahme Steuerung (CAC) für den Link zwischen der Gateway-Schnittstelle des Vermittlungsservers und einem PSTN-Gateway (Public Switched Telephone Network) oder einer PBX (Private Branch Exchange) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40b6d-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="40b6d-140">Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="40b6d-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="40b6d-141">CAC kann auf der WAN-Verbindung vom Gateway-Interface des Mediation-Servers zu einer PBX-Anlage oder einem PSTN-Gateway eines Drittanbieters bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="40b6d-142">**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="40b6d-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="40b6d-144">In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und einem PSTN-Gateway angewendet.</span><span class="sxs-lookup"><span data-stu-id="40b6d-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="40b6d-145">Wenn ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="40b6d-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="40b6d-146">Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="40b6d-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="40b6d-147">Zwischen der Skype for Business-Clientanwendung und dem Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="40b6d-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="40b6d-148">Zwischen dem Vermittlungs Server und dem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="40b6d-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="40b6d-149">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-150">Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-151">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-152">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b6d-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="40b6d-153">Fall 2: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage mit medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="40b6d-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="40b6d-154">Diese Konfiguration ähnelt Fall 1.</span><span class="sxs-lookup"><span data-stu-id="40b6d-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="40b6d-155">In beiden Fällen weiß der Vermittlungsserver, welches Gerät Medien am gegenüberliegenden Ende der WAN-Verbindung beendet, und die IP-Adresse des PSTN-Gateways oder der Telefonanlage mit Media Termination Point (MTP) wird auf dem Vermittlungsserver als nächster Hop konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="40b6d-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="40b6d-156">**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="40b6d-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage mit MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="40b6d-158">In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und der PBX/MTP angewendet.</span><span class="sxs-lookup"><span data-stu-id="40b6d-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="40b6d-159">Wenn ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über die Telefonanlage/MTP in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="40b6d-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="40b6d-160">Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="40b6d-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="40b6d-161">Zwischen der Skype for Business-Clientanwendung und dem Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="40b6d-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="40b6d-162">Zwischen dem Vermittlungs Server und der PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="40b6d-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="40b6d-163">Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-164">Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-165">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-166">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b6d-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="40b6d-167">Fall 3: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage ohne medienendpunkt</span><span class="sxs-lookup"><span data-stu-id="40b6d-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="40b6d-168">Fall 3 unterscheidet sich leicht von den ersten beiden Fällen.</span><span class="sxs-lookup"><span data-stu-id="40b6d-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="40b6d-169">Wenn kein MTP auf der Drittanbieter-Telefonanlage vorhanden ist, kann der Vermittlungs Server für eine ausgehende Sitzungs Anfrage an die Drittanbieter-PBX-Anlage nicht wissen, wo Medien in der PBX-Grenze beendet werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="40b6d-170">In diesem Fall fließt das Medium direkt zwischen dem Vermittlungs Server und dem Endpunktgerät eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="40b6d-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="40b6d-171">**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**</span><span class="sxs-lookup"><span data-stu-id="40b6d-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Festnetztelefonanlage ohne MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="40b6d-173">Wenn in diesem Beispiel ein Skype for Business-Clientbenutzer am Netzwerkstandort 1 einen Benutzer über die Telefonanlage anruft, kann der Vermittlungsserver CAC-Prüfungen nur auf dem Proxy-Leg durchführen (zwischen der Skype for Business-Clientanwendung und dem Vermittlungsserver).</span><span class="sxs-lookup"><span data-stu-id="40b6d-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="40b6d-174">Da der Vermittlungsserver keine Informationen über das Endpunktgerät aufweist, während die Sitzung angefordert wird, können keine CAC-Prüfungen für die WAN-Verbindung (zwischen dem Vermittlungsserver und dem Endpunkt des Drittanbieters) vor der Einrichtung des Anrufs durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="40b6d-175">Nach dem Einrichten der Sitzung vereinfacht der Vermittlungs Server jedoch die Berechnung der im trunk verwendeten Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="40b6d-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="40b6d-176">Bei Anrufen, die vom Endpunkt eines Drittanbieters stammen, sind die Informationen zu diesem Endpunktgerät zum Zeitpunkt der Sitzungsanforderung verfügbar, und die CAC-Prüfung kann sowohl auf den Seiten des Vermittlungsservers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40b6d-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-177">Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-178">Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40b6d-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="40b6d-179">Ausführliche Informationen finden Sie unter [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b6d-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


