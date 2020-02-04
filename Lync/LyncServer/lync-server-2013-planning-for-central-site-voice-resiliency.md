---
title: 'Lync Server 2013: Planen von VoIP-Ausfallsicherheit für den zentralen Standort'
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
ms.openlocfilehash: fbeda869c078e6adfce18088545428170b356980
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="0774f-102">Planen von VoIP-Ausfallsicherheit für den zentralen Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0774f-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0774f-103">_**Letztes Änderungsdatum des Themas:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="0774f-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="0774f-104">In zunehmendem Maße haben Unternehmen mehrere Websites, die sich auf der ganzen Welt verteilen.</span><span class="sxs-lookup"><span data-stu-id="0774f-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="0774f-105">Die Verwaltung von Notfalldiensten, der Zugriff auf den Helpdesk und die Möglichkeit, wichtige Geschäftsaufgaben auszuführen, wenn eine zentrale Website nicht mehr zur Verfügung steht, ist für die Lösung von Enterprise-VoIP-Resilienz unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="0774f-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="0774f-106">Wenn eine zentrale Website nicht mehr verfügbar ist, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="0774f-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="0774f-107">Sprach-Failover muss bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="0774f-108">Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich mit einem alternativen Front-End-Pool registrieren können.</span><span class="sxs-lookup"><span data-stu-id="0774f-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="0774f-109">Dies kann durch Erstellen mehrerer DNS-SRV-Einträge erfolgen, die jeweils zu einem Director-Pool oder einem Front-End-Pool in jeder ihrer zentralen Websites aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="0774f-110">Sie können die Priorität und die Gewichtung der SRV-Einträge anpassen, damit Benutzer, die von dieser zentralen Website bedient werden, den entsprechenden Director und den Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.</span><span class="sxs-lookup"><span data-stu-id="0774f-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="0774f-111">Anrufe an und von Benutzern, die sich an anderen Standorten befinden, müssen an das PSTN umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="0774f-112">In diesem Thema wird die empfohlene Lösung zum Sichern der VoIP-Stabilität der zentralen Website beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0774f-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="0774f-113">Architektur und Topologie</span><span class="sxs-lookup"><span data-stu-id="0774f-113">Architecture and Topology</span></span>

<span data-ttu-id="0774f-114">Für die Planung der sprach Stabilität an einem zentralen Standort ist ein grundlegendes Verständnis der zentralen Rolle erforderlich, die von der lync Server 2013-Registrierungsstelle beim Aktivieren des sprach Failovers gespielt wird.</span><span class="sxs-lookup"><span data-stu-id="0774f-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="0774f-115">Die lync Server-Registrierungsstelle ist eine Serverrolle, die die Clientregistrierung und-Authentifizierung ermöglicht und Routingdienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0774f-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="0774f-116">Es befindet sich zusammen mit anderen Komponenten auf einem Standard Edition-Server, Front-End-Server, Director oder Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="0774f-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="0774f-117">Ein Registrierungspool besteht aus Registrierungsdiensten, die im Front-End-Pool ausgeführt werden und sich am gleichen Standort befinden.</span><span class="sxs-lookup"><span data-stu-id="0774f-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="0774f-118">Der Front-End-Pool muss Lastenausgleich sein.</span><span class="sxs-lookup"><span data-stu-id="0774f-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="0774f-119">DNS-Lastenausgleich wird empfohlen, der Hardwarelastenausgleich ist jedoch akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="0774f-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="0774f-120">Ein lync-Client ermittelt den Front-End-Pool mithilfe des folgenden Ermittlungsmechanismus:</span><span class="sxs-lookup"><span data-stu-id="0774f-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="0774f-121">DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="0774f-121">DNS SRV record</span></span>

2.  <span data-ttu-id="0774f-122">AutoDiscovery Web Service (neu in lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="0774f-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="0774f-123">DHCP-Option 120</span><span class="sxs-lookup"><span data-stu-id="0774f-123">DHCP option 120</span></span>

<span data-ttu-id="0774f-124">Nachdem der lync-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Load Balancer an einen der Front-End-Server im Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0774f-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="0774f-125">Dieser Front-End-Server leitet den Client wiederum an eine bevorzugte Registrierungsstelle im Pool um.</span><span class="sxs-lookup"><span data-stu-id="0774f-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="0774f-126">Jeder Benutzer, der für Enterprise-VoIP aktiviert ist, wird einem bestimmten Registrar-Pool zugewiesen, der zum primären Registrierungspool des Benutzers wird.</span><span class="sxs-lookup"><span data-stu-id="0774f-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="0774f-127">An einer bestimmten Website teilen sich in der Regel Hunderte oder Tausende von Benutzern einen einzigen primären Registrierungspool.</span><span class="sxs-lookup"><span data-stu-id="0774f-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="0774f-128">Zum berücksichtigen des Verbrauchs von Ressourcen für zentrale Websites durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie die einzelnen Verzweigungs Websitebenutzer als Benutzer berücksichtigen, die bei der zentralen Website registriert sind.</span><span class="sxs-lookup"><span data-stu-id="0774f-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="0774f-129">Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.</span><span class="sxs-lookup"><span data-stu-id="0774f-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="0774f-130">Um die sprach Sicherheit bei einem zentralen Standortausfall zu gewährleisten, muss der primäre Registrierungspool über einen einzelnen dedizierten Sicherungs Registrierungs Registrierungspool an einer anderen Website verfügen.</span><span class="sxs-lookup"><span data-stu-id="0774f-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="0774f-131">Die Sicherung kann mithilfe der Stabilitäts Einstellungen des Topologie-Generators konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="0774f-132">Unter der Voraussetzung, dass eine stabile WAN-Verbindung zwischen den beiden Websites besteht, werden Benutzer, deren primärer Registrierungspool nicht mehr verfügbar ist, automatisch an den sicherungsregistrierungspool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0774f-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="0774f-133">Die folgenden Schritte beschreiben den Client Ermittlungs-und Registrierungsprozess:</span><span class="sxs-lookup"><span data-stu-id="0774f-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="0774f-134">Ein Client erkennt lync Server über DNS-SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="0774f-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="0774f-135">In lync Server 2013 können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0774f-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="0774f-136">Wenn Enterprise Contoso beispielsweise über drei zentrale Standorte (Nordamerika, Europa und Asien – Pazifik) und einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die FQDNs des Director-Pools in jedem der drei Speicherorte verweisen.</span><span class="sxs-lookup"><span data-stu-id="0774f-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="0774f-137">Solange der Director-Pool an einem der Speicherorte verfügbar ist, kann der Client eine Verbindung mit dem lync-Server für den ersten Hop herstellen.</span><span class="sxs-lookup"><span data-stu-id="0774f-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0774f-138">Die Verwendung eines Director-Pools ist optional.</span><span class="sxs-lookup"><span data-stu-id="0774f-138">Using a Director pool is optional.</span></span> <span data-ttu-id="0774f-139">Stattdessen kann ein Front-End-Pool verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="0774f-140">Der Director-Pool informiert den lync-Client über den primären Registrierungspool und den sicherungsregistrierungspool des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0774f-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="0774f-141">Der lync-Client versucht zunächst, eine Verbindung mit dem primären Registrierungspool des Benutzers herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0774f-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="0774f-142">Wenn der primäre Registrierungspool verfügbar ist, akzeptiert die Registrierungsstelle die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="0774f-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="0774f-143">Wenn der primäre Registrierungspool nicht verfügbar ist, versucht der lync-Client, eine Verbindung mit dem sicherungsregistrierungspool herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0774f-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="0774f-144">Wenn der sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (durch Erkennen eines fehlenden Heartbeats für ein angegebenes Failover-Intervall), akzeptiert der sicherungsregistrierungspool die Registrierung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0774f-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="0774f-145">Nachdem die Sicherungs Registrierungsstelle festgestellt hat, dass die primäre Registrierungsstelle wieder verfügbar ist, leitet der sicherungsregistrierungspool Failover-lync-Clients an Ihren primären Pool um.</span><span class="sxs-lookup"><span data-stu-id="0774f-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="0774f-146">Die folgende Abbildung zeigt die empfohlene Topologie zur Gewährleistung der Stabilität des zentralen Standorts.</span><span class="sxs-lookup"><span data-stu-id="0774f-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="0774f-147">Die beiden Standorte sind durch eine stabile WAN-Verbindung verbunden.</span><span class="sxs-lookup"><span data-stu-id="0774f-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="0774f-148">Wenn die zentrale Website nicht mehr verfügbar ist, werden Benutzer, die diesem Pool zugewiesen sind, zur Registrierung an die Sicherungswebsite weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0774f-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="0774f-149">**Empfohlene Topologie für die sprach Stabilität von Central Site**</span><span class="sxs-lookup"><span data-stu-id="0774f-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="0774f-150">![Topologie für Voice-resliency für zentrale Websites](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie für Voice-resliency für zentrale Websites")</span><span class="sxs-lookup"><span data-stu-id="0774f-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="0774f-151">Anforderungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="0774f-151">Requirements and Recommendations</span></span>

<span data-ttu-id="0774f-152">Die folgenden Voraussetzungen und Empfehlungen für die Implementierung der VoIP-Flexibilität für die zentrale Website sind für die meisten Organisationen geeignet:</span><span class="sxs-lookup"><span data-stu-id="0774f-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="0774f-153">Die Websites, auf denen sich die primären und die Sicherungs registrierungspools befinden, sollten über eine stabile WAN-Verbindung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="0774f-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="0774f-154">Jede zentrale Website muss einen Registrierungspool enthalten, der aus einer oder mehreren Registrierungsstellen besteht.</span><span class="sxs-lookup"><span data-stu-id="0774f-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="0774f-155">Jeder Registrierungspool muss mithilfe des DNS-Lastenausgleichs, des Hardwarelastenausgleichs oder beider Lastenausgleich erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0774f-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="0774f-156">Detaillierte Informationen zum Planen Ihrer Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0774f-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="0774f-157">Jeder Benutzer muss einem primären registrierungsstellenpool mithilfe des lync Server-Verwaltungsshell-Cmdlets " **CsUser** " oder der lync Server-Systemsteuerung zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="0774f-158">Der primäre Registrierungspool muss über einen einzelnen sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.</span><span class="sxs-lookup"><span data-stu-id="0774f-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="0774f-159">Der primäre Registrierungspool muss so konfiguriert sein, dass ein Failover zum sicherungsregistrierungspool durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="0774f-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="0774f-160">Standardmäßig ist die primäre Registrierungsstelle so eingestellt, dass Sie nach einem Intervall von 300 Sekunden ein Failover für den sicherungsregistrierungspool durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="0774f-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="0774f-161">Sie können dieses Intervall mithilfe des lync Server 2013-Topologie-Generators ändern.</span><span class="sxs-lookup"><span data-stu-id="0774f-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="0774f-162">Konfigurieren Sie eine Failover-Route, wie im Thema "[Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" in der Planning-Dokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0774f-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="0774f-163">Geben Sie bei der Konfiguration der Route ein Gateway an, das sich an einem anderen Standort als dem Gateway befindet, das auf der primären Route angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0774f-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="0774f-164">Wenn die zentrale Website Ihren primären Verwaltungsserver enthielt und die Website wahrscheinlich für einen längeren Zeitraum nicht mehr zur Verfügung steht, müssen Sie Ihre Verwaltungstools auf der Sicherungswebsite erneut installieren. Andernfalls können Sie keine Verwaltungseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="0774f-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="0774f-165">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="0774f-165">Dependencies</span></span>

<span data-ttu-id="0774f-166">Lync Server hängt von den folgenden Infrastruktur-und Softwarekomponenten ab, um die sprach Sicherheit zu gewährleisten:</span><span class="sxs-lookup"><span data-stu-id="0774f-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0774f-167"><strong>Komponente</strong></span><span class="sxs-lookup"><span data-stu-id="0774f-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="0774f-168"><strong>Funktions</strong></span><span class="sxs-lookup"><span data-stu-id="0774f-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0774f-169">DNS</span><span class="sxs-lookup"><span data-stu-id="0774f-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="0774f-170">Auflösen von SRV-Einträgen und Datensätzen für Server-Server-und Server-Client-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="0774f-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0774f-171">Exchange-und Exchange-Webdienste (EWS)</span><span class="sxs-lookup"><span data-stu-id="0774f-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="0774f-172">Kontaktspeicher; Kalenderdaten</span><span class="sxs-lookup"><span data-stu-id="0774f-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0774f-173">Exchange Unified Messaging und Exchange-Webdienste</span><span class="sxs-lookup"><span data-stu-id="0774f-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="0774f-174">Anrufprotokolle, voicemailliste, Voicemail</span><span class="sxs-lookup"><span data-stu-id="0774f-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0774f-175">DHCP-Optionen 120</span><span class="sxs-lookup"><span data-stu-id="0774f-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="0774f-176">Wenn der DNS-SRV nicht zur Verfügung steht, versucht der Client, DHCP-Option 120 zu verwenden, um die Registrierungsstelle zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0774f-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="0774f-177">Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert sein, oder lync Server 2013 DHCP muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0774f-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="0774f-178">Ausführliche Informationen finden Sie unter Hardware-und Software Anforderungen für die Stabilität des Zweigstellen Standorts in den Anforderungen an die <a href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität des Zweigstellen Standorts für den lync Server 2013</a> -Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0774f-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="0774f-179">Überlebende sprach Features</span><span class="sxs-lookup"><span data-stu-id="0774f-179">Survivable Voice Features</span></span>

<span data-ttu-id="0774f-180">Wenn die Voraussetzungen und Empfehlungen implementiert wurden, werden die folgenden Sprachfeatures vom sicherungsregistrierungspool bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="0774f-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="0774f-181">Ausgehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="0774f-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="0774f-182">Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter die Möglichkeit unterstützt, ein Failover zu einer Sicherungswebsite durchführen zu können</span><span class="sxs-lookup"><span data-stu-id="0774f-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="0774f-183">Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites</span><span class="sxs-lookup"><span data-stu-id="0774f-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="0774f-184">Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen</span><span class="sxs-lookup"><span data-stu-id="0774f-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="0774f-185">Instant Messaging mit zwei Teilnehmern und Freigeben von Audio und Video zwischen Benutzern am gleichen Standort</span><span class="sxs-lookup"><span data-stu-id="0774f-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="0774f-186">Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn beide Teilnehmer die Delegation oder alle Teammitglieder anrufen, auf der gleichen Website konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0774f-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="0774f-187">Vorhandene Telefone und Clients funktionieren weiterhin.</span><span class="sxs-lookup"><span data-stu-id="0774f-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="0774f-188">Aufzeichnung von Kommunikationsdatensätzen (KDS)</span><span class="sxs-lookup"><span data-stu-id="0774f-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="0774f-189">Authentifizierung und Autorisierung</span><span class="sxs-lookup"><span data-stu-id="0774f-189">Authentication and authorization</span></span>

<span data-ttu-id="0774f-190">Je nachdem, wie Sie konfiguriert sind, funktionieren die folgenden Sprachfeatures möglicherweise nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="0774f-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="0774f-191">Voicemail-Einzahlung und-Abruf</span><span class="sxs-lookup"><span data-stu-id="0774f-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="0774f-192">Wenn Sie Exchange um verfügbar machen möchten, wenn der primäre zentrale Standort außer Dienst ist, müssen Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="0774f-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="0774f-193">Ändern Sie die DNS-SRV-Einträge so, dass die Exchange um-Server am zentralen Standort auf Exchange-Exchange um-Server an einem anderen Standort verweisen.</span><span class="sxs-lookup"><span data-stu-id="0774f-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="0774f-194">Konfigurieren Sie die Exchange UM-Wähleinstellungen für jeden Benutzer so, dass Exchange um-Server sowohl am zentralen Standort als auch an der Sicherungswebsite eingeschlossen werden, die Exchange um-Server jedoch als deaktiviert festlegen.</span><span class="sxs-lookup"><span data-stu-id="0774f-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="0774f-195">Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange um-Server auf der Sicherungswebsite als aktiviert kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0774f-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="0774f-196">Wenn keine der vorhergehenden Lösungen möglich ist, steht Exchange um nicht zur Verfügung, wenn die zentrale Website nicht mehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="0774f-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="0774f-197">Konferenzen aller Typen</span><span class="sxs-lookup"><span data-stu-id="0774f-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="0774f-198">Ein Benutzer, der ein Failover auf eine Sicherungswebsite durchgeführt hat, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist, aber keine Konferenz im eigenen primären Pool erstellen oder hosten kann, die nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0774f-198">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available.</span></span> <span data-ttu-id="0774f-199">Ebenso können andere Benutzer nicht an Konferenzen teilnehmen, die im primären Pool des betroffenen Benutzers gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="0774f-199">Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="0774f-200">Die folgenden Sprachfeatures funktionieren nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="0774f-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="0774f-201">Automatische Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="0774f-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="0774f-202">Anwesenheits-und auf den textbasierendes Routing</span><span class="sxs-lookup"><span data-stu-id="0774f-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="0774f-203">Aktualisieren der Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="0774f-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="0774f-204">Reaktionsgruppendienst und Anruf parken</span><span class="sxs-lookup"><span data-stu-id="0774f-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="0774f-205">Bereitstellungneuer Telefone und Clients</span><span class="sxs-lookup"><span data-stu-id="0774f-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="0774f-206">Adressbuch-Websuche</span><span class="sxs-lookup"><span data-stu-id="0774f-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0774f-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0774f-207">See Also</span></span>


[<span data-ttu-id="0774f-208">Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0774f-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

