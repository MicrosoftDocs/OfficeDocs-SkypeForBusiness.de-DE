---
title: 'Lync Server 2013: Anrufsteuerung in einem MPLS-Netzwerk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee138a0f61bace067db12c9df4f06338aa13ac8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="e4831-102">Anrufsteuerung in einem MPLS-Netzwerk mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4831-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4831-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e4831-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e4831-p101">In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e4831-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="e4831-108">**Beispiel eines MPLS-Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="e4831-108">**Example MPLS network**</span></span>

<span data-ttu-id="e4831-109">![CAC mit MPLS] (images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC mit MPLS")</span><span class="sxs-lookup"><span data-stu-id="e4831-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="e4831-p102">Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der Abbildung oben darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, die die MPLS-Cloud darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4831-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="e4831-113">**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="e4831-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="e4831-114">![Anrufsteuerung (CAC) mit MPLS-Diagramm] (images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Anrufsteuerung (CAC) mit MPLS-Diagramm")</span><span class="sxs-lookup"><span data-stu-id="e4831-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

