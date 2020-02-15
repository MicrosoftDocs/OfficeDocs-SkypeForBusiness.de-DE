---
title: Konfigurieren der globalen Einstellungen für die medienumgehung zur Verwendung von Standort-und Regionsinformationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="c5001-102">Konfigurieren der globalen Einstellungen für die medienumgehung in lync Server 2013 zur Verwendung von Standort-und Regionsinformationen</span><span class="sxs-lookup"><span data-stu-id="c5001-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5001-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c5001-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c5001-104">In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung bereits für Trunkverbindungen zwischen dem Vermittlungsserver und einem Peer (PSTN)-Gateway, einer IP-Nebenstellenanlage oder dem Session Border Controller (SBC) eines Anbieters von Internettelefoniediensten (ITSP) für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5001-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="c5001-105">In diesem Thema wird auch davon ausgegangen, dass Sie alle zentralen Standorte und Zweigstellen im Topologie-Generator so definiert haben, dass Sie mit der netzwerkregion, dem Netzwerkstandort und der Subnetz Konfiguration übereinstimmen, die Sie gemäß den Schritten unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>und einem <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Netzwerkstandort in lync Server 2013 zuordnen</A>.</span><span class="sxs-lookup"><span data-stu-id="c5001-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="c5001-106">Falls die Konfigurationen nicht übereinstimmen, ist die Medienumgehung nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c5001-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="c5001-p102">Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie auch die globalen Einstellungen konfigurieren. Wenn Sie die globalen Einstellungen für die Medienumgehung anhand der hier beschriebenen Schritte durchführen, wird vorausgesetzt, dass eine der folgenden Bedingungen für Ihre Konfiguration zutrifft:</span><span class="sxs-lookup"><span data-stu-id="c5001-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="c5001-109">Sie verfügen *nicht* über eine gute Konnektivität zwischen lync Server Endpunkten und allen Peers, für die Sie die medienumgehung für die trunkverbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="c5001-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="c5001-110">Die Anrufsteuerung (Call Admission Control, CAC) zur Bandbreitenverwaltung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c5001-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c5001-111">Ausführliche Informationen zu den Überlegungen zur Anrufsteuerung und zur medienumgehung finden Sie im Abschnitt "Anrufsteuerung für PSTN-Verbindungen" unter <A href="lync-server-2013-media-bypass-and-mediation-server.md">medienumgehung und Vermittlungsserver in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c5001-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="c5001-p103">Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c5001-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="c5001-115">Oder führen Sie diese Schritte aus, wenn die Informationen zu Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden sollen, Sie jedoch nicht die Anrufsteuerung aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c5001-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="c5001-116">In diesem Fall müssen Links zur Bandbreiteneinschränkung weiterhin über Netzwerk-standortübergreifende Richtlinien dargestellt werden, wie unter [Create Network Standort-Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5001-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="c5001-117">Die tatsächlichen Bandbreiteneinschränkungen sind hierbei weniger wichtig, da die Anrufsteuerung nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c5001-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="c5001-118">Stattdessen werden diese Verbindungen zur Partitionierung von Subnetzen verwendet, um Verbindungen mit Bandbreitenbeschränkungen anzugeben, die für die Medienumgehung eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="c5001-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="c5001-119">Beachten Sie, dass dies auch gilt, wenn sowohl die Anrufsteuerung als auch die Medienumgehung aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c5001-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="c5001-120">Damit die Umgehung ordnungsgemäß funktioniert, muss außerdem Konsistenz zwischen einem Standort gemäß Definition im Topologie-Generator und wie er definiert ist, wenn Sie netzwerkregionen und Netzwerkstandorte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c5001-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="c5001-121">Wenn Sie beispielsweise einen Zweigstellenstandort haben, den Sie im Topologie-Generator als nur ein PSTN-Gateway festgelegt haben, muss dieser Zweigstellenstandort mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, mit der Zweigstellenbenutzer ihre PSTN-Anrufe über das PSTN weiterleiten können. Gateway am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="c5001-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="c5001-122">So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="c5001-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="c5001-123">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c5001-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5001-124">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5001-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c5001-125">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c5001-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="c5001-126">Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="c5001-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="c5001-127">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c5001-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="c5001-128">Klicken Sie auf **Konfiguration von Standorten und Regionen verwenden**.</span><span class="sxs-lookup"><span data-stu-id="c5001-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="c5001-129">Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c5001-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c5001-p107">Aktivieren Sie dieses Kontrollkästchen nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigstandorten zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c5001-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="c5001-133">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c5001-133">Click **Commit**.</span></span>

<span data-ttu-id="c5001-134">Fügen Sie dann dem Netzwerkstandort Subnetze hinzu, wie in [Zuordnen von Subnetzen mit Netzwerkstandorten für die medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5001-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="c5001-135">(Die tatsächlichen Verfahren zum Zuordnen von Subnetzen zu Netzwerkstandorten werden in [Zuordnen eines Subnetzes mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)beschrieben.) Nachdem Sie alle Subnetze mit Netzwerkstandorten verknüpft haben, ist die Bereitstellung der medienumgehung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c5001-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c5001-136">Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="c5001-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="c5001-137">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A> und <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c5001-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5001-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5001-138">See Also</span></span>


[<span data-ttu-id="c5001-139">Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5001-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

