---
title: 'Lync Server 2013: Konfiguration des standortbasierten Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 237799a84d0230bf55737779921dd66b23c27130
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="80cfb-102">Konfiguration des standortbasierten Routings für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80cfb-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80cfb-103">_**Letztes Änderungsstand des Themas:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="80cfb-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="80cfb-104">Die standortbasierte Routing Konferenz Anwendung beruht auf der Konfiguration lync Server 2013 standortbasierten Routings.</span><span class="sxs-lookup"><span data-stu-id="80cfb-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="80cfb-105">Die wichtigsten Konfigurationen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="80cfb-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="80cfb-106">Die Position der Teilnehmer, die einer Besprechung beitreten, wird basierend auf dem Netzwerkstandort bestimmt.</span><span class="sxs-lookup"><span data-stu-id="80cfb-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="80cfb-107">Ein Netzwerkstandort und die zugehörigen Netzwerk Subnetze müssen in lync Server definiert sein, um standortbasiertes Routing erzwingen zu können.</span><span class="sxs-lookup"><span data-stu-id="80cfb-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="80cfb-108">Um das standortbasierte Routing von Besprechungen zu erzwingen, müssen lync-Teilnehmer für das standortbasierte Routing aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="80cfb-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="80cfb-109">Zum Erzwingen eines standortbasierten Routings von PSTN-Endpunkten, die Besprechungen beitreten, muss der SIP-Trunk, der zum Verbinden der PSTN-Endpunkte verwendet wird, für das standortbasierte Routing konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="80cfb-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="80cfb-110">Weitere Informationen zum Bereitstellen und konfigurieren lync Server 2013 standortbasierten Routings finden Sie unter Konfigurieren des [standortbasierten Routings](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="80cfb-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="80cfb-111">Aktivieren der standortbasierten Routing Konferenz Anwendung</span><span class="sxs-lookup"><span data-stu-id="80cfb-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="80cfb-112">Die standortbasierte Routing Konferenz Anwendung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="80cfb-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="80cfb-113">Vor dem Aktivieren dieser Anwendung müssen Sie die richtige Priorität bestimmen, die für die Anwendung zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="80cfb-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="80cfb-114">Um diese Priorität zu ermitteln, führen Sie das folgende Cmdlet in lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="80cfb-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="80cfb-115">Get-CsServerApplication-Identity Service: Registrierungsstelle\<: Pool-FQDN\></span><span class="sxs-lookup"><span data-stu-id="80cfb-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="80cfb-116">In diesem Cmdlet ist \<Pool FQDN\> der Pool, in dem die standortbasierte Routing Konferenz Anwendung aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="80cfb-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="80cfb-117">Dieses Cmdlet gibt die Liste der von lync Server gehosteten Anwendungen und den Prioritätswert für jeden von Ihnen zurück.</span><span class="sxs-lookup"><span data-stu-id="80cfb-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="80cfb-118">Die standortbasierte Routing Konferenz Anwendung muss einen Prioritätswert größer als die "UdcAgent"-Anwendung und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="80cfb-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="80cfb-119">Es wird empfohlen, der standortbasierten Routing Konferenz Anwendung einen Prioritätswert zuzuweisen, der einen Punkt höher ist als der Prioritätswert der Anwendung "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="80cfb-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="80cfb-120">Wenn die "UdcAgent"-Anwendung beispielsweise den Prioritätswert "2" hat, hat die "DefaultRouting"-Anwendung den Prioritätswert "8", die "ExumRouting"-Anwendung hat den Prioritätswert "9" und die "OutboundRouting"-Anwendung hat den Prioritätswert "10", dann Sie sollten der standortbasierten Routing Konferenz Anwendung einen Prioritätswert von "3" zuweisen.</span><span class="sxs-lookup"><span data-stu-id="80cfb-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="80cfb-121">Dadurch wird die Priorität der Anwendungen in der folgenden Reihenfolge platziert: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), standortbasierte Routing Konferenz Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), " DefaultRouting "(Priorität: 9)," ExumRouting "(Priorität: 10) und" OutboundRouting "(Priorität: 11).</span><span class="sxs-lookup"><span data-stu-id="80cfb-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="80cfb-122">Nachdem Sie den richtigen Prioritätswert für die standortbasierte Routing Konferenz Anwendung gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, für den Benutzer für standortbasiertes Routing aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="80cfb-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="80cfb-123">New-CsServerApplication-Identity Service: Registrar:\<Pool FQDN\>/LBRouting-Priority \<\> -Enabled $true-Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="80cfb-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="80cfb-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80cfb-124">For example:</span></span>

<span data-ttu-id="80cfb-125">New-CsServerApplication-Identity Service:Registrar:ls2013cu2lbrpool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="80cfb-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="80cfb-126">Nachdem Sie dieses Cmdlet verwendet haben, starten Sie alle Front-End-Server im Pool oder die Standard Edition-Server neu, auf denen die standortbasierte Routing Konferenz Anwendung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="80cfb-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80cfb-127">Standortbasierte Routing-Erzwingungen zu Konferenzen oder beratenden Übertragungen werden erst durchgesetzt, wenn alle Front-End-Server in den entsprechenden Pools oder Standard Edition-Servern neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="80cfb-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="80cfb-128">Nachdem die standortbasierte Routing Konferenz Anwendung erfolgreich aktiviert wurde und alle entsprechenden lync-Server neu gestartet wurden, werden alle Konferenzen, die von lync-Benutzern für standortbasiertes Routing organisiert wurden, überwacht, um zu verhindern, dass die PSTN-Maut Umgehung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="80cfb-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

