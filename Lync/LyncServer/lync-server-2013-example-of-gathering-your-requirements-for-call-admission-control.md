---
title: Beispiel für das Sammeln Ihrer Anforderungen für die Anrufsteuerung
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
ms.openlocfilehash: 46e0b0a294500514ce1b200fd646ed4e70136828
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="73faf-102">Beispiel: Sammeln der Anforderungen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73faf-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73faf-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="73faf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="73faf-p101">Dieses Beispiel führt Sie Schritt für Schritt durch die Planung und Implementierung der Anrufsteuerungsdiensts (Call Admission Control, CAC). Bei diesem Verfahren werden die folgenden allgemeinen Aufgaben ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="73faf-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="73faf-106">Identifizieren aller Netzwerkhubs und Backbones (als *Netzwerkregionen* bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="73faf-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="73faf-107">Identifizieren des lync Server zentralen Standorts, der die Anrufsteuerung für jede netzwerkregion verwalten wird.</span><span class="sxs-lookup"><span data-stu-id="73faf-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="73faf-108">Identifizieren und Definieren der *Netzwerkstandorte*, die mit jeder Netzwerkregion verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="73faf-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="73faf-109">Beschreiben Sie für jeden Netzwerkstandort, dessen Verbindung mit dem WAN Bandbreite eingeschränkt ist, die Bandbreitenkapazität der WAN-Verbindung und die Bandbreitenbeschränkungen, die der Netzwerkadministrator für lync Server Mediendatenverkehr festgelegt hat (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="73faf-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="73faf-110">Standorte mit WAN-Verbindungen ohne Bandbreiteneinschränkung müssen nicht einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="73faf-111">Zuordnen der einzelnen Subnetze in Ihrem Netzwerk zu einem Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="73faf-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="73faf-112">Zuordnen der Verbindungen zwischen den Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="73faf-112">Map the links between the network regions.</span></span> <span data-ttu-id="73faf-113">Beschreiben Sie für jeden Link die Bandbreitenkapazität und alle Beschränkungen, die der Netzwerkadministrator für lync Server Mediendatenverkehr festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="73faf-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="73faf-114">Definieren einer Route zwischen jedem Netzwerkregionenpaar.</span><span class="sxs-lookup"><span data-stu-id="73faf-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="73faf-115">Sammeln der erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="73faf-115">Gather the Required Information</span></span>

<span data-ttu-id="73faf-116">Zur Vorbereitung der Anrufsteuerung müssen Sie die in den folgenden Schritten beschriebenen Informationen sammeln:</span><span class="sxs-lookup"><span data-stu-id="73faf-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="73faf-p104">Identifizieren Sie Ihre Netzwerkregionen. Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.</span><span class="sxs-lookup"><span data-stu-id="73faf-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="73faf-p105">Ein Netzwerkbackbone oder ein Netzwerkhub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="73faf-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="73faf-p106">Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um die Netzwerkregionen für Ihr Unternehmen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="73faf-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="73faf-125">Identifizieren Sie den zentralen Standort, dem jede Netzwerkregion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="73faf-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="73faf-126">Ein zentraler Standort enthält mindestens eine Front-End-Server und ist die lync Server-Bereitstellung, die die Anrufsteuerung für den gesamten Mediendatenverkehr verwaltet, der über die WAN-Verbindung der netzwerkregion geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="73faf-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="73faf-127">**Beispielunternehmensnetzwerk mit drei Netzwerkregionen**</span><span class="sxs-lookup"><span data-stu-id="73faf-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="73faf-128">![Beispiel für eine Netzwerktopologie mit drei netzwerkregionen](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Beispiel für eine Netzwerktopologie mit drei netzwerkregionen")</span><span class="sxs-lookup"><span data-stu-id="73faf-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="73faf-129">Ein MPLS-Netzwerk (Multiprotocol Label Switching) sollte als Netzwerkregion abgebildet werden, bei der jeder geografische Standort über einen entsprechenden Netzwerkstandort verfügt.</span><span class="sxs-lookup"><span data-stu-id="73faf-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="73faf-130">Ausführliche Informationen finden Sie im Thema "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Anrufsteuerung für ein MPLS-Netzwerk mit lync Server 2013</A>" in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="73faf-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="73faf-131">In der vorherigen Beispiel Netzwerktopologie gibt es drei netzwerkregionen mit jeweils einem lync Server zentralen Standort, der die Anrufsteuerung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="73faf-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="73faf-132">Der geeignete zentrale Standort für eine Netzwerkregion wird nach geografischer Nähe ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="73faf-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="73faf-133">Da innerhalb der Netzwerkregionen das Aufkommen an Mediendatenverkehr am höchsten ist, führt die Festlegung nach geografischer Nähe zu einer eigenständigen Konfiguration, die auch dann noch funktionsfähig ist, wenn andere zentrale Standorte ausfallen.</span><span class="sxs-lookup"><span data-stu-id="73faf-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="73faf-134">In diesem Beispiel ist eine lync Server-Bereitstellung namens "Chicago" der zentrale Standort für die Region "Nordamerika".</span><span class="sxs-lookup"><span data-stu-id="73faf-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="73faf-135">Alle lync-Benutzer in Nordamerika werden auf Servern in der Bereitstellung von Chicago verwaltet.</span><span class="sxs-lookup"><span data-stu-id="73faf-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="73faf-136">Die folgende Tabelle zeigt die zentralen Standorte für alle drei Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="73faf-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="73faf-137">Netzwerkregionen und zugeordnete zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="73faf-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="73faf-138">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="73faf-138">Network Region</span></span></th>
    <th><span data-ttu-id="73faf-139">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="73faf-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-140">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-141">Chicago</span><span class="sxs-lookup"><span data-stu-id="73faf-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="73faf-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="73faf-143">London</span><span class="sxs-lookup"><span data-stu-id="73faf-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-144">APAC</span><span class="sxs-lookup"><span data-stu-id="73faf-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="73faf-145">Peking</span><span class="sxs-lookup"><span data-stu-id="73faf-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="73faf-146">Je nach lync Server Topologie kann derselbe zentrale Standort mehreren netzwerkregionen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="73faf-p111">Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte (Büros oder Zweigstellen), für deren WAN-Verbindungen keine Bandbreiteneinschränkungen gelten. Da diese Standorte keine Bandbreiteneinschränkungen aufweisen, müssen keine Richtlinien für die Anrufsteuerung auf sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="73faf-149">Im Beispiel in der folgenden Tabelle gibt es drei Netzwerkstandorte, deren WAN-Verbindungen keine Bandbreiteneinschränkungen aufweisen: "New York", "Chicago" und "Detroit".</span><span class="sxs-lookup"><span data-stu-id="73faf-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="73faf-150">Netzwerkstandorte ohne Einschränkungen in Bezug auf die WAN-Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="73faf-151">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="73faf-151">Network Site</span></span></th>
    <th><span data-ttu-id="73faf-152">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="73faf-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-153">New York</span><span class="sxs-lookup"><span data-stu-id="73faf-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="73faf-154">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-155">Chicago</span><span class="sxs-lookup"><span data-stu-id="73faf-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="73faf-156">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-157">Detroit</span><span class="sxs-lookup"><span data-stu-id="73faf-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="73faf-158">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="73faf-159">Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen eine Verbindung mit der Netzwerkregion herstellen.</span><span class="sxs-lookup"><span data-stu-id="73faf-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="73faf-160">Um die Audio- und Videoqualität besser sicherstellen zu können, wird für diese Netzwerkstandorte mit Bandbreiteneinschränkungen empfohlen, die WAN-Verbindungen zu überwachen und Richtlinien für die Anrufsteuerung anzuwenden, um den Mediendatenverkehr (Sprache oder Video) von und zu der Netzwerkregion zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="73faf-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="73faf-161">Im Beispiel in der folgenden Tabelle sind drei Netzwerkstandorte vorhanden, deren WAN-Bandbreite eingeschränkt ist: "Portland", "Reno" und "Albuquerque".</span><span class="sxs-lookup"><span data-stu-id="73faf-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="73faf-162">Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="73faf-163">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="73faf-163">Network Site</span></span></th>
    <th><span data-ttu-id="73faf-164">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="73faf-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="73faf-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="73faf-166">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-167">Reno</span><span class="sxs-lookup"><span data-stu-id="73faf-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="73faf-168">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-169">Portland</span><span class="sxs-lookup"><span data-stu-id="73faf-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="73faf-170">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="73faf-171">**Anrufsteuerung in der Netzwerkregion "Nordamerika" mit drei Netzwerkstandorten, die keine Bandbreiteneinschränkung aufweisen (Chicago, New York und Detroit), und drei Netzwerkstandorten mit eingeschränkter WAN-Bandbreite (Portland, Reno und Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="73faf-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="73faf-172">![Beispiel für Netzwerkstandorte mit eingeschränkter WAN-Bandbreite](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Beispiel für Netzwerkstandorte mit eingeschränkter WAN-Bandbreite")</span><span class="sxs-lookup"><span data-stu-id="73faf-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="73faf-173">Ermitteln Sie für jede WAN-Verbindung mit eingeschränkter Bandbreite die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="73faf-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="73faf-174">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="73faf-175">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p113">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="73faf-178">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="73faf-179">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p115">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="73faf-182">Netzwerkstandorte mit Informationen zur WAN-Bandbreiteneinschränkung (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="73faf-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="73faf-183">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="73faf-183">Network Site</span></span></th>
    <th><span data-ttu-id="73faf-184">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="73faf-184">Network Region</span></span></th>
    <th><span data-ttu-id="73faf-185">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-185">BW Limit</span></span></th>
    <th><span data-ttu-id="73faf-186">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="73faf-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="73faf-187">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="73faf-188">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="73faf-188">Video Limit</span></span></th>
    <th><span data-ttu-id="73faf-189">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="73faf-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="73faf-191">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-192">5,000</span><span class="sxs-lookup"><span data-stu-id="73faf-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-193">2,000</span><span class="sxs-lookup"><span data-stu-id="73faf-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-194">175</span><span class="sxs-lookup"><span data-stu-id="73faf-194">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-195">1.400</span><span class="sxs-lookup"><span data-stu-id="73faf-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="73faf-196">700</span><span class="sxs-lookup"><span data-stu-id="73faf-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-197">Reno</span><span class="sxs-lookup"><span data-stu-id="73faf-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="73faf-198">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-199">10.000</span><span class="sxs-lookup"><span data-stu-id="73faf-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-200">4.000</span><span class="sxs-lookup"><span data-stu-id="73faf-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-201">175</span><span class="sxs-lookup"><span data-stu-id="73faf-201">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-202">2.800</span><span class="sxs-lookup"><span data-stu-id="73faf-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="73faf-203">700</span><span class="sxs-lookup"><span data-stu-id="73faf-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-204">Portland</span><span class="sxs-lookup"><span data-stu-id="73faf-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="73faf-205">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-206">5,000</span><span class="sxs-lookup"><span data-stu-id="73faf-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-207">4.000</span><span class="sxs-lookup"><span data-stu-id="73faf-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-208">175</span><span class="sxs-lookup"><span data-stu-id="73faf-208">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-209">2.800</span><span class="sxs-lookup"><span data-stu-id="73faf-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="73faf-210">700</span><span class="sxs-lookup"><span data-stu-id="73faf-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-211">New York</span><span class="sxs-lookup"><span data-stu-id="73faf-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="73faf-212">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-213">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-214">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-215">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-216">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-217">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-218">Chicago</span><span class="sxs-lookup"><span data-stu-id="73faf-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="73faf-219">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-220">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-221">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-222">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-223">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-224">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-225">Detroit</span><span class="sxs-lookup"><span data-stu-id="73faf-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="73faf-226">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-227">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-228">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-229">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-230">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-231">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="73faf-232">Geben Sie für jedes Subnetz in Ihrem Netzwerk den zugeordneten Netzwerkstandort an.</span><span class="sxs-lookup"><span data-stu-id="73faf-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="73faf-p116">Jedes Subnetz in Ihrem Netzwerk muss einem Netzwerkstandort zugeordnet sein – selbst dann, wenn für den Netzwerkstandort keine Bandbreiteneinschränkungen gelten. Diese Anforderung gilt, da die Anrufsteuerung mithilfe von Subnetzinformationen ermittelt, an welchem Netzwerkstandort sich ein Endpunkt befindet. Wenn die Standorte beider Sitzungsteilnehmer ermittelt wurden, kann über die Anrufsteuerung festgestellt werden, ob genügend Bandbreite für einen Anruf vorhanden ist. Wird eine Sitzung über eine Verbindung ohne Bandbreiteneinschränkungen hergestellt, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="73faf-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="73faf-237">Wenn Sie A/V-Edgeserver (Audio/Video) bereitstellen, müssen die öffentlichen IP-Adressen der jeweiligen Edgeserver dem Netzwerkstandort zugeordnet werden, in dem der Edgeserver bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="73faf-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="73faf-238">Jede öffentliche IP-Adresse des A/V-Edgeservers muss in den Netzwerkkonfigurationseinstellungen als Subnetz mit der Subnetzmaske 32 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="73faf-239">Wenn Sie beispielsweise A/V-Edgeserver in Chicago bereitstellen, müssen Sie für jede externe IP-Adresse dieser Server ein Subnetz mit der Subnetzmaske 32 erstellen und Netzwerkstandort "Chicago" diesen Subnetzen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="73faf-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="73faf-240">Ausführliche Informationen zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="73faf-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="73faf-p118">Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von 8 Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73faf-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="73faf-244"><STRONG>Quelle:</STRONG> CS Bandwidth Policy Service (Kern)</span><span class="sxs-lookup"><span data-stu-id="73faf-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="73faf-245"><STRONG>Ereignisnummer:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="73faf-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="73faf-246"><STRONG>Ebene:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="73faf-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="73faf-247"><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP- &lt;Adressen: Liste der&gt; IP-Adressen sind entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73faf-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="73faf-248"><STRONG>Ursache:</STRONG> Die Subnetze für die entsprechenden IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73faf-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="73faf-249"><STRONG>Lösung:</STRONG> Fügen Sie den Netzwerkkonfigurationseinstellungen Subnetze hinzu, die der vorherigen Liste der IP-Adressen entsprechen, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.</span><span class="sxs-lookup"><span data-stu-id="73faf-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="73faf-p119">Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:</span><span class="sxs-lookup"><span data-stu-id="73faf-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="73faf-252">Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="73faf-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="73faf-253">Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="73faf-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="73faf-254">Netzwerkstandorte und zugeordnete Subnetze (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="73faf-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="73faf-255">Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="73faf-255">Network Site</span></span></th>
    <th><span data-ttu-id="73faf-256">Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="73faf-256">Network Region</span></span></th>
    <th><span data-ttu-id="73faf-257">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-257">BW Limit</span></span></th>
    <th><span data-ttu-id="73faf-258">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="73faf-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="73faf-259">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="73faf-260">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="73faf-260">Video Limit</span></span></th>
    <th><span data-ttu-id="73faf-261">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="73faf-262">Subnetze</span><span class="sxs-lookup"><span data-stu-id="73faf-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="73faf-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="73faf-264">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-265">5,000</span><span class="sxs-lookup"><span data-stu-id="73faf-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-266">2,000</span><span class="sxs-lookup"><span data-stu-id="73faf-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-267">175</span><span class="sxs-lookup"><span data-stu-id="73faf-267">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-268">1.400</span><span class="sxs-lookup"><span data-stu-id="73faf-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="73faf-269">700</span><span class="sxs-lookup"><span data-stu-id="73faf-269">700</span></span></p></td>
    <td><p><span data-ttu-id="73faf-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="73faf-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-271">Reno</span><span class="sxs-lookup"><span data-stu-id="73faf-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="73faf-272">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-273">10.000</span><span class="sxs-lookup"><span data-stu-id="73faf-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-274">4.000</span><span class="sxs-lookup"><span data-stu-id="73faf-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-275">175</span><span class="sxs-lookup"><span data-stu-id="73faf-275">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-276">2.800</span><span class="sxs-lookup"><span data-stu-id="73faf-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="73faf-277">700</span><span class="sxs-lookup"><span data-stu-id="73faf-277">700</span></span></p></td>
    <td><p><span data-ttu-id="73faf-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="73faf-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-279">Portland</span><span class="sxs-lookup"><span data-stu-id="73faf-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="73faf-280">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-281">5,000</span><span class="sxs-lookup"><span data-stu-id="73faf-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-282">4.000</span><span class="sxs-lookup"><span data-stu-id="73faf-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-283">175</span><span class="sxs-lookup"><span data-stu-id="73faf-283">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-284">2.800</span><span class="sxs-lookup"><span data-stu-id="73faf-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="73faf-285">700</span><span class="sxs-lookup"><span data-stu-id="73faf-285">700</span></span></p></td>
    <td><p><span data-ttu-id="73faf-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="73faf-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-287">New York</span><span class="sxs-lookup"><span data-stu-id="73faf-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="73faf-288">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-289">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-290">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-291">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-292">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-293">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="73faf-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-295">Chicago</span><span class="sxs-lookup"><span data-stu-id="73faf-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="73faf-296">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-297">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-298">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-299">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-300">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-301">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="73faf-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-303">Detroit</span><span class="sxs-lookup"><span data-stu-id="73faf-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="73faf-304">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-305">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-306">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-307">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-308">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-309">(keine Begrenzung)</span><span class="sxs-lookup"><span data-stu-id="73faf-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="73faf-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="73faf-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="73faf-311">In lync Server Anrufsteuerung werden die Verbindungen zwischen netzwerkregionen als *Regions Verknüpfungen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="73faf-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="73faf-312">Ermitteln Sie für jede Regionenverbindung, ebenso wie für die Netzwerkstandorte, die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="73faf-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="73faf-313">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="73faf-314">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p122">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="73faf-317">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="73faf-318">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p124">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="73faf-321">**Netzwerkregionenverbindungen mit zugehörigen Bandbreiteneinschränkungen**</span><span class="sxs-lookup"><span data-stu-id="73faf-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="73faf-322">![Beispiel für Einschränkungen zwischen drei Regionen](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Beispiel für Einschränkungen zwischen drei Regionen")</span><span class="sxs-lookup"><span data-stu-id="73faf-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="73faf-323">Bandbreiteninformationen zu Regionenverbindungen (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="73faf-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="73faf-324">Name der Regionenverbindung</span><span class="sxs-lookup"><span data-stu-id="73faf-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="73faf-325">Erste Region</span><span class="sxs-lookup"><span data-stu-id="73faf-325">First Region</span></span></th>
    <th><span data-ttu-id="73faf-326">Zweite Region</span><span class="sxs-lookup"><span data-stu-id="73faf-326">Second Region</span></span></th>
    <th><span data-ttu-id="73faf-327">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-327">BW Limit</span></span></th>
    <th><span data-ttu-id="73faf-328">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="73faf-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="73faf-329">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="73faf-330">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="73faf-330">Video Limit</span></span></th>
    <th><span data-ttu-id="73faf-331">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-332">Na-EMEA-Link</span><span class="sxs-lookup"><span data-stu-id="73faf-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="73faf-333">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="73faf-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="73faf-335">50.000</span><span class="sxs-lookup"><span data-stu-id="73faf-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-336">20,000</span><span class="sxs-lookup"><span data-stu-id="73faf-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-337">175</span><span class="sxs-lookup"><span data-stu-id="73faf-337">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-338">14.000</span><span class="sxs-lookup"><span data-stu-id="73faf-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-339">700</span><span class="sxs-lookup"><span data-stu-id="73faf-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-340">EMEA-APAC-Link</span><span class="sxs-lookup"><span data-stu-id="73faf-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="73faf-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="73faf-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="73faf-342">APAC</span><span class="sxs-lookup"><span data-stu-id="73faf-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="73faf-343">25.000</span><span class="sxs-lookup"><span data-stu-id="73faf-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-344">10.000</span><span class="sxs-lookup"><span data-stu-id="73faf-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-345">175</span><span class="sxs-lookup"><span data-stu-id="73faf-345">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-346">7.000</span><span class="sxs-lookup"><span data-stu-id="73faf-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-347">700</span><span class="sxs-lookup"><span data-stu-id="73faf-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="73faf-348">Definieren einer Route zwischen jedem Netzwerkregionenpaar.</span><span class="sxs-lookup"><span data-stu-id="73faf-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="73faf-349">Für die Route zwischen den Regionen "Nordamerika" und "APAC" sind zwei Verbindungen erforderlich, da keine Region vorhanden ist, die die Regionen direkt miteinander verbindet.</span><span class="sxs-lookup"><span data-stu-id="73faf-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="73faf-350">Routen zwischen Regionen</span><span class="sxs-lookup"><span data-stu-id="73faf-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="73faf-351">Name der Regionenroute</span><span class="sxs-lookup"><span data-stu-id="73faf-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="73faf-352">Erste Region</span><span class="sxs-lookup"><span data-stu-id="73faf-352">First Region</span></span></th>
    <th><span data-ttu-id="73faf-353">Zweite Region</span><span class="sxs-lookup"><span data-stu-id="73faf-353">Second Region</span></span></th>
    <th><span data-ttu-id="73faf-354">Regionenverbindungen</span><span class="sxs-lookup"><span data-stu-id="73faf-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-355">Na-EMEA-Route</span><span class="sxs-lookup"><span data-stu-id="73faf-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="73faf-356">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="73faf-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="73faf-358">Na-EMEA-Link</span><span class="sxs-lookup"><span data-stu-id="73faf-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="73faf-359">EMEA-APAC-Route</span><span class="sxs-lookup"><span data-stu-id="73faf-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="73faf-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="73faf-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="73faf-361">APAC</span><span class="sxs-lookup"><span data-stu-id="73faf-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="73faf-362">EMEA-APAC-Link</span><span class="sxs-lookup"><span data-stu-id="73faf-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-363">Na-APAC-Route</span><span class="sxs-lookup"><span data-stu-id="73faf-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="73faf-364">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="73faf-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="73faf-365">APAC</span><span class="sxs-lookup"><span data-stu-id="73faf-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="73faf-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="73faf-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="73faf-367">Ermitteln Sie für jedes Netzwerkstandortpaar, das durch eine einzelne Verbindung direkt miteinander verbunden wird (als *standortübergreifende* Verbindung bezeichnet), die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="73faf-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="73faf-368">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="73faf-369">Wenn bei einer neuen Audiositzung dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p126">Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="73faf-372">Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73faf-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="73faf-373">Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Lync Server die Sitzung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="73faf-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="73faf-p128">Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73faf-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="73faf-376">**Anrufsteuerung in der Netzwerkregion "Nordamerika" mit Anzeige der Bandbreitenkapazitäten und -einschränkungen für die standortübergreifende Verbindung zwischen Reno und Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="73faf-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="73faf-377">![Netzwerkstandorte mit eingeschränkter WAN-Bandbreite (Beispiel)](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Netzwerkstandorte mit eingeschränkter WAN-Bandbreite (Beispiel)")</span><span class="sxs-lookup"><span data-stu-id="73faf-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="73faf-378">Bandbreiteninformationen für eine standortübergreifende Verbindung zwischen zwei Netzwerkstandorten (Bandbreite in KBit/s)</span><span class="sxs-lookup"><span data-stu-id="73faf-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="73faf-379">Name der standortübergreifenden Verbindung</span><span class="sxs-lookup"><span data-stu-id="73faf-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="73faf-380">Erster Standort</span><span class="sxs-lookup"><span data-stu-id="73faf-380">First Site</span></span></th>
    <th><span data-ttu-id="73faf-381">Zweiter Standort</span><span class="sxs-lookup"><span data-stu-id="73faf-381">Second Site</span></span></th>
    <th><span data-ttu-id="73faf-382">Grenzwert für Bandbreite</span><span class="sxs-lookup"><span data-stu-id="73faf-382">BW Limit</span></span></th>
    <th><span data-ttu-id="73faf-383">Grenzwert für Audio</span><span class="sxs-lookup"><span data-stu-id="73faf-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="73faf-384">Grenzwert für Audiositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="73faf-385">Grenzwert für Video</span><span class="sxs-lookup"><span data-stu-id="73faf-385">Video Limit</span></span></th>
    <th><span data-ttu-id="73faf-386">Grenzwert für Videositzung</span><span class="sxs-lookup"><span data-stu-id="73faf-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="73faf-387">Reno-Albu-standortübergreifendes Link</span><span class="sxs-lookup"><span data-stu-id="73faf-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="73faf-388">Reno</span><span class="sxs-lookup"><span data-stu-id="73faf-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="73faf-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="73faf-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="73faf-390">20,000</span><span class="sxs-lookup"><span data-stu-id="73faf-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-391">12.000</span><span class="sxs-lookup"><span data-stu-id="73faf-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-392">175</span><span class="sxs-lookup"><span data-stu-id="73faf-392">175</span></span></p></td>
    <td><p><span data-ttu-id="73faf-393">5,000</span><span class="sxs-lookup"><span data-stu-id="73faf-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="73faf-394">700</span><span class="sxs-lookup"><span data-stu-id="73faf-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="73faf-395">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="73faf-395">Next Steps</span></span>

<span data-ttu-id="73faf-396">Nachdem Sie die erforderlichen Informationen gesammelt haben, können Sie die Bereitstellung der Anrufsteuerung mithilfe der lync Server-Verwaltungsshell oder der lync Server-Systemsteuerung durchführen.</span><span class="sxs-lookup"><span data-stu-id="73faf-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="73faf-397">Obwohl Sie die meisten Netzwerk Konfigurationsaufgaben mithilfe von lync Server-Systemsteuerung ausführen können, müssen Sie lync Server-Verwaltungsshell verwenden, um Subnetze und standortübergreifende Links zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73faf-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="73faf-398">Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation zum Cmdlet <STRONG>New-CsNetworkSubnet</STRONG> und im Cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="73faf-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

