---
title: 'Lync Server 2013: Szenarien für den Zugriff durch externe Benutzer'
description: 'Lync Server 2013: Szenarien für den Zugriff durch externe Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547641"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ba12b-103">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba12b-103">Scenarios for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba12b-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ba12b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ba12b-105">Für die Bereitstellung von externem Benutzer Zugriff für lync Server 2013 müssen Sie mindestens einen Edgeserver und einen Reverseproxy im Umkreisnetzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-105">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="ba12b-106">Optional können Sie einen Director oder Directorpool im internen Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-106">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="ba12b-107">Wenn Sie mehr Kapazität benötigen, als ein einzelnes Edgeserver bereitstellen kann, oder wenn Sie hohe Verfügbarkeit für Ihre Edgeserver-Bereitstellung benötigen, können Sie den Lastenausgleich konfigurieren und mehrere Edgeserver in einem Lastenausgleichspool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-107">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="ba12b-108">Wenn Ihre Organisation über mehrere Rechenzentren verfügt, können Sie Edgeserver-oder Edgepool-Bereitstellungen an mehr als einem Standort haben.</span><span class="sxs-lookup"><span data-stu-id="ba12b-108">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="ba12b-109">Es kann jedoch nur eine der Edgeserver-Bereitstellungen als Verbund Route festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-109">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="ba12b-110">In diesem Abschnitt werden die Szenarien für Edgeserver Bereitstellungen definiert und die Planungsabschnitte den möglichen Szenarien zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ba12b-110">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="ba12b-111">Wenn Ihre Bereitstellung beispielsweise eine hohe Verfügbarkeit, einen Partnerverbund mit XMPP-Kontakten (Extensible Messaging and Presence) und lync Mobility erfordert, wählen Sie die entsprechenden Einträge in der folgenden Tabelle aus, die diese Anforderungen erfüllen würden, und verwenden Sie die referenzierten Planungsabschnitte, um Ihre Bereitstellung zu definieren, wie im folgenden Flussdiagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-111">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="ba12b-112">**Auswahl des Szenarios für die Bereitstellung von Edgeservers**</span><span class="sxs-lookup"><span data-stu-id="ba12b-112">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="ba12b-113">![Beispiel Bereitstellungs Flussdiagramm](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Beispiel Bereitstellungs Flussdiagramm")</span><span class="sxs-lookup"><span data-stu-id="ba12b-113">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="ba12b-114">Mit diesem Verfahren können Sie die Konfiguration aller potenziellen Features planen und dokumentieren, die Sie für Ihre Benutzer bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ba12b-114">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="ba12b-115">Sie können jedoch Verbund-und Mobilitätsdienste hinzufügen, nachdem Sie die Edgeserver bereitgestellt und den korrekten Vorgang vor dem Hinzufügen anderer Features bestätigt haben.</span><span class="sxs-lookup"><span data-stu-id="ba12b-115">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="ba12b-116">Der Vorgang des Hinzufügens von Features zu einer vorhandenen Edgeserver-Bereitstellung wird im Abschnitt Bereitstellung behandelt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-116">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="ba12b-117">Ausführliche Informationen zur Bereitstellung finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) durch einschließen der Planung für diese Features während des anfänglichen Planungsprozesses können Sie die DNS-, Firewall-und Zertifikatanforderungen für die hinzugefügten Features vorbereiten, mit denen Sie die Zertifikate erwerben und die DNS-und Port/Protocol-Anforderungen vorab konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="ba12b-117">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ba12b-118">Wenn Sie planen, die Edgeserver und den Reverseproxy zu installieren und später Features hinzuzufügen (beispielsweise "Verbund" und "Mobilität"), legen Sie fest, welche Zertifikate für alle Dienste nach der Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ba12b-118">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="ba12b-119">Wenn Sie die Zertifikate für alle Features vorab planen und erwerben, die anfänglich bereitgestellt wurden oder nicht, müssen Sie keine neuen Zertifikate bestellen, um die Anforderungen des Verbunds (also auf den Edgeserver) oder des Reverseproxys (also für Mobilitätsdienste) zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-119">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ba12b-120">Alle Edge-Dienste werden auf jeder Edgeserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-120">All edge services run on each Edge Server.</span></span> <span data-ttu-id="ba12b-121">Dienste können nicht zwischen zwei unterschiedlichen Edge-Servern aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-121">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="ba12b-122">Wenn Sie eine Edgepool für die Skalierbarkeit bereitstellen, werden alle Edgedienst auf jeder Edgeserver im Pool bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-122">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="ba12b-123">XMPP-Partnerverbund, Office Communications Server und lync Server-Verbund, öffentliche Chat-Konnektivität und Clientmobilität sind zusätzliche Dienste, die bereitgestellt werden können, nachdem Sie Ihre erste Edgeserver oder Edgepool bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba12b-123">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="ba12b-124">Bei den Mobilitätsdiensten handelt es sich um ein Feature, das den Reverseproxy verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba12b-124">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="ba12b-125">Durch die Installation von Mobilitätsdiensten werden keine Funktionen zu ihren Edgeserver hinzugefügt, es ist jedoch eine Neukonfiguration des Reverseproxys erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ba12b-125">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="ba12b-126">Die Spalte <STRONG>Installationsziel</STRONG> , in der diese Features aufgeführt sind, enthält Planungsanleitungen in der zugehörigen Spalte unter <STRONG>Edgeserver Planning-Abschnitt oder in Abschnitten</STRONG> zur gleichzeitigen Planung dieser Features, die bei der Installation und Konfiguration der Edgeserver bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-126">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="ba12b-127">Ermitteln und Zuordnen der Bereitstellungsziele</span><span class="sxs-lookup"><span data-stu-id="ba12b-127">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba12b-128">Installationssziel</span><span class="sxs-lookup"><span data-stu-id="ba12b-128">Installation goal</span></span></th>
<th><span data-ttu-id="ba12b-129">Planungsdokumentation für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="ba12b-129">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba12b-p107">Sie haben entschieden, dass ein einzelner Server für die Edgedienste in Ihrer Infrastruktur ausreichend ist. Außerdem möchten Sie private IP-Adressen für die externen Schnittstellen des Edgeservers mit NAT zum Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="ba12b-132">Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-132">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="ba12b-133">Sie stellen eine Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden NAT, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-133">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba12b-p109">Sie haben entschieden, dass ein einzelner Server für die Edgedienste in Ihrer Infrastruktur ausreichend ist. Außerdem möchten Sie öffentliche IP-Adressen für die externen Schnittstellen des Edgeservers zum Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="ba12b-137">Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-137">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="ba12b-138">Sie stellen eine Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ba12b-138">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="ba12b-139">Anstelle von NAT verwenden Sie Routing in diesem Szenario.</span><span class="sxs-lookup"><span data-stu-id="ba12b-139">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="ba12b-140">Die tatsächliche öffentliche IP-Adresse des Edgeservers wird für externe Benutzer Verbindungen zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-140">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba12b-p111">Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit. Sie möchten außerdem private IP-Adressen für die externen Schnittstellen der Edgeserver mit NAT zum Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="ba12b-144">Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-144">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="ba12b-145">Sie stellen die Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-145">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="ba12b-146">Mit NAT stellen Sie die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</span><span class="sxs-lookup"><span data-stu-id="ba12b-146">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba12b-148">Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="ba12b-148">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="ba12b-149">Sie beabsichtigen auch, öffentliche IP-Adressen für die Edgeserver externen Schnittstellen mit dem Internet zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-149">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="ba12b-150">Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-150">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="ba12b-151">Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-151">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="ba12b-152">Anstelle von NAT stellen Sie mit Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</span><span class="sxs-lookup"><span data-stu-id="ba12b-152">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba12b-154">Sie haben entschieden, dass die hohe Verfügbarkeit der Edge-Dienste für Ihre Benutzer wichtig ist, und Sie werden zwei oder mehr Edgeserver in diesem Pool mit einem Hardwaregerät zum Lastenausgleich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-154">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="ba12b-155">Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-155">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="ba12b-156">Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden Hardwarelastenausgleichs zum Verteilen der Kommunikation über den Pool.</span><span class="sxs-lookup"><span data-stu-id="ba12b-156">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="ba12b-157">Anstelle von NAT stellen Sie mit Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</span><span class="sxs-lookup"><span data-stu-id="ba12b-157">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba12b-159">Die Verbundszenarien ermöglichen die Planung für das Feature, das die Typen der Partner erweitert, mit denen Ihre Benutzer kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="ba12b-159">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="ba12b-160">Lync Server Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="ba12b-160">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="ba12b-161">Office Communications Server Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="ba12b-161">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="ba12b-162">Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="ba12b-162">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="ba12b-163">XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="ba12b-163">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba12b-164">Planen von Verbundszenarien</span><span class="sxs-lookup"><span data-stu-id="ba12b-164">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="ba12b-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planung für lync Server 2013 und Office Communications Server Partnerverbund</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="ba12b-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planen der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="ba12b-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planen des XMPP-Verbunds (Extensible Messaging and Presence Protocol) in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba12b-168">Mobilitätdienste werden über den Reverseproxy bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-168">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="ba12b-169">Dienste, die die Mobilität für externe Benutzer ermöglichen, werden im Front-End-Server oder Front-End-Pool bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba12b-169">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="ba12b-170">Sie erstellen oder ändern vorhandene Veröffentlichungsregeln auf dem Reverseproxy, um Mobilitätsdienste für Ihre externen Benutzer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ba12b-170">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="ba12b-171"><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba12b-171"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="ba12b-172">Die folgenden Szenarioabschnitte enthalten Referenzarchitekturen, Beispiel-DNS, Port-/Protokolldefinitionen und Zertifikatanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-172">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="ba12b-173">Darüber hinaus sind Diagramme für Ihr DNS, Ihre Port-/Protokolldefinitionen und Zertifikatanforderungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ba12b-173">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="ba12b-174">Die Diagramme enthalten eine Vorlage, die Sie ausfüllen und an andere Teams (z. B. das Netzwerkteam, PKI (Public Key Infrastructure)-Team oder Serverbereitstellungsteam) weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="ba12b-174">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="ba12b-175">Das Ziel der Diagramme besteht darin, die Kommunikation zu verbessern und den Erfolg zu gewährleisten, wenn die erforderlichen Edgeserver Konfigurationselemente an die Personen kommuniziert werden, die die eigentliche Konfigurationsarbeit erledigen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-175">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="ba12b-176">Es wird empfohlen, die Diagramme und zugehörigen Referenzarchitekturen zum Planen der Bereitstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-176">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

