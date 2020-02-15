---
title: 'Lync Server 2013: Planen der VoIP-Ausfallsicherheit für den zentralen Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11f1f6a44530bbb6bdabde4f39b3e63bd0b5c1c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="8b877-102">Planen der VoIP-Ausfallsicherheit für den zentralen Standort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b877-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b877-103">_**Letztes Änderungsstand des Themas:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="8b877-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="8b877-104">Immer mehr Unternehmen verfügen über mehrere Standorte, die weltweit verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="8b877-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="8b877-105">Die Verwaltung von Notfalldiensten, der Zugriff auf das Helpdesk und die Möglichkeit, wichtige geschäftliche Aufgaben auszuführen, wenn ein zentraler Standort außer Betrieb ist, sind für alle Lösungen für die Ausfallsicherheit von Enterprise-VoIP unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="8b877-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="8b877-106">Wenn ein zentraler Standort nicht länger verfügbar ist, muss Folgendes sichergestellt werden:</span><span class="sxs-lookup"><span data-stu-id="8b877-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="8b877-107">Bereitstellung von VoIP-Failover.</span><span class="sxs-lookup"><span data-stu-id="8b877-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="8b877-108">Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich mit einem alternativen Front-End-Pool registrieren können.</span><span class="sxs-lookup"><span data-stu-id="8b877-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="8b877-109">Dies kann durch Erstellen mehrerer DNS-SRV-Einträge geschehen, die jeweils in eine Directorpool oder Front-End-Pool an jedem zentralen Standort aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="8b877-110">Sie können die Priorität und die Gewichtung der SRV-Einträge anpassen, sodass Benutzer, die von diesem zentralen Standort bedient werden, den entsprechenden Director und Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.</span><span class="sxs-lookup"><span data-stu-id="8b877-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="8b877-111">Eingehende und ausgehende Anrufe von Benutzern an anderen Standorten müssen an das Telefonfestnetz umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="8b877-112">In diesem Thema wird die empfohlene Lösung zum Sicherstellen der VoIP-Ausfallsicherheit für einen zentralen Standort beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b877-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="8b877-113">Architektur und Topologie</span><span class="sxs-lookup"><span data-stu-id="8b877-113">Architecture and Topology</span></span>

<span data-ttu-id="8b877-114">Für die Planung der VoIP-Ausfallsicherheit an einem zentralen Standort ist ein grundlegendes Verständnis der zentralen Rolle erforderlich, die die lync Server 2013 Registrierungsstelle beim Aktivieren des VoIP-Failovers spielt.</span><span class="sxs-lookup"><span data-stu-id="8b877-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="8b877-115">Die lync Server Registrierungsstelle ist eine Server Rolle, die die Clientregistrierung und-Authentifizierung ermöglicht und Routingdienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8b877-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="8b877-116">Sie befindet sich zusammen mit anderen Komponenten auf einem Standard Edition-Server, Front-End-Server, Director oder Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="8b877-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="8b877-117">Ein registrierungsstellenpool besteht aus Registrierungsdiensten, die auf der Front-End-Pool und an derselben Website installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8b877-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="8b877-118">Die Front-End-Pool muss Lastenausgleich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8b877-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="8b877-119">Empfohlen wird der DNS-Lastenausgleich, der Einsatz eines Hardwaregeräts zum Lastenausgleich ist jedoch ebenfalls möglich.</span><span class="sxs-lookup"><span data-stu-id="8b877-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="8b877-120">Ein lync-Client ermittelt die Front-End-Pool über den folgenden Erkennungsmechanismus:</span><span class="sxs-lookup"><span data-stu-id="8b877-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="8b877-121">DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="8b877-121">DNS SRV record</span></span>

2.  <span data-ttu-id="8b877-122">AutoErmittlungsdienst (neu in lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="8b877-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="8b877-123">DHCP-Option 120</span><span class="sxs-lookup"><span data-stu-id="8b877-123">DHCP option 120</span></span>

<span data-ttu-id="8b877-124">Nachdem der lync-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Lastenausgleich an einen der Front-End-Server im Pool geleitet.</span><span class="sxs-lookup"><span data-stu-id="8b877-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="8b877-125">Durch diese Front-End-Server wird der Client wiederum an eine bevorzugte Registrierungsstelle im Pool umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8b877-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="8b877-126">Jeder für Enterprise-VoIP aktivierte Benutzer wird einem bestimmten registrierungsstellenpool zugewiesen, der zum primären registrierungsstellenpool des Benutzers wird.</span><span class="sxs-lookup"><span data-stu-id="8b877-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="8b877-127">Typischerweise verwenden Hunderte oder Tausende Benutzer an einem Standort einen einzigen primären Registrierungspool gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="8b877-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="8b877-128">Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer als Benutzer betrachten, der für den zentralen Standort registriert ist.</span><span class="sxs-lookup"><span data-stu-id="8b877-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="8b877-129">Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die mit einem Survivable Branch Appliance registriert sind.</span><span class="sxs-lookup"><span data-stu-id="8b877-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="8b877-130">Zum Gewährleisten von VoIP-Ausfallsicherheit beim Ausfall eines zentralen Standorts muss der primäre Registrierungspool über einen einzelnen designierten Sicherungsregistrierungspool verfügen, der sich an einem anderen Standort befindet.</span><span class="sxs-lookup"><span data-stu-id="8b877-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="8b877-131">Die Sicherung kann mithilfe von Ausfall Sicherheitseinstellungen für den Topologie-Generator konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="8b877-132">Vorausgesetzt, dass eine ausfallsichere WAN-Leitung zwischen den beiden Standorten besteht, werden Benutzer des nicht mehr verfügbaren primären Registrierungspools automatisch an den Sicherungsregistrierungspool geleitet.</span><span class="sxs-lookup"><span data-stu-id="8b877-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="8b877-133">Der Such- und Registrierungsprozess des Clients umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="8b877-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="8b877-134">Ein Client erkennt lync Server über DNS-SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="8b877-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="8b877-135">In lync Server 2013 können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8b877-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="8b877-136">Beispiel: Wenn das Unternehmen Contoso über drei zentrale Standorte (in Nordamerika, Europa und im asiatisch-pazifischen Raum) sowie einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die vollqualifizierten Domänennamen der Director-Pools an jedem dieser drei Standorte verweisen.</span><span class="sxs-lookup"><span data-stu-id="8b877-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="8b877-137">Solange die Directorpool an einem der Standorte verfügbar ist, kann der Client eine Verbindung mit dem ersten Hop-lync Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="8b877-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b877-138">Die Verwendung eines Directorpool ist optional.</span><span class="sxs-lookup"><span data-stu-id="8b877-138">Using a Director pool is optional.</span></span> <span data-ttu-id="8b877-139">Stattdessen kann ein Front-End-Pool verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="8b877-140">Das Directorpool informiert den lync-Client über den primären Registrierungspool des Benutzers und den sicherungsregistrierungspool.</span><span class="sxs-lookup"><span data-stu-id="8b877-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="8b877-141">Der lync-Client versucht zuerst, eine Verbindung mit dem primären Registrierungspool des Benutzers herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8b877-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="8b877-142">Wenn der primäre Registrierungspool verfügbar ist, wird die Registrierung akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="8b877-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="8b877-143">Wenn der primäre registrierungsstellenpool nicht verfügbar ist, versucht der lync-Client, eine Verbindung mit dem Sicherungs registrierungsstellenpool herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8b877-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="8b877-144">Wenn der Sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (kein Empfang des Heartbeatsignals innerhalb eines festgelegten Failoverintervalls), akzeptiert der Sicherungsregistrierungspool die Registrierung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8b877-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="8b877-145">Nachdem die Sicherungs Registrierungsstelle festgestellt hat, dass die primäre Registrierungsstelle wieder verfügbar ist, leitet der Sicherungs Registrierungsstellen-Pool Failover-lync-Clients an Ihren primären Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="8b877-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="8b877-p110">Die folgende Abbildung zeigt die empfohlene Topologie zum Gewährleisten von Ausfallsicherheit für einen zentralen Standort. Die zwei Standorte sind über eine ausfallsichere WAN-Leitung verbunden. Wenn der zentrale Standort ausfällt, werden Benutzer, die diesem Pool zugewiesen sind, zur Registrierung an den Sicherungsstandort umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8b877-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="8b877-149">**Empfohlene Topologie für VoIP-Ausfallsicherheit an einem zentralen Standort**</span><span class="sxs-lookup"><span data-stu-id="8b877-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="8b877-150">![Topologie für VoIP-resliency für den zentralen Standort](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie für VoIP-resliency für den zentralen Standort")</span><span class="sxs-lookup"><span data-stu-id="8b877-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="8b877-151">Anforderungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="8b877-151">Requirements and Recommendations</span></span>

<span data-ttu-id="8b877-152">Die folgenden Anforderungen und Empfehlungen für die Implementierung von VoIP-Ausfallsicherheit an einem zentralen Standort gelten für die meisten Organisationen:</span><span class="sxs-lookup"><span data-stu-id="8b877-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="8b877-153">Die Standorte, an denen sich der primäre und der Sicherungsregistrierungspool befinden, sollten über eine ausfallsichere WAN-Leitung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="8b877-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="8b877-154">Jeder zentrale Standort muss über einen Registrierungspool mit mindestens einer Registrierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b877-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="8b877-155">Jeder registrierungsstellenpool muss mithilfe des DNS-Lastenausgleichs, des Hardwarelastenausgleichs oder beider Lastenausgleich erfolgen.</span><span class="sxs-lookup"><span data-stu-id="8b877-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="8b877-156">Ausführliche Informationen zum Planen der Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b877-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="8b877-157">Jeder Benutzer muss einem primären registrierungsstellenpool zugewiesen werden, indem er entweder das lync Server-Verwaltungsshell-Cmdlet " **CsUser** " oder den lync Server-Systemsteuerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b877-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="8b877-158">Der primäre Registrierungspool muss über einen einzelnen Sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b877-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="8b877-159">Für den primären Registrierungspool muss ein Failover auf den Sicherungsregistrierungspool konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="8b877-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="8b877-160">In der Standardeinstellung ist für die primäre Registrierung ein Failover auf den Sicherungsregistrierungspool nach 300 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8b877-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="8b877-161">Sie können dieses Intervall mithilfe des lync Server 2013 Topologie-Generators ändern.</span><span class="sxs-lookup"><span data-stu-id="8b877-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="8b877-162">Konfigurieren Sie eine Failover-Route, wie im Thema "[Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" in der Planungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b877-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="8b877-163">Geben Sie beim Konfigurieren der Route ein Gateway an, das sich an einem anderen Standort befindet als das in der primären Route angegebene Gateway.</span><span class="sxs-lookup"><span data-stu-id="8b877-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="8b877-164">Wenn sich Ihr primärer Verwaltungsserver am zentralen Standort befindet und dieser Standort wahrscheinlich für einen längeren Zeitraum ausfällt, müssen Sie Ihre Verwaltungstools am Sicherungsstandort erneut installieren. Andernfalls können keine Verwaltungseinstellungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="8b877-165">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="8b877-165">Dependencies</span></span>

<span data-ttu-id="8b877-166">Lync Server hängt von den folgenden Infrastruktur-und Softwarekomponenten ab, um die VoIP-Ausfallsicherheit zu gewährleisten:</span><span class="sxs-lookup"><span data-stu-id="8b877-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b877-167"><strong>Komponente</strong></span><span class="sxs-lookup"><span data-stu-id="8b877-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="8b877-168"><strong>Funktions</strong></span><span class="sxs-lookup"><span data-stu-id="8b877-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b877-169">DNS</span><span class="sxs-lookup"><span data-stu-id="8b877-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="8b877-170">Auflösen von SRV- und A-Einträgen für Konnektivität zwischen Servern bzw. zwischen Servern und Clients</span><span class="sxs-lookup"><span data-stu-id="8b877-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b877-171">Exchange und Exchange-Webdienste</span><span class="sxs-lookup"><span data-stu-id="8b877-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="8b877-172">Speicherung von Kontakten, Kalenderdaten</span><span class="sxs-lookup"><span data-stu-id="8b877-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b877-173">Exchange Unified Messaging und Exchange-Webdienste</span><span class="sxs-lookup"><span data-stu-id="8b877-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="8b877-174">Anrufprotokolle, Voicemailliste, Voicemail</span><span class="sxs-lookup"><span data-stu-id="8b877-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b877-175">DHCP Options 120</span><span class="sxs-lookup"><span data-stu-id="8b877-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="8b877-176">Wenn DNS-SRV nicht verfügbar ist, versucht der Client, DHCP Option 120 für die Suche nach der Registrierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b877-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="8b877-177">Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert sein, oder lync Server 2013 DHCP muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="8b877-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="8b877-178">Ausführliche Informationen finden Sie unter Hardware-und Software Anforderungen für Ausfallsicherheit für Zweigstellenstandorte in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für lync Server 2013</a> Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="8b877-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="8b877-179">VoIP-Funktionen mit Ausfallsicherheit</span><span class="sxs-lookup"><span data-stu-id="8b877-179">Survivable Voice Features</span></span>

<span data-ttu-id="8b877-180">Wenn die vorstehenden Anforderungen und Empfehlungen implementiert wurden, werden die folgenden VoIP-Funktionen vom Sicherungsregistrierungspool bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="8b877-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="8b877-181">Ausgehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="8b877-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="8b877-182">Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter das Failover auf einen Sicherungsstandort unterstützt</span><span class="sxs-lookup"><span data-stu-id="8b877-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="8b877-183">Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden</span><span class="sxs-lookup"><span data-stu-id="8b877-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="8b877-184">Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe</span><span class="sxs-lookup"><span data-stu-id="8b877-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="8b877-185">Instant Messaging mit zwei Teilnehmern sowie Freigabe von Audio- und Videoinhalten zwischen Benutzern am selben Standort</span><span class="sxs-lookup"><span data-stu-id="8b877-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="8b877-186">Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste (jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung oder alle Teammitglieder am selben Standort konfiguriert sind).</span><span class="sxs-lookup"><span data-stu-id="8b877-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="8b877-187">Vorhandene Telefone und Clients sind weiterhin funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="8b877-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="8b877-188">Aufzeichnung von Kommunikationsdatensätzen (KDS)</span><span class="sxs-lookup"><span data-stu-id="8b877-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="8b877-189">Authentifizierung und Autorisierung</span><span class="sxs-lookup"><span data-stu-id="8b877-189">Authentication and authorization</span></span>

<span data-ttu-id="8b877-190">Abhängig von ihrer Konfiguration können die folgenden VoIP-Funktionen beim Ausfall eines primären zentralen Standorts verwendet werden oder nicht:</span><span class="sxs-lookup"><span data-stu-id="8b877-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="8b877-191">Hinterlassen und Abrufen von Voicemail</span><span class="sxs-lookup"><span data-stu-id="8b877-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="8b877-192">Wenn Exchange UM beim Ausfall des primären zentralen Standorts verfügbar sein soll, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8b877-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="8b877-193">Ändern Sie DNS-SRV-Einträge so, dass die Exchange UM-Server am zentralen Standort auf Exchange UM-Sicherungsserver an einem anderen Standort verweisen.</span><span class="sxs-lookup"><span data-stu-id="8b877-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="8b877-194">Konfigurieren Sie die Exchange UM Wähleinstellungen für die einzelnen Benutzer so, dass Sie Exchange um Server am zentralen Standort und am Sicherungsstandort einschließen, jedoch die Sicherung Exchange um Server als deaktiviert festlegen.</span><span class="sxs-lookup"><span data-stu-id="8b877-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="8b877-195">Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange um Server am Sicherungsstandort als aktiviert kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="8b877-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="8b877-196">Wenn keine der oben genannten Lösungen möglich ist, sind Exchange um nicht verfügbar, falls der zentrale Standort nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8b877-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="8b877-197">Alle Konferenztypen</span><span class="sxs-lookup"><span data-stu-id="8b877-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="8b877-p116">Ein Benutzer, für den ein Failover auf einen Sicherungsstandort durchgeführt wurde, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist. In seinem eigenen primären Pool, der nicht länger verfügbar ist, kann der Benutzer jedoch keine Konferenz erstellen oder hosten. Gleichermaßen können auch keine anderen Benutzer an Konferenzen teilnehmen, die im betroffenen primären Pool des Benutzers gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="8b877-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="8b877-200">Die folgenden VoIP-Funktionen können nicht verwendet werden, wenn ein primärer zentraler Standort ausfällt:</span><span class="sxs-lookup"><span data-stu-id="8b877-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="8b877-201">Automatische Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="8b877-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="8b877-202">Anwesenheits- und DNS-basiertes Routing</span><span class="sxs-lookup"><span data-stu-id="8b877-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="8b877-203">Aktualisieren der Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="8b877-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="8b877-204">Reaktionsgruppendienst und Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="8b877-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="8b877-205">Bereitstellen neuer Telefone und Clients</span><span class="sxs-lookup"><span data-stu-id="8b877-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="8b877-206">Adressbuchwebsuche</span><span class="sxs-lookup"><span data-stu-id="8b877-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b877-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b877-207">See Also</span></span>


[<span data-ttu-id="8b877-208">Planen von VoIP-Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b877-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

