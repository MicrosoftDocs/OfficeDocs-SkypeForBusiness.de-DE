---
title: 'Lync Server 2013: Zertifikatzusammenfassung-DNS-und HLB-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055f1eea81f67281384e6a6124b5c72cee6d823f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="0fce3-102">Zertifikatzusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fce3-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fce3-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0fce3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0fce3-104">Zertifikatanforderungen für einen Director mit DNS-Lastenausgleich und ein Hardwaregerät zum Lastenausgleich verwenden ein Standardzertifikat, das einen Antragstellernamen und alternative Antragstellernamen für Dienste verwendet, die der Director empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="0fce3-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="0fce3-105">Ein Zertifikat wird für jeden Director im Pool angefordert.</span><span class="sxs-lookup"><span data-stu-id="0fce3-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="0fce3-106">Bedenken Sie dabei, dass das Hardwaregerät zum Lastenausgleich den Lastenausgleich nur für den Datenverkehr durchführt, der vom Reverseproxy ausgeht.</span><span class="sxs-lookup"><span data-stu-id="0fce3-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="0fce3-107">Außerdem gibt es ein OAuth-Token-Zertifikat für die Authentifizierung von Server zu Server, das auf jedem Server installiert wird.</span><span class="sxs-lookup"><span data-stu-id="0fce3-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="0fce3-108">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="0fce3-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fce3-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="0fce3-109">Component</span></span></th>
<th><span data-ttu-id="0fce3-110">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="0fce3-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="0fce3-111">Alternative Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="0fce3-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="0fce3-112">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="0fce3-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fce3-113">Standard</span><span class="sxs-lookup"><span data-stu-id="0fce3-113">Default</span></span></p></td>
<td><p><span data-ttu-id="0fce3-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0fce3-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0fce3-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0fce3-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="0fce3-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0fce3-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="0fce3-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fce3-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0fce3-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fce3-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="0fce3-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fce3-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="0fce3-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fce3-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="0fce3-121">(Optional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fce3-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0fce3-122">Director-Zertifikate können von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0fce3-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="0fce3-123">Der Director antwortet auf Anfragen vom Reverseproxy im Umkreis oder von der Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="0fce3-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="0fce3-124">Für interne Clients wird der Director nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fce3-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="0fce3-125">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="0fce3-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fce3-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="0fce3-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="0fce3-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0fce3-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0fce3-128">Kein Eintrag</span><span class="sxs-lookup"><span data-stu-id="0fce3-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="0fce3-129">Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.</span><span class="sxs-lookup"><span data-stu-id="0fce3-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="0fce3-p103">Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fce3-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

