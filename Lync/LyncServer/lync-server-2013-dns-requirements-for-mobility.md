---
title: 'Lync Server 2013: DNS-Anforderungen für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="7fe6a-102">DNS-Anforderungen für Mobilität mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe6a-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe6a-103">_**Letztes Änderungsdatum des Themas:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="7fe6a-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="7fe6a-104">Wenn Sie das Mobilitätsfeature von lync Server 2013 bereitstellen, können Sie die neuen URLs verwenden, die für den AutoErmittlungsdienst von Microsoft lync Server 2013 verfügbar sind, oder Sie können Ihre vorhandenen URLs für Webdienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="7fe6a-105">Wenn Sie Ihre vorhandenen URLs verwenden, müssen die Benutzer die URLs in Ihren Einstellungen für mobile Geräte manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="7fe6a-106">Diese Option wird in der Regel für die Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="7fe6a-107">Wenn Sie die neuen URLs verwenden, können mobile Clients die lync Server 2013-Ressourcen automatisch ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="7fe6a-108">Wenn Sie die automatische Ermittlung unterstützen, müssen Sie neue DNS-Einträge (Domain Name System) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="7fe6a-109">In diesem Abschnitt werden die DNS-Einträge beschrieben, die für die automatische Ermittlung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="7fe6a-110">Zur Unterstützung der automatischen Ermittlung müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:</span><span class="sxs-lookup"><span data-stu-id="7fe6a-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="7fe6a-111">Ein interner DNS-Eintrag zur Unterstützung von mobilen Benutzern, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen</span><span class="sxs-lookup"><span data-stu-id="7fe6a-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="7fe6a-112">Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von mobilen Benutzern, die eine Verbindung mit dem Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="7fe6a-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="7fe6a-113">Die interne automatische Erkennungs-URL sollte nicht von außerhalb Ihres Netzwerks adressierbar sein.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="7fe6a-114">Die URL für die externe automatische Suche sollte in Ihrem Netzwerk nicht adressierbar sein.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="7fe6a-115">Wenn Sie diese Voraussetzungen für die externe URL nicht erfüllen können, sollte der Mobile Client jedoch nicht beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="7fe6a-116">Bei den DNS-Einträgen kann es sich entweder um CNAME-Einträge oder einen (Host-) Eintrag handeln.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="7fe6a-117">**Interne DNS-Einträge**</span><span class="sxs-lookup"><span data-stu-id="7fe6a-117">**Internal DNS records**</span></span>

<span data-ttu-id="7fe6a-118">Sie müssen einen der folgenden internen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="7fe6a-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe6a-119">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="7fe6a-119">Record type</span></span></th>
<th><span data-ttu-id="7fe6a-120">Hostname oder SRV-Definition</span><span class="sxs-lookup"><span data-stu-id="7fe6a-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="7fe6a-121">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="7fe6a-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe6a-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="7fe6a-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-123">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe6a-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-124">Interner Webdienste (Fully Qualified Domain Name, FQDN) für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="7fe6a-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe6a-125">A (Host)</span><span class="sxs-lookup"><span data-stu-id="7fe6a-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-126">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe6a-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-127">Interne Web Services-IP-Adresse (virtuelle IP-Adresse (VIP-Adresse), wenn Sie ein Lastenausgleichsmodul verwenden) Ihres Director-Pools, falls vorhanden, oder des Front-End-Pools, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="7fe6a-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7fe6a-128">**Externe DNS-Einträge**</span><span class="sxs-lookup"><span data-stu-id="7fe6a-128">**External DNS records**</span></span>

<span data-ttu-id="7fe6a-129">Sie müssen einen der folgenden externen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="7fe6a-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe6a-130">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="7fe6a-130">Record type</span></span></th>
<th><span data-ttu-id="7fe6a-131">Hostname</span><span class="sxs-lookup"><span data-stu-id="7fe6a-131">Host name</span></span></th>
<th><span data-ttu-id="7fe6a-132">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="7fe6a-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe6a-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="7fe6a-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-134">lyncdiscover.</span></span> <span data-ttu-id="7fe6a-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe6a-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-136">FQDN externer Webdienste für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben</span><span class="sxs-lookup"><span data-stu-id="7fe6a-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe6a-137">A (Host)</span><span class="sxs-lookup"><span data-stu-id="7fe6a-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-138">lyncdiscover.</span></span> <span data-ttu-id="7fe6a-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe6a-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-140">Externe oder öffentliche IP-Adresse (VIP-Adresse, wenn Sie ein Lastenausgleichsmodul verwenden) des Reverse-Proxys</span><span class="sxs-lookup"><span data-stu-id="7fe6a-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe6a-141">SRV</span><span class="sxs-lookup"><span data-stu-id="7fe6a-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-142">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="7fe6a-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe6a-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="7fe6a-144">Behebt einen Host-Eintrag (A oder AAAA) für den Access-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="7fe6a-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7fe6a-145">Um den Push-Benachrichtigungsdienst und den Apple Push-Benachrichtigungsdienst zu unterstützen, erstellen Sie für jede SIP-Domäne mit Microsoft lync Mobile-Clients einen SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="7fe6a-146">Diese Anforderung gilt nur für Microsoft lync Mobile-Clients auf mobilen Apple-oder Microsoft-basierten Geräten.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="7fe6a-147">Android und Nokia Symbian-Geräte verwenden keine Push-Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7fe6a-148">Lyncdiscover, auch als AutoErmittlung bekannt, verkehrt durch den Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="7fe6a-149">Der SRV-Eintrag verweist auf einen Datensatz, der über den Access-Edgedienst aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7fe6a-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

