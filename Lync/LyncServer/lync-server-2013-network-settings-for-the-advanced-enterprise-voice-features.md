---
title: 'Lync Server 2013: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d6b01009aac5fdaf3d69e24b4137897e70051b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="62e01-102">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e01-103">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="62e01-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="62e01-104">Lync Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="62e01-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="62e01-105">Diese Features Teilen bestimmte Konfigurationsanforderungen für netzwerkregionen, Netzwerkstandorte und Zuordnungen der einzelnen Subnetze in der lync Server Topologie mit einem Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="62e01-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="62e01-106">Ausführliche Informationen zur Bereitstellungsplanung für diese Funktionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="62e01-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="62e01-107">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="62e01-108">Planung von Notrufdiensten (E9-1-1) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="62e01-109">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="62e01-110">Ausführliche Informationen zur Bereitstellung der einzelnen Funktionen finden Sie unter [Deploying Advanced Enterprise Voice Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="62e01-111">Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die allen drei erweiterten Enterprise-VoIP-Features gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="62e01-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="62e01-112">Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="62e01-112">Network Regions</span></span>

<span data-ttu-id="62e01-113">Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62e01-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62e01-114">Netzwerkregionen sind nicht identisch mit lync Server Einwahlkonferenz Regionen, die zum Zuordnen von Zugriffsnummern für Einwahlkonferenzen mit einem oder mehreren lync Server Wählplänen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="62e01-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="62e01-115">Ausführliche Informationen zu Regionen mit Einwahlkonferenzen finden Sie unter <A href="lync-server-2013-dial-in-conferencing-requirements.md">Einwahlkonferenz Anforderungen in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="62e01-116">Für die Anrufsteuerung ist es erforderlich, dass für jede netzwerkregion ein zugeordneter lync Server zentraler Standort vorhanden ist, der den Mediendatenverkehr innerhalb der Region verwaltet (also Entscheidungen basierend auf den von Ihnen konfigurierten Richtlinien trifft, ob eine echt Zeit-Audio-oder Videositzung möglich ist oder nicht. festgelegt werden).</span><span class="sxs-lookup"><span data-stu-id="62e01-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="62e01-117">Lync Server zentralen Standorte stellen keine geografischen Standorte, sondern logische Gruppen von Servern dar, die als Pool oder eine Gruppe von Pools konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="62e01-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="62e01-118">Ausführliche Informationen zu zentralen Standorten finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="62e01-119">Siehe auch [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="62e01-120">Zum Konfigurieren einer netzwerkregion können Sie entweder die Registerkarte **Regionen** im Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder die Cmdlets **New-CsNetworkRegion** oder **CsNetworkRegion** lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="62e01-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="62e01-121">Anweisungen finden Sie unter [erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="62e01-122">Die gleichen Netzwerkbereichs Definitionen werden von allen drei erweiterten Enterprise-VoIP-Funktionen gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="62e01-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="62e01-123">Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="62e01-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="62e01-124">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="62e01-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="62e01-125">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="62e01-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="62e01-126">Zum Zuordnen eines lync Server zentralen Standorts zu einer netzwerkregion geben Sie den Namen des zentralen Standorts entweder mithilfe des Abschnitts " **Netzwerkkonfiguration** " in lync Server-Systemsteuerung oder durch Ausführen der Cmdlets " **New-CsNetworkRegion** " oder " **Sets-CsNetworkRegion** lync Server-Verwaltungsshell" an.</span><span class="sxs-lookup"><span data-stu-id="62e01-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="62e01-127">Anweisungen finden Sie unter [erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="62e01-128">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="62e01-128">Network Sites</span></span>

<span data-ttu-id="62e01-p107">Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="62e01-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62e01-131">Netzwerkstandorte werden nur von den erweiterten Enterprise-VoIP-Funktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="62e01-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="62e01-132">Sie sind nicht identisch mit den Zweigstellenstandorten, die Sie in ihrer lync Server Topologie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62e01-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="62e01-133">Ausführliche Informationen zu Zweigstellenstandorten finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-reference-topologies.md">Referenz Topologien in lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="62e01-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="62e01-134">Siehe auch <A href="lync-server-2013-supported-topologies.md">Unterstützte Topologien in lync Server 2013</A> in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="62e01-135">Zum Konfigurieren eines Netzwerkstandorts und Zuordnen dieser zu einer netzwerkregion können Sie entweder den Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder die lync Server-Verwaltungsshell Cmdlets **New-CsNetworkSite** oder **CsNetworkSite** ausführen.</span><span class="sxs-lookup"><span data-stu-id="62e01-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="62e01-136">Ausführliche Informationen finden Sie unter [erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in der Bereitstellungsdokumentation, oder lesen Sie die lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="62e01-137">Identifizieren von IP-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="62e01-137">Identify IP Subnets</span></span>

<span data-ttu-id="62e01-p110">Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="62e01-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="62e01-p111">Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="62e01-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="62e01-142">Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="62e01-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="62e01-143">Ein lync-Client nimmt seine lokale IP-Adresse an und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske.</span><span class="sxs-lookup"><span data-stu-id="62e01-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="62e01-144">Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="62e01-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="62e01-145">Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt.</span><span class="sxs-lookup"><span data-stu-id="62e01-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="62e01-146">(Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung selbst dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)</span><span class="sxs-lookup"><span data-stu-id="62e01-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="62e01-147">Wenn sich beispielsweise ein lync-Client auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske 255.255.255.0 anmeldet, wird die Umgehungs-ID angefordert, die dem Subnetz 172.29.81.0 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="62e01-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="62e01-148">Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht.</span><span class="sxs-lookup"><span data-stu-id="62e01-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="62e01-149">Daher ist es wichtig, dass der Administrator die Subnetze genau so eingibt, wie von lync-Clients bereitgestellt (die mit Subnetzen während der Netzwerkkonfiguration entweder statisch oder durch DHCP (Dynamic Host Configuration Protocol) konfiguriert sind.)</span><span class="sxs-lookup"><span data-stu-id="62e01-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="62e01-150">Zuordnen von Subnetzen zu Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="62e01-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="62e01-151">Jedes Subnetz im Unternehmensnetzwerk muss einem Netzwerkstandort zugeordnet sein (das heißt, jedes Subnetz muss einem geografischen Standort zugeordnet sein).</span><span class="sxs-lookup"><span data-stu-id="62e01-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="62e01-152">Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP-Funktionen, die Endpunkte geografisch zu finden.</span><span class="sxs-lookup"><span data-stu-id="62e01-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="62e01-153">Durch das Auffinden der Endpunkte kann die Anrufsteuerung beispielsweise den Fluss von Audio-und Videodaten in Echtzeit regulieren, die an den Netzwerkstandort und von diesem gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="62e01-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="62e01-154">Um Subnetzen Netzwerkstandorten zuzuordnen, können Sie entweder den Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder den lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="62e01-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="62e01-155">Anweisungen hierzu finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="62e01-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62e01-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62e01-156">See Also</span></span>


[<span data-ttu-id="62e01-157">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="62e01-158">Planung von Notrufdiensten (E9-1-1) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="62e01-159">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e01-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

