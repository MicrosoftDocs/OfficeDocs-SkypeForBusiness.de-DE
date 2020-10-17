---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen einzelnen Director'
description: 'Lync Server 2013: Zertifikatzusammenfassung für einen einzelnen Director.'
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
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572161"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="7b8d2-103">Zertifikatzusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b8d2-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b8d2-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7b8d2-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7b8d2-105">Die Zertifikatanforderungen für einen einzelnen Director bestehen aus einem Standardzertifikat, das einen Antragstellernamen und alternative Antragstellernamen für Dienste aufweist, die der Director erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="7b8d2-106">Darüber hinaus steht ein Zertifikat für OAuth-Token für die Authentifizierung zwischen Servern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="7b8d2-107">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="7b8d2-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b8d2-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="7b8d2-108">Component</span></span></th>
<th><span data-ttu-id="7b8d2-109">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="7b8d2-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="7b8d2-110">Alternative Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="7b8d2-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="7b8d2-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="7b8d2-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b8d2-112">Standard</span><span class="sxs-lookup"><span data-stu-id="7b8d2-112">Default</span></span></p></td>
<td><p><span data-ttu-id="7b8d2-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b8d2-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b8d2-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b8d2-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="7b8d2-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b8d2-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7b8d2-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b8d2-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="7b8d2-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b8d2-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="7b8d2-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b8d2-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="7b8d2-119">(Optional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b8d2-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b8d2-120">Director-Zertifikate können von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="7b8d2-121">Der Director antwortet auf Anfragen vom Reverseproxy im Umkreis oder von der Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="7b8d2-122">Für interne Clients wird der Director nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="7b8d2-123">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="7b8d2-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b8d2-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="7b8d2-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="7b8d2-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b8d2-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b8d2-126">Kein Eintrag</span><span class="sxs-lookup"><span data-stu-id="7b8d2-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="7b8d2-127">Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="7b8d2-p103">Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b8d2-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

