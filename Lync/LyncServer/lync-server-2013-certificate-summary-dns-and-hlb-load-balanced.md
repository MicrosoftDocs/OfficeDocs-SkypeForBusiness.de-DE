---
title: 'Lync Server 2013: Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="09d02-102">Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09d02-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09d02-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="09d02-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="09d02-104">Die Zertifikatanforderungen für einen Director mit DNS-Lastenausgleich und einem Hardware Lastenausgleichsmodul verwenden ein Standardzertifikat, das einen Antragstellernamen und einen alternativen Betreff für Dienste enthält, die der Director empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="09d02-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="09d02-105">Für jeden Director im Pool wird ein Zertifikat angefordert.</span><span class="sxs-lookup"><span data-stu-id="09d02-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="09d02-106">Beachten Sie, dass der Hardwarelastenausgleich nur den Datenverkehr vom Reverseproxy abgleicht.</span><span class="sxs-lookup"><span data-stu-id="09d02-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="09d02-107">Darüber hinaus gibt es ein OAuth-Token Zertifikat für Server-zu-Server-Authentifizierungszwecke, das auf jedem Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="09d02-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="09d02-108">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="09d02-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09d02-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="09d02-109">Component</span></span></th>
<th><span data-ttu-id="09d02-110">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="09d02-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="09d02-111">Subject Alternative Names (San)</span><span class="sxs-lookup"><span data-stu-id="09d02-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="09d02-112">Kommentare</span><span class="sxs-lookup"><span data-stu-id="09d02-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09d02-113">Standard</span><span class="sxs-lookup"><span data-stu-id="09d02-113">Default</span></span></p></td>
<td><p><span data-ttu-id="09d02-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="09d02-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="09d02-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="09d02-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="09d02-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="09d02-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="09d02-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09d02-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="09d02-118">Meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09d02-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="09d02-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09d02-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="09d02-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09d02-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="09d02-121">(Optional) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="09d02-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="09d02-122">Director-Zertifikate können entweder von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="09d02-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="09d02-123">Der Director antwortet auf Anforderungen vom Reverse-Proxy im Umkreis oder vom Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="09d02-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="09d02-124">Interne Clients verwenden den Director nicht.</span><span class="sxs-lookup"><span data-stu-id="09d02-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="09d02-125">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="09d02-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09d02-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="09d02-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="09d02-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="09d02-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="09d02-128">Kein Eintrag</span><span class="sxs-lookup"><span data-stu-id="09d02-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="09d02-129">Beachten Sie, dass die minimale Schlüssellänge 1024 ist, aber möglicherweise eine Warnung angezeigt wird, dass die empfohlene Mindestlänge von 2048 Bits beträgt.</span><span class="sxs-lookup"><span data-stu-id="09d02-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="09d02-130">Das OAuthTokenIssuer-Zertifikat ist ein Single-Purpose-Zertifikat zum Zweck der Authentifizierung von Servern in einer großen Umgebung und kann von einer internen Zertifizierungsstelle oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="09d02-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="09d02-131">Das Zertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="09d02-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

