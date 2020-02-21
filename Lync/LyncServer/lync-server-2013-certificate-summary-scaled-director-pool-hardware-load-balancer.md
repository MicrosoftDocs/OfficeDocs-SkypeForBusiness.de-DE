---
title: Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fed49b1174260e29f6badc4a3f994f888c1a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="a172e-102">Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a172e-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a172e-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a172e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a172e-104">Zertifikatanforderungen für einen Director mit einem Hardwaregerät zum Lastenausgleich verwenden ein Standardzertifikat, das über einen Antragstellernamen und alternative Antragstellernamen für Dienste verfügt, die der Directorpool empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="a172e-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="a172e-105">Ein Zertifikat wird für jeden Director im Pool angefordert.</span><span class="sxs-lookup"><span data-stu-id="a172e-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="a172e-106">Darüber hinaus ist ein OAuth-Tokenzertifikat für die Authentifizierung zwischen Servern verfügbar, das auf jedem Server installiert wird.</span><span class="sxs-lookup"><span data-stu-id="a172e-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="a172e-107">Zertifikate für einen skalierten Director mit einem Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="a172e-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a172e-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="a172e-108">Component</span></span></th>
<th><span data-ttu-id="a172e-109">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="a172e-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="a172e-110">Alternative Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="a172e-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="a172e-111">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a172e-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a172e-112">Standard</span><span class="sxs-lookup"><span data-stu-id="a172e-112">Default</span></span></p></td>
<td><p><span data-ttu-id="a172e-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a172e-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a172e-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a172e-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="a172e-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a172e-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="a172e-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a172e-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a172e-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a172e-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="a172e-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a172e-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="a172e-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a172e-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="a172e-120">(Optional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a172e-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a172e-121">Director-Zertifikate können von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a172e-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="a172e-122">Der Director antwortet auf Anfragen vom Reverseproxy im Umkreis oder von der Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a172e-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="a172e-123">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="a172e-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a172e-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="a172e-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="a172e-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a172e-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a172e-126">Kein Eintrag</span><span class="sxs-lookup"><span data-stu-id="a172e-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="a172e-127">Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.</span><span class="sxs-lookup"><span data-stu-id="a172e-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="a172e-p102">Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a172e-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

