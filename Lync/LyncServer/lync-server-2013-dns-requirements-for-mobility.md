---
title: 'Lync Server 2013: DNS-Anforderungen für die Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da4910594581f253db155bfceb85c0dcd78f60
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="1c058-102">DNS-Anforderungen für die Mobilität mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c058-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c058-103">_**Letztes Änderungsstand des Themas:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="1c058-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="1c058-104">Wenn Sie das lync Server 2013 Mobilitätsfeature bereitstellen, können Sie die neuen URLs verwenden, die mit dem Microsoft lync Server 2013 AutoErmittlungsdienst zur Verfügung stehen, oder Sie können Ihre vorhandenen Webdienste-URLs verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c058-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="1c058-105">Wenn Sie vorhandene URLs verwenden, müssen Benutzer in den Einstellungen des mobilen Geräts die URLs manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="1c058-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="1c058-106">Diese Option wird normalerweise zur Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c058-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="1c058-107">Wenn Sie die neuen URLs verwenden, können mobile Clients lync Server 2013 Ressourcen automatisch ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1c058-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="1c058-108">Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue DNS-Einträge (Domain Name System) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c058-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="1c058-109">In diesem Abschnitt werden die DNS-Einträge beschrieben, die für die automatische Ermittlung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1c058-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="1c058-110">Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c058-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="1c058-111">Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen</span><span class="sxs-lookup"><span data-stu-id="1c058-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="1c058-112">Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="1c058-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="1c058-p102">Die interne AutoErmittlung-URL sollte nicht von außerhalb des Netzwerks adressierbar sein. Die externe AutoErmittlung-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn Sie diese Anforderung für die externe URL nicht erfüllen können, sollte dies allerdings nicht die Funktionen des mobilen Clients beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="1c058-p102">The internal automatic discovery URL should not be addressable from outside your network. The external automatic discovery URL should not be addressable from within your network. However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="1c058-116">Bei den DNS-Einträgen kann es sich entweder um A-Einträge (Host) oder um CNAME-Einträge handeln.</span><span class="sxs-lookup"><span data-stu-id="1c058-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="1c058-117">**Interne DNS-Einträge**</span><span class="sxs-lookup"><span data-stu-id="1c058-117">**Internal DNS records**</span></span>

<span data-ttu-id="1c058-118">Sie müssen einen der folgenden internen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c058-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c058-119">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="1c058-119">Record type</span></span></th>
<th><span data-ttu-id="1c058-120">Hostname oder SRV-Definition</span><span class="sxs-lookup"><span data-stu-id="1c058-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="1c058-121">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="1c058-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c058-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c058-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="1c058-123">"lyncdiscoverinternal". &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="1c058-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1c058-124">Interner Webdienste vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="1c058-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c058-125">A (Host)</span><span class="sxs-lookup"><span data-stu-id="1c058-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="1c058-126">"lyncdiscoverinternal". &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="1c058-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1c058-127">Interne Webdienste IP-Adresse (virtuelle IP-Adresse (VIP), wenn Sie einen Lastenausgleich verwenden) Ihres Directorpool, wenn Sie einen haben, oder Ihrer Front-End-Pool, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="1c058-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c058-128">**Externe DNS-Einträge**</span><span class="sxs-lookup"><span data-stu-id="1c058-128">**External DNS records**</span></span>

<span data-ttu-id="1c058-129">Sie müssen einen der folgenden externen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c058-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c058-130">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="1c058-130">Record type</span></span></th>
<th><span data-ttu-id="1c058-131">Hostname</span><span class="sxs-lookup"><span data-stu-id="1c058-131">Host name</span></span></th>
<th><span data-ttu-id="1c058-132">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="1c058-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c058-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c058-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="1c058-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="1c058-134">lyncdiscover.</span></span> <span data-ttu-id="1c058-135">&lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="1c058-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1c058-136">Externer Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="1c058-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c058-137">A (Host)</span><span class="sxs-lookup"><span data-stu-id="1c058-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="1c058-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="1c058-138">lyncdiscover.</span></span> <span data-ttu-id="1c058-139">&lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="1c058-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1c058-140">Externe oder öffentliche IP-Adresse (VIP-Adresse bei Verwendung eines Lastenausgleichs) des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="1c058-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c058-141">SRV</span><span class="sxs-lookup"><span data-stu-id="1c058-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="1c058-142">_sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="1c058-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="1c058-143">&lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="1c058-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="1c058-144">Aufgelöst in Hosteintrag (a oder AAAA) für den Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="1c058-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1c058-145">Zur Unterstützung von Push Notification Service und Apple Push Notification Service erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft lync Mobile-Clients.</span><span class="sxs-lookup"><span data-stu-id="1c058-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1c058-146">Diese Anforderung gilt nur für Microsoft lync Mobile-Clients auf Apple-oder Microsoft-basierten mobilen Geräten.</span><span class="sxs-lookup"><span data-stu-id="1c058-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="1c058-147">Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.</span><span class="sxs-lookup"><span data-stu-id="1c058-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1c058-148">Lyncdiscover, auch bekannt als AutoErmittlung, Verkehr durchläuft den Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="1c058-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="1c058-149">Der SRV-Eintrag verweist auf einen Datensatz, der durch den Zugriffs-Edgedienst aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1c058-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

