---
title: Beispiel für das Sammeln Ihrer Anforderungen für die Anrufsteuerung
description: Beispiel für das Sammeln Ihrer Anforderungen für die Anrufsteuerung.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564941"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="eead7-103">Beispiel: Sammeln der Anforderungen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eead7-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eead7-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="eead7-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="eead7-p101">Dieses Beispiel führt Sie Schritt für Schritt durch die Planung und Implementierung der Anrufsteuerungsdiensts (Call Admission Control, CAC). Bei diesem Verfahren werden die folgenden allgemeinen Aufgaben ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="eead7-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="eead7-107">Identifizieren aller Netzwerkhubs und Backbones (als *Netzwerkregionen* bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="eead7-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="eead7-108">Identifizieren des lync Server zentralen Standorts, der die Anrufsteuerung für jede netzwerkregion verwalten wird.</span><span class="sxs-lookup"><span data-stu-id="eead7-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="eead7-109">Identifizieren und Definieren der *Netzwerkstandorte*, die mit jeder Netzwerkregion verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="eead7-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="eead7-110">Beschreiben Sie für jeden Netzwerkstandort, dessen Verbindung mit dem WAN Bandbreite eingeschränkt ist, die Bandbreitenkapazität der WAN-Verbindung und die Bandbreitenbeschränkungen, die der Netzwerkadministrator für lync Server Mediendatenverkehr festgelegt hat (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="eead7-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="eead7-111">Standorte mit WAN-Verbindungen ohne Bandbreiteneinschränkung müssen nicht einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="eead7-112">Zuordnen der einzelnen Subnetze in Ihrem Netzwerk zu einem Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="eead7-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="eead7-113">Zuordnen der Verbindungen zwischen den Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="eead7-113">Map the links between the network regions.</span></span> <span data-ttu-id="eead7-114">Beschreiben Sie für jeden Link die Bandbreitenkapazität und alle Beschränkungen, die der Netzwerkadministrator für lync Server Mediendatenverkehr festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="eead7-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="eead7-115">Definieren einer Route zwischen jedem Netzwerkregionenpaar.</span><span class="sxs-lookup"><span data-stu-id="eead7-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="eead7-116">Sammeln der erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="eead7-116">Gather the Required Information</span></span>

<span data-ttu-id="eead7-117">Zur Vorbereitung der Anrufsteuerung müssen Sie die in den folgenden Schritten beschriebenen Informationen sammeln:</span><span class="sxs-lookup"><span data-stu-id="eead7-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="eead7-p104">Identifizieren Sie Ihre Netzwerkregionen. Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.</span><span class="sxs-lookup"><span data-stu-id="eead7-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="eead7-p105">Ein Netzwerkbackbone oder ein Netzwerkhub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="eead7-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="eead7-p106">Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um die Netzwerkregionen für Ihr Unternehmen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="eead7-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="eead7-126">Identifizieren Sie den zentralen Standort, dem jede Netzwerkregion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eead7-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="eead7-127">Ein zentraler Standort enthält mindestens eine Front-End-Server und ist die lync Server-Bereitstellung, die die Anrufsteuerung für den gesamten Mediendatenverkehr verwaltet, der über die WAN-Verbindung der netzwerkregion geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="eead7-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="eead7-128">**Beispielunternehmensnetzwerk mit drei Netzwerkregionen**</span><span class="sxs-lookup"><span data-stu-id="eead7-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="eead7-129">![Beispiel für eine Netzwerktopologie mit drei netzwerkregionen](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Beispiel für eine Netzwerktopologie mit drei netzwerkregionen")</span><span class="sxs-lookup"><span data-stu-id="eead7-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="eead7-130">Ein MPLS-Netzwerk (Multiprotocol Label Switching) sollte als Netzwerkregion abgebildet werden, bei der jeder geografische Standort über einen entsprechenden Netzwerkstandort verfügt.</span><span class="sxs-lookup"><span data-stu-id="eead7-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="eead7-131">Ausführliche Informationen finden Sie im Thema "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Anrufsteuerung für ein MPLS-Netzwerk mit lync Server 2013</A>" in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="eead7-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="eead7-132">In der vorherigen Beispiel Netzwerktopologie gibt es drei netzwerkregionen mit jeweils einem lync Server zentralen Standort, der die Anrufsteuerung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="eead7-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="eead7-133">Der geeignete zentrale Standort für eine Netzwerkregion wird nach geografischer Nähe ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="eead7-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="eead7-134">Da innerhalb der Netzwerkregionen das Aufkommen an Mediendatenverkehr am höchsten ist, führt die Festlegung nach geografischer Nähe zu einer eigenständigen Konfiguration, die auch dann noch funktionsfähig ist, wenn andere zentrale Standorte ausfallen.</span><span class="sxs-lookup"><span data-stu-id="eead7-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="eead7-135">In diesem Beispiel ist eine lync Server-Bereitstellung namens "Chicago" der zentrale Standort für die Region "Nordamerika".</span><span class="sxs-lookup"><span data-stu-id="eead7-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="eead7-136">Alle lync-Benutzer in Nordamerika werden auf Servern in der Bereitstellung von Chicago verwaltet.</span><span class="sxs-lookup"><span data-stu-id="eead7-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="eead7-137">Die folgende Tabelle zeigt die zentralen Standorte für alle drei Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="eead7-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="eead7-138">Netzwerkregionen und zugeordnete zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="eead7-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-139">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="eead7-139">Network Region</span></span></th>
    <th><span data-ttu-id="eead7-140">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="eead7-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-141">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-142">Chicago</span><span class="sxs-lookup"><span data-stu-id="eead7-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="eead7-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="eead7-144">London</span><span class="sxs-lookup"><span data-stu-id="eead7-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-145">APAC</span><span class="sxs-lookup"><span data-stu-id="eead7-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="eead7-146">Peking</span><span class="sxs-lookup"><span data-stu-id="eead7-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="eead7-147">Je nach lync Server Topologie kann derselbe zentrale Standort mehreren netzwerkregionen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="eead7-p111">Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte (Büros oder Zweigstellen), für deren WAN-Verbindungen keine Bandbreiteneinschränkungen gelten. Da diese Standorte keine Bandbreiteneinschränkungen aufweisen, müssen keine Richtlinien für die Anrufsteuerung auf sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="eead7-150">Im Beispiel in der folgenden Tabelle gibt es drei Netzwerkstandorte, deren WAN-Verbindungen keine Bandbreiteneinschränkungen aufweisen: "New York", "Chicago" und "Detroit".</span><span class="sxs-lookup"><span data-stu-id="eead7-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="eead7-151">Netzwerkstandorte ohne Einschränkungen in Bezug auf die WAN-Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-152">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="eead7-152">Network Site</span></span></th>
    <th><span data-ttu-id="eead7-153">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="eead7-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-154">New York</span><span class="sxs-lookup"><span data-stu-id="eead7-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="eead7-155">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-156">Chicago</span><span class="sxs-lookup"><span data-stu-id="eead7-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="eead7-157">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-158">Detroit</span><span class="sxs-lookup"><span data-stu-id="eead7-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="eead7-159">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="eead7-160">Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen eine Verbindung mit der Netzwerkregion herstellen.</span><span class="sxs-lookup"><span data-stu-id="eead7-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="eead7-161">Um die Audio- und Videoqualität besser sicherstellen zu können, wird für diese Netzwerkstandorte mit Bandbreiteneinschränkungen empfohlen, die WAN-Verbindungen zu überwachen und Richtlinien für die Anrufsteuerung anzuwenden, um den Mediendatenverkehr (Sprache oder Video) von und zu der Netzwerkregion zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="eead7-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="eead7-162">Im Beispiel in der folgenden Tabelle sind drei Netzwerkstandorte vorhanden, deren WAN-Bandbreite eingeschränkt ist: "Portland", "Reno" und "Albuquerque".</span><span class="sxs-lookup"><span data-stu-id="eead7-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="eead7-163">Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-164">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="eead7-164">Network Site</span></span></th>
    <th><span data-ttu-id="eead7-165">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="eead7-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-166">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="eead7-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="eead7-167">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-168">Reno</span><span class="sxs-lookup"><span data-stu-id="eead7-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="eead7-169">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-170">Portland</span><span class="sxs-lookup"><span data-stu-id="eead7-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="eead7-171">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="eead7-172">**Anrufsteuerung in der Netzwerkregion "Nordamerika" mit drei Netzwerkstandorten, die keine Bandbreiteneinschränkung aufweisen (Chicago, New York und Detroit), und drei Netzwerkstandorten mit eingeschränkter WAN-Bandbreite (Portland, Reno und Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="eead7-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="eead7-173">![Beispiel für Netzwerkstandorte mit eingeschränkter WAN-Bandbreite](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Beispiel für Netzwerkstandorte mit eingeschränkter WAN-Bandbreite")</span><span class="sxs-lookup"><span data-stu-id="eead7-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="eead7-174">Ermitteln Sie für jede WAN-Verbindung mit eingeschränkter Bandbreite die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="eead7-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="eead7-175">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="eead7-176">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p113">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="eead7-179">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="eead7-180">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p115">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="eead7-183">Netzwerkstandorte mit Informationen zur WAN-Bandbreiteneinschränkung (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="eead7-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-184">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="eead7-184">Network Site</span></span></th>
    <th><span data-ttu-id="eead7-185">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="eead7-185">Network Region</span></span></th>
    <th><span data-ttu-id="eead7-186">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-186">BW Limit</span></span></th>
    <th><span data-ttu-id="eead7-187">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="eead7-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="eead7-188">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="eead7-189">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="eead7-189">Video Limit</span></span></th>
    <th><span data-ttu-id="eead7-190">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-191">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="eead7-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="eead7-192">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-193">5,000</span><span class="sxs-lookup"><span data-stu-id="eead7-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-194">2,000</span><span class="sxs-lookup"><span data-stu-id="eead7-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-195">175</span><span class="sxs-lookup"><span data-stu-id="eead7-195">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-196">1.400</span><span class="sxs-lookup"><span data-stu-id="eead7-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="eead7-197">700</span><span class="sxs-lookup"><span data-stu-id="eead7-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-198">Reno</span><span class="sxs-lookup"><span data-stu-id="eead7-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="eead7-199">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-200">10.000</span><span class="sxs-lookup"><span data-stu-id="eead7-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-201">4.000</span><span class="sxs-lookup"><span data-stu-id="eead7-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-202">175</span><span class="sxs-lookup"><span data-stu-id="eead7-202">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-203">2.800</span><span class="sxs-lookup"><span data-stu-id="eead7-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="eead7-204">700</span><span class="sxs-lookup"><span data-stu-id="eead7-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-205">Portland</span><span class="sxs-lookup"><span data-stu-id="eead7-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="eead7-206">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-207">5,000</span><span class="sxs-lookup"><span data-stu-id="eead7-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-208">4.000</span><span class="sxs-lookup"><span data-stu-id="eead7-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-209">175</span><span class="sxs-lookup"><span data-stu-id="eead7-209">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-210">2.800</span><span class="sxs-lookup"><span data-stu-id="eead7-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="eead7-211">700</span><span class="sxs-lookup"><span data-stu-id="eead7-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-212">New York</span><span class="sxs-lookup"><span data-stu-id="eead7-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="eead7-213">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-214">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-215">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-216">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-217">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-218">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-219">Chicago</span><span class="sxs-lookup"><span data-stu-id="eead7-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="eead7-220">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-221">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-222">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-223">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-224">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-225">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-226">Detroit</span><span class="sxs-lookup"><span data-stu-id="eead7-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="eead7-227">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-228">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-229">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-230">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-231">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-232">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="eead7-233">Geben Sie für jedes Subnetz in Ihrem Netzwerk den zugeordneten Netzwerkstandort an.</span><span class="sxs-lookup"><span data-stu-id="eead7-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="eead7-p116">Jedes Subnetz in Ihrem Netzwerk muss einem Netzwerkstandort zugeordnet sein – selbst dann, wenn für den Netzwerkstandort keine Bandbreiteneinschränkungen gelten. Diese Anforderung gilt, da die Anrufsteuerung mithilfe von Subnetzinformationen ermittelt, an welchem Netzwerkstandort sich ein Endpunkt befindet. Wenn die Standorte beider Sitzungsteilnehmer ermittelt wurden, kann über die Anrufsteuerung festgestellt werden, ob genügend Bandbreite für einen Anruf vorhanden ist. Wird eine Sitzung über eine Verbindung ohne Bandbreiteneinschränkungen hergestellt, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="eead7-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="eead7-238">Wenn Sie A/V-Edgeserver (Audio/Video) bereitstellen, müssen die öffentlichen IP-Adressen der jeweiligen Edgeserver dem Netzwerkstandort zugeordnet werden, in dem der Edgeserver bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="eead7-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="eead7-239">Jede öffentliche IP-Adresse des A/V-Edgeservers muss in den Netzwerkkonfigurationseinstellungen als Subnetz mit der Subnetzmaske 32 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="eead7-240">Wenn Sie beispielsweise A/V-Edgeserver in Chicago bereitstellen, müssen Sie für jede externe IP-Adresse dieser Server ein Subnetz mit der Subnetzmaske 32 erstellen und Netzwerkstandort "Chicago" diesen Subnetzen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="eead7-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="eead7-241">Ausführliche Informationen zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="eead7-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="eead7-p118">Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von 8 Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eead7-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="eead7-245"><STRONG>Quelle:</STRONG> CS Bandwidth Policy Service (Kern)</span><span class="sxs-lookup"><span data-stu-id="eead7-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="eead7-246"><STRONG>Ereignisnummer:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="eead7-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="eead7-247"><STRONG>Ebene:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="eead7-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="eead7-248"><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP-Adressen: &lt; Liste der IP-Adressen &gt; sind entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="eead7-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="eead7-249"><STRONG>Ursache:</STRONG> Die Subnetze für die entsprechenden IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="eead7-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="eead7-250"><STRONG>Lösung:</STRONG> Fügen Sie den Netzwerkkonfigurationseinstellungen Subnetze hinzu, die der vorherigen Liste der IP-Adressen entsprechen, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.</span><span class="sxs-lookup"><span data-stu-id="eead7-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="eead7-p119">Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:</span><span class="sxs-lookup"><span data-stu-id="eead7-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="eead7-253">Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eead7-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eead7-254">Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="eead7-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="eead7-255">Netzwerkstandorte und zugeordnete Subnetze (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="eead7-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-256">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="eead7-256">Network Site</span></span></th>
    <th><span data-ttu-id="eead7-257">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="eead7-257">Network Region</span></span></th>
    <th><span data-ttu-id="eead7-258">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-258">BW Limit</span></span></th>
    <th><span data-ttu-id="eead7-259">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="eead7-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="eead7-260">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="eead7-261">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="eead7-261">Video Limit</span></span></th>
    <th><span data-ttu-id="eead7-262">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="eead7-263">Subnetze</span><span class="sxs-lookup"><span data-stu-id="eead7-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-264">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="eead7-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="eead7-265">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-266">5,000</span><span class="sxs-lookup"><span data-stu-id="eead7-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-267">2,000</span><span class="sxs-lookup"><span data-stu-id="eead7-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-268">175</span><span class="sxs-lookup"><span data-stu-id="eead7-268">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-269">1.400</span><span class="sxs-lookup"><span data-stu-id="eead7-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="eead7-270">700</span><span class="sxs-lookup"><span data-stu-id="eead7-270">700</span></span></p></td>
    <td><p><span data-ttu-id="eead7-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="eead7-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-272">Reno</span><span class="sxs-lookup"><span data-stu-id="eead7-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="eead7-273">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-274">10.000</span><span class="sxs-lookup"><span data-stu-id="eead7-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-275">4.000</span><span class="sxs-lookup"><span data-stu-id="eead7-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-276">175</span><span class="sxs-lookup"><span data-stu-id="eead7-276">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-277">2.800</span><span class="sxs-lookup"><span data-stu-id="eead7-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="eead7-278">700</span><span class="sxs-lookup"><span data-stu-id="eead7-278">700</span></span></p></td>
    <td><p><span data-ttu-id="eead7-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="eead7-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-280">Portland</span><span class="sxs-lookup"><span data-stu-id="eead7-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="eead7-281">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-282">5,000</span><span class="sxs-lookup"><span data-stu-id="eead7-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-283">4.000</span><span class="sxs-lookup"><span data-stu-id="eead7-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-284">175</span><span class="sxs-lookup"><span data-stu-id="eead7-284">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-285">2.800</span><span class="sxs-lookup"><span data-stu-id="eead7-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="eead7-286">700</span><span class="sxs-lookup"><span data-stu-id="eead7-286">700</span></span></p></td>
    <td><p><span data-ttu-id="eead7-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="eead7-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-288">New York</span><span class="sxs-lookup"><span data-stu-id="eead7-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="eead7-289">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-290">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-291">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-292">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-293">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-294">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="eead7-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-296">Chicago</span><span class="sxs-lookup"><span data-stu-id="eead7-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="eead7-297">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-298">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-299">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-300">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-301">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-302">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="eead7-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-304">Detroit</span><span class="sxs-lookup"><span data-stu-id="eead7-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="eead7-305">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-306">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-307">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-308">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-309">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-310">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="eead7-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="eead7-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="eead7-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="eead7-312">In lync Server Anrufsteuerung werden die Verbindungen zwischen netzwerkregionen als *Regions Verknüpfungen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="eead7-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="eead7-313">Ermitteln Sie für jede Regionenverbindung, ebenso wie für die Netzwerkstandorte, die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="eead7-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="eead7-314">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="eead7-315">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p122">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="eead7-318">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="eead7-319">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p124">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="eead7-322">**Netzwerkregionenverbindungen mit zugehörigen Bandbreiteneinschränkungen**</span><span class="sxs-lookup"><span data-stu-id="eead7-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="eead7-323">![Beispiel für Einschränkungen zwischen drei Regionen](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Beispiel für Einschränkungen zwischen drei Regionen")</span><span class="sxs-lookup"><span data-stu-id="eead7-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="eead7-324">Bandbreiteninformationen zu Regionenverbindungen (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="eead7-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-325">Name der Regionenverbindung</span><span class="sxs-lookup"><span data-stu-id="eead7-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="eead7-326">Erste Region</span><span class="sxs-lookup"><span data-stu-id="eead7-326">First Region</span></span></th>
    <th><span data-ttu-id="eead7-327">Zweite Region</span><span class="sxs-lookup"><span data-stu-id="eead7-327">Second Region</span></span></th>
    <th><span data-ttu-id="eead7-328">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-328">BW Limit</span></span></th>
    <th><span data-ttu-id="eead7-329">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="eead7-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="eead7-330">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="eead7-331">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="eead7-331">Video Limit</span></span></th>
    <th><span data-ttu-id="eead7-332">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-333">Na-EMEA-Link</span><span class="sxs-lookup"><span data-stu-id="eead7-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="eead7-334">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="eead7-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="eead7-336">50.000</span><span class="sxs-lookup"><span data-stu-id="eead7-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-337">20,000</span><span class="sxs-lookup"><span data-stu-id="eead7-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-338">175</span><span class="sxs-lookup"><span data-stu-id="eead7-338">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-339">14.000</span><span class="sxs-lookup"><span data-stu-id="eead7-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-340">700</span><span class="sxs-lookup"><span data-stu-id="eead7-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-341">EMEA-APAC-Link</span><span class="sxs-lookup"><span data-stu-id="eead7-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="eead7-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="eead7-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="eead7-343">APAC</span><span class="sxs-lookup"><span data-stu-id="eead7-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="eead7-344">25.000</span><span class="sxs-lookup"><span data-stu-id="eead7-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-345">10.000</span><span class="sxs-lookup"><span data-stu-id="eead7-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-346">175</span><span class="sxs-lookup"><span data-stu-id="eead7-346">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-347">7.000</span><span class="sxs-lookup"><span data-stu-id="eead7-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-348">700</span><span class="sxs-lookup"><span data-stu-id="eead7-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="eead7-349">Definieren einer Route zwischen jedem Netzwerkregionenpaar.</span><span class="sxs-lookup"><span data-stu-id="eead7-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="eead7-350">Für die Route zwischen den Regionen "Nordamerika" und "APAC" sind zwei Verbindungen erforderlich, da keine Region vorhanden ist, die die Regionen direkt miteinander verbindet.</span><span class="sxs-lookup"><span data-stu-id="eead7-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="eead7-351">Routen zwischen Regionen</span><span class="sxs-lookup"><span data-stu-id="eead7-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-352">Name der Regionenroute</span><span class="sxs-lookup"><span data-stu-id="eead7-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="eead7-353">Erste Region</span><span class="sxs-lookup"><span data-stu-id="eead7-353">First Region</span></span></th>
    <th><span data-ttu-id="eead7-354">Zweite Region</span><span class="sxs-lookup"><span data-stu-id="eead7-354">Second Region</span></span></th>
    <th><span data-ttu-id="eead7-355">Regionenverbindungen</span><span class="sxs-lookup"><span data-stu-id="eead7-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-356">Na-EMEA-Route</span><span class="sxs-lookup"><span data-stu-id="eead7-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="eead7-357">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="eead7-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="eead7-359">Na-EMEA-Link</span><span class="sxs-lookup"><span data-stu-id="eead7-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eead7-360">EMEA-APAC-Route</span><span class="sxs-lookup"><span data-stu-id="eead7-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="eead7-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="eead7-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="eead7-362">APAC</span><span class="sxs-lookup"><span data-stu-id="eead7-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="eead7-363">EMEA-APAC-Link</span><span class="sxs-lookup"><span data-stu-id="eead7-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-364">Na-APAC-Route</span><span class="sxs-lookup"><span data-stu-id="eead7-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="eead7-365">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="eead7-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="eead7-366">APAC</span><span class="sxs-lookup"><span data-stu-id="eead7-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="eead7-367">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="eead7-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="eead7-368">Ermitteln Sie für jedes Netzwerkstandortpaar, das durch eine einzelne Verbindung direkt miteinander verbunden wird (als *standortübergreifende* Verbindung bezeichnet), die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="eead7-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="eead7-369">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="eead7-370">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p126">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="eead7-373">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="eead7-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="eead7-374">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="eead7-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="eead7-p128">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eead7-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="eead7-377">**Anrufsteuerung in der Netzwerkregion "Nordamerika" mit Anzeige der Bandbreitenkapazitäten und -einschränkungen für die standortübergreifende Verbindung zwischen Reno und Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="eead7-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="eead7-378">![Netzwerkstandorte mit eingeschränkter WAN-Bandbreite (Beispiel)](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Netzwerkstandorte mit eingeschränkter WAN-Bandbreite (Beispiel)")</span><span class="sxs-lookup"><span data-stu-id="eead7-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="eead7-379">Bandbreiteninformationen für eine standortübergreifende Verbindung zwischen zwei Netzwerkstandorten (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="eead7-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eead7-380">Name der standortübergreifenden Verbindung</span><span class="sxs-lookup"><span data-stu-id="eead7-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="eead7-381">Erster Standort</span><span class="sxs-lookup"><span data-stu-id="eead7-381">First Site</span></span></th>
    <th><span data-ttu-id="eead7-382">Zweiter Standort</span><span class="sxs-lookup"><span data-stu-id="eead7-382">Second Site</span></span></th>
    <th><span data-ttu-id="eead7-383">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="eead7-383">BW Limit</span></span></th>
    <th><span data-ttu-id="eead7-384">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="eead7-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="eead7-385">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="eead7-386">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="eead7-386">Video Limit</span></span></th>
    <th><span data-ttu-id="eead7-387">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="eead7-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eead7-388">Reno-Albu-standortübergreifendes Link</span><span class="sxs-lookup"><span data-stu-id="eead7-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="eead7-389">Reno</span><span class="sxs-lookup"><span data-stu-id="eead7-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="eead7-390">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="eead7-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="eead7-391">20,000</span><span class="sxs-lookup"><span data-stu-id="eead7-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-392">12.000</span><span class="sxs-lookup"><span data-stu-id="eead7-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-393">175</span><span class="sxs-lookup"><span data-stu-id="eead7-393">175</span></span></p></td>
    <td><p><span data-ttu-id="eead7-394">5,000</span><span class="sxs-lookup"><span data-stu-id="eead7-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="eead7-395">700</span><span class="sxs-lookup"><span data-stu-id="eead7-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="eead7-396">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="eead7-396">Next Steps</span></span>

<span data-ttu-id="eead7-397">Nachdem Sie die erforderlichen Informationen gesammelt haben, können Sie die Bereitstellung der Anrufsteuerung mithilfe der lync Server-Verwaltungsshell oder der lync Server-Systemsteuerung durchführen.</span><span class="sxs-lookup"><span data-stu-id="eead7-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="eead7-398">Obwohl Sie die meisten Netzwerk Konfigurationsaufgaben mithilfe von lync Server-Systemsteuerung ausführen können, müssen Sie lync Server-Verwaltungsshell verwenden, um Subnetze und standortübergreifende Links zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eead7-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="eead7-399">Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation zum Cmdlet <STRONG>New-CsNetworkSubnet</STRONG> und im Cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="eead7-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

