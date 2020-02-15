---
title: 'Lync Server 2013: Definieren der Anforderungen für die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d26596f48178f53f79b1c4cc136610d45705ffd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="26d37-102">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d37-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d37-103">_**Letztes Änderungsstand des Themas:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="26d37-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="26d37-p101">Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.</span><span class="sxs-lookup"><span data-stu-id="26d37-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="26d37-106">Identifizieren Sie die Hubs/Backbones (als *Netzwerkregionen* bezeichnet) in Ihrem Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="26d37-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="26d37-107">Identifizieren Sie die Niederlassungen oder Standorte (als *Netzwerkstandorte* bezeichnet) innerhalb jeder Netzwerkregion.</span><span class="sxs-lookup"><span data-stu-id="26d37-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="26d37-108">Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.</span><span class="sxs-lookup"><span data-stu-id="26d37-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="26d37-109">Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="26d37-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d37-110">Bandbreitengrenzwerte bezeichnen, wie viel Bandbreite einer WAN-Verbindung für Enterprise-VoIP-und Audio/Video-Datenverkehr zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="26d37-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="26d37-111">Wenn eine WAN-Verbindung als eine Verbindung mit "Bandbreiteneinschränkungen" beschrieben wird, liegt die Bandbreitengrenze der WAN-Verbindung unter dem erwarteten Spitzendatenverkehr über diese Verbindung.</span><span class="sxs-lookup"><span data-stu-id="26d37-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="26d37-112">Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="26d37-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="26d37-113">Zur Erläuterung dieser Konzepte wird die in der folgenden Abbildung dargestellte Beispielnetzwerktopologie herangezogen.</span><span class="sxs-lookup"><span data-stu-id="26d37-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="26d37-114">**Beispieltopologie für die Anrufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="26d37-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="26d37-115">![Beispiel für eine Netzwerktopologie mit Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Beispiel für eine Netzwerktopologie mit Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="26d37-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d37-p103">Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte "Portland", "Reno" und "Albuquerque" in der Region "Nordamerika" enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte "Chicago", "New York" und "Detroit" werden innerhalb des Regionenovals "Nordamerika" angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="26d37-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="26d37-120">Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="26d37-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="26d37-121">Ausführliche Informationen zur Planung dieser Topologie, einschließlich der Bandbreitenbeschränkungen, finden Sie unter [Beispiel: Sammeln der Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="26d37-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="26d37-122">Identifizieren der Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="26d37-122">Identify Network Regions</span></span>

<span data-ttu-id="26d37-123">Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.</span><span class="sxs-lookup"><span data-stu-id="26d37-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="26d37-p105">Ein Netzwerkbackbone oder Hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="26d37-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="26d37-p106">Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="26d37-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="26d37-130">Zuordnen eines zentralen Standorts zu jeder Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="26d37-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="26d37-131">Für die Anrufsteuerung muss für jede netzwerkregion ein lync Server zentraler Standort definiert sein.</span><span class="sxs-lookup"><span data-stu-id="26d37-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="26d37-132">Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet.</span><span class="sxs-lookup"><span data-stu-id="26d37-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="26d37-133">In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="26d37-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="26d37-134">Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="26d37-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d37-135">Zentrale Standorte entsprechen nicht unbedingt Netzwerkstandorten.</span><span class="sxs-lookup"><span data-stu-id="26d37-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="26d37-136">In den Beispielen in dieser Dokumentation haben einige zentrale Standorte – Chicago, London und Peking – denselben Namen wie die Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="26d37-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="26d37-137">Selbst wenn ein zentraler Standort und ein Netzwerkstandort denselben Namen haben, ist der zentrale Standort jedoch ein Element der lync Server-Topologie, wohingegen der Netzwerkstandort Teil des Gesamtnetzwerks ist, in dem sich die lync Server-Topologie befindet.</span><span class="sxs-lookup"><span data-stu-id="26d37-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="26d37-138">Netzwerkregionen, zentrale Standorte und Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="26d37-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26d37-139">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="26d37-139">Network Region</span></span></th>
<th><span data-ttu-id="26d37-140">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="26d37-140">Central Site</span></span></th>
<th><span data-ttu-id="26d37-141">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="26d37-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26d37-142">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="26d37-142">North America</span></span></p></td>
<td><p><span data-ttu-id="26d37-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="26d37-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="26d37-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="26d37-144">Chicago</span></span></p>
<p><span data-ttu-id="26d37-145">New York</span><span class="sxs-lookup"><span data-stu-id="26d37-145">New York</span></span></p>
<p><span data-ttu-id="26d37-146">Detroit</span><span class="sxs-lookup"><span data-stu-id="26d37-146">Detroit</span></span></p>
<p><span data-ttu-id="26d37-147">Portland</span><span class="sxs-lookup"><span data-stu-id="26d37-147">Portland</span></span></p>
<p><span data-ttu-id="26d37-148">Reno</span><span class="sxs-lookup"><span data-stu-id="26d37-148">Reno</span></span></p>
<p><span data-ttu-id="26d37-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="26d37-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="26d37-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="26d37-151">London</span><span class="sxs-lookup"><span data-stu-id="26d37-151">London</span></span></p></td>
<td><p><span data-ttu-id="26d37-152">London</span><span class="sxs-lookup"><span data-stu-id="26d37-152">London</span></span></p>
<p><span data-ttu-id="26d37-153">Köln</span><span class="sxs-lookup"><span data-stu-id="26d37-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-154">APAC</span><span class="sxs-lookup"><span data-stu-id="26d37-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="26d37-155">Peking</span><span class="sxs-lookup"><span data-stu-id="26d37-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="26d37-156">Peking</span><span class="sxs-lookup"><span data-stu-id="26d37-156">Beijing</span></span></p>
<p><span data-ttu-id="26d37-157">Manila</span><span class="sxs-lookup"><span data-stu-id="26d37-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="26d37-158">Identifizieren von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="26d37-158">Identify Network Sites</span></span>

<span data-ttu-id="26d37-p109">Ein Netzwerkstandort repräsentiert einen Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Beginnen Sie damit, alle Büros Ihrer Organisation zu erfassen. In der verwendeten Beispieltopologie umfasst die Netzwerkregion "Nordamerika" die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="26d37-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="26d37-p110">Sie müssen jeden Netzwerkstandort einer Netzwerkregion zuordnen. Abhängig davon, ob der Netzwerkstandort über eine eingeschränkte WAN-Verbindung verfügt oder nicht, wird dem Netzwerkstandort eine Bandbreitenrichtlinie zugeordnet. Ausführliche Informationen zu Anrufsteuerungsrichtlinien und der Bandbreite, die Sie über die Richtlinienverwendung zuweisen, finden Sie im Abschnitt "Definieren von Bandbreitenrichtlinien" weiter unten in diesem Thema. Zum Konfigurieren der Anrufsteuerung ordnen Sie Netzwerkstandorte Netzwerkregionen zu. Anschließend erstellen Sie Richtlinien zur Bandbreitenzuweisung, die auf Verbindungen mit Bandbreiteneinschränkungen zwischen einem Standort oder einer Region und die WAN-Verbindungen zwischen den Standorten und Regionen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="26d37-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="26d37-167">Identifizieren von Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="26d37-167">Identify Network Links</span></span>

<span data-ttu-id="26d37-p111">Netzwerkverbindungen repräsentieren Verbindungen zum physischen WAN, das unterschiedliche Regionen und Standorte verknüpft. In der Beispieltopologie sind zwei regionale Netzwerkverbindungen enthalten, fünf Netzwerkverbindungen zwischen Regionen und Standorten und eine Netzwerkverbindung zwischen zwei Standorten.</span><span class="sxs-lookup"><span data-stu-id="26d37-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="26d37-170">Die zwei regionalen Verbindungen befinden sich zwischen "Nordamerika" und "EMEA", dargestellt als "NA-EMEA-LINK", und zwischen "APAC" und "EMEA", dargestellt als "EMEA-APAC-LINK".</span><span class="sxs-lookup"><span data-stu-id="26d37-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="26d37-p112">Die Standortverbindungen kennzeichnen die Leitungen zur Verbindung von "Portland", "Reno" und "Albuquerque" mit der Region "Nordamerika", zur Verbindung von "Manila" mit der Region "APAC" und zur Verbindung von "Köln" mit der Region "EMEA".  Die Verbindung zwischen "Reno" und "Albuquerque" kennzeichnet eine direkte Netzwerkverbindung zwischen diesen zwei Standorten.</span><span class="sxs-lookup"><span data-stu-id="26d37-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="26d37-173">Definieren von Bandbreitenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="26d37-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="26d37-p113">Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verfügbare WAN-Bandbreite für in Echtzeit übertragenen Audio- und Videodatenverkehr über die WAN-Verbindungen in Ihrer Organisation zu ermitteln. Bandbreitenrichtlinien werden üblicherweise auf WAN-Verbindungen angewendet, wenn die Bandbreite eingeschränkt ist, wenn also der erwartete Datenverkehr die Bandbreite übersteigt, die für Audio- und Videodaten zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="26d37-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="26d37-p114">*Bandbreitenrichtlinien* für die Anrufsteuerung definieren, wie viel Bandbreite für in Echtzeit übertragene Audio- und Videodaten reserviert ist. Da die Bandbreite für anderen Datenverkehr bei der Anrufsteuerung nicht begrenzt wird, kann nicht verhindert werden, dass dieser die gesamte Netzwerkbandbreite durch Aktionen wie das Übertragen großer Dateien oder das Streamen von Musik beansprucht.</span><span class="sxs-lookup"><span data-stu-id="26d37-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="26d37-178">Bandbreitenrichtlinien für die Anrufsteuerung können einige oder alle der folgenden Werte definieren:</span><span class="sxs-lookup"><span data-stu-id="26d37-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="26d37-179">Maximal reservierte Gesamtbandbreite für Audiodaten</span><span class="sxs-lookup"><span data-stu-id="26d37-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="26d37-180">Maximal reservierte Gesamtbandbreite für Videodaten</span><span class="sxs-lookup"><span data-stu-id="26d37-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="26d37-181">Maximal reservierte Bandbreite für einen einzelnen Audioanruf (Sitzung)</span><span class="sxs-lookup"><span data-stu-id="26d37-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="26d37-182">Maximal reservierte Bandbreite für einen einzelnen Videoanruf (Sitzung)</span><span class="sxs-lookup"><span data-stu-id="26d37-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d37-183">Alle Bandbreitenwerte für die Anrufsteuerung stellen Maximalwerte für die <EM>unidirektionale</EM> Bandbreitenbeschränkung dar.</span><span class="sxs-lookup"><span data-stu-id="26d37-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="26d37-184">Die lync Server 2013 VoIP-Richtlinienfeatures bieten die Möglichkeit, die Bandbreitenrichtlinien Überprüfungen für eingehende Anrufe des Benutzers außer Kraft zu setzen (nicht für ausgehende Anrufe, die vom Benutzer getätigt werden).</span><span class="sxs-lookup"><span data-stu-id="26d37-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="26d37-185">Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet.</span><span class="sxs-lookup"><span data-stu-id="26d37-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="26d37-186">Diese Einstellung sollte mit Bedacht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26d37-186">This setting should be used sparingly.</span></span> <span data-ttu-id="26d37-187">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="26d37-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="26d37-p116">Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="26d37-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="26d37-193">Peer-zu-Peer-Audioanrufe zwischen lync-Endpunkten verwenden entweder RTAudio (8 kHz) oder RTAudio (16kHz), wenn Sie die Bandbreite und Priorisierung von Codecs berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="26d37-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="26d37-194">Telefonkonferenzen zwischen lync-Endpunkten und dem A/V-Konferenzdienst werden entweder G. 722 oder Sirene verwenden.</span><span class="sxs-lookup"><span data-stu-id="26d37-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="26d37-195">Bei Anrufen an das Telefon Festnetz (Public Switched Telephone Network, PSTN) entweder an oder von lync-Endpunkten wird entweder G. 711 oder RTAudio (8 kHz) verwendet.</span><span class="sxs-lookup"><span data-stu-id="26d37-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="26d37-196">Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="26d37-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="26d37-197">Bandbreitenauslastung nach Codec</span><span class="sxs-lookup"><span data-stu-id="26d37-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26d37-198">Codec</span><span class="sxs-lookup"><span data-stu-id="26d37-198">Codec</span></span></th>
<th><span data-ttu-id="26d37-199">Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)</span><span class="sxs-lookup"><span data-stu-id="26d37-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="26d37-200">Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)</span><span class="sxs-lookup"><span data-stu-id="26d37-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26d37-201">RTAudio (8 KHz)</span><span class="sxs-lookup"><span data-stu-id="26d37-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="26d37-202">49,8 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-203">61,6 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-204">RTAudio (16 KHz)</span><span class="sxs-lookup"><span data-stu-id="26d37-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="26d37-205">67 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-206">96 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-207">Sirene</span><span class="sxs-lookup"><span data-stu-id="26d37-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="26d37-208">57,6 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-209">73,6 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-210">G. 711</span><span class="sxs-lookup"><span data-stu-id="26d37-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="26d37-211">102 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-212">166 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-213">G. 722</span><span class="sxs-lookup"><span data-stu-id="26d37-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="26d37-214">105,6 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-215">169,6 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-216">RTVideo (CIF mit 15 F/s)</span><span class="sxs-lookup"><span data-stu-id="26d37-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="26d37-217">260 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-218">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="26d37-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-219">RTVideo (VGA mit 30 F/s)</span><span class="sxs-lookup"><span data-stu-id="26d37-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="26d37-220">610 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-221">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="26d37-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="26d37-p117">Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10 KBit/s für RTCP.</span><span class="sxs-lookup"><span data-stu-id="26d37-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="26d37-224">Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.</span><span class="sxs-lookup"><span data-stu-id="26d37-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="26d37-225">G. 722, der standardmäßige Codec für lync Server Konferenzen, unterscheidet sich vollständig von den Codecs g. 722.1 und Siren.</span><span class="sxs-lookup"><span data-stu-id="26d37-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="26d37-226">Der Siren-Codec wird in den folgenden Situationen in lync Server verwendet:</span><span class="sxs-lookup"><span data-stu-id="26d37-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="26d37-227">Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen</span><span class="sxs-lookup"><span data-stu-id="26d37-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="26d37-228">Wenn ein Communications Server 2007-oder Communications Server 2007 R2-Client eine Verbindung mit einem lync Server-Konferenzdienst herstellt (da diese Clients den G. 722-Codec nicht unterstützen).</span><span class="sxs-lookup"><span data-stu-id="26d37-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="26d37-229">Bandbreitenauslastung nach Szenario</span><span class="sxs-lookup"><span data-stu-id="26d37-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26d37-230">Szenario</span><span class="sxs-lookup"><span data-stu-id="26d37-230">Scenario</span></span></th>
<th><span data-ttu-id="26d37-231">Bandbreitenanforderung für Menge optimiert (KBit/s)</span><span class="sxs-lookup"><span data-stu-id="26d37-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="26d37-232">Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)</span><span class="sxs-lookup"><span data-stu-id="26d37-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="26d37-233">Bandbreitenanforderung für Qualität optimiert (KBit/s)</span><span class="sxs-lookup"><span data-stu-id="26d37-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26d37-234">Peer-zu-Peer-Audioanrufe</span><span class="sxs-lookup"><span data-stu-id="26d37-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="26d37-235">45 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-236">62 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-237">91 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-238">Telefonkonferenz</span><span class="sxs-lookup"><span data-stu-id="26d37-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="26d37-239">53 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-240">101 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-241">165 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-242">PSTN-Anrufe (zwischen lync 2013 und dem PSTN-Gateway, mit medienumgehung)</span><span class="sxs-lookup"><span data-stu-id="26d37-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="26d37-243">97 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-244">97 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-245">161 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-246">PSTN-Anrufe (zwischen lync 2013 und Vermittlungsserver, ohne medienumgehung)</span><span class="sxs-lookup"><span data-stu-id="26d37-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="26d37-247">45 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-248">97 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-249">161 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d37-250">PSTN-Anrufe (zwischen Vermittlungsserver und dem PSTN-Gateway ohne medienumgehung)</span><span class="sxs-lookup"><span data-stu-id="26d37-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="26d37-251">97 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-252">97 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-253">161 KBit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d37-254">Lync-Polycom-Anrufe</span><span class="sxs-lookup"><span data-stu-id="26d37-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="26d37-255">101 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-256">101 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="26d37-257">101 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="26d37-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="26d37-258">Identifizieren von IP-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="26d37-258">Identify IP Subnets</span></span>

<span data-ttu-id="26d37-p118">Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="26d37-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="26d37-p119">Im hier verwendeten Beispiel sind dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" reserviert sind, beispielsweise die Adresse 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="26d37-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="26d37-264">Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="26d37-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="26d37-265">Ein lync-Client nimmt seine lokale IP-Adresse an und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske.</span><span class="sxs-lookup"><span data-stu-id="26d37-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="26d37-266">Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="26d37-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="26d37-267">Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt.</span><span class="sxs-lookup"><span data-stu-id="26d37-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="26d37-268">(Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung selbst dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)</span><span class="sxs-lookup"><span data-stu-id="26d37-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="26d37-269">Wenn sich ein Client beispielsweise auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske 255.255.255.0 anmeldet, fordert lync 2013 die Umgehungs-ID an, die dem Subnetz 172.29.81.0 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="26d37-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="26d37-270">Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht.</span><span class="sxs-lookup"><span data-stu-id="26d37-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="26d37-271">Daher ist es wichtig, dass der Administrator die Subnetze genau so eingibt, wie von lync-Clients bereitgestellt (die bei der Netzwerkkonfiguration entweder statisch oder per DHCP mit Subnetzen bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="26d37-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

