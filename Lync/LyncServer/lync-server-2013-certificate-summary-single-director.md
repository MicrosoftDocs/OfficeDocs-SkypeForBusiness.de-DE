---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen einzelnen Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3b1e9963d88a7876232219a8d4f2290c2c9cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c5cb6-102">Zertifikatzusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5cb6-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5cb6-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c5cb6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c5cb6-104">Die Zertifikatanforderungen für einen einzelnen Director bestehen aus einem Standardzertifikat, das einen Antragstellernamen und alternative Antragstellernamen für Dienste aufweist, die der Director erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="c5cb6-105">Darüber hinaus steht ein Zertifikat für OAuth-Token für die Authentifizierung zwischen Servern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="c5cb6-106">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="c5cb6-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5cb6-107">Komponente</span><span class="sxs-lookup"><span data-stu-id="c5cb6-107">Component</span></span></th>
<th><span data-ttu-id="c5cb6-108">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="c5cb6-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="c5cb6-109">Alternative Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="c5cb6-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="c5cb6-110">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c5cb6-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5cb6-111">Standard</span><span class="sxs-lookup"><span data-stu-id="c5cb6-111">Default</span></span></p></td>
<td><p><span data-ttu-id="c5cb6-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c5cb6-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c5cb6-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c5cb6-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="c5cb6-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5cb6-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="c5cb6-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5cb6-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="c5cb6-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5cb6-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="c5cb6-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5cb6-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="c5cb6-118">(Optional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5cb6-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5cb6-119">Director-Zertifikate können von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="c5cb6-120">Der Director antwortet auf Anfragen vom Reverseproxy im Umkreis oder von der Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="c5cb6-121">Für interne Clients wird der Director nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="c5cb6-122">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="c5cb6-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5cb6-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="c5cb6-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="c5cb6-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c5cb6-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c5cb6-125">Kein Eintrag</span><span class="sxs-lookup"><span data-stu-id="c5cb6-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="c5cb6-126">Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="c5cb6-p103">Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

