---
title: 'Lync Server 2013: Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="017c6-102">Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017c6-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="017c6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="017c6-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="017c6-104">Wenn Sie Zertifikate für die öffentliche Instant Messaging-Konnektivität konfigurieren möchten, sollten Sie zuerst feststellen, dass sich nichts von anderen SIP Federation-Typen oder sogar Standard-Edgeserver-Zertifikaten unterscheidet, es sei denn, dass America Online (AOL) eine eindeutige Zertifikatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="017c6-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="017c6-105">Neben der üblichen Server-Erweiterte Schlüsselverwendung (EKU) erfordert America Online, dass das Zertifikat oder die Zertifikate (im Fall eines Edge-Pools) auch die Client-EKU enthalten.</span><span class="sxs-lookup"><span data-stu-id="017c6-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="017c6-106">Die Client-EKU ist eine Ergänzung zum Zertifikat und Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="017c6-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="017c6-107">Zusammenfassung des Zertifikats – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="017c6-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="017c6-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="017c6-108">Component</span></span></th>
<th><span data-ttu-id="017c6-109">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="017c6-109">Subject name</span></span></th>
<th><span data-ttu-id="017c6-110">Subject Alternative Names (San)/Order</span><span class="sxs-lookup"><span data-stu-id="017c6-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="017c6-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="017c6-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="017c6-112">Extern/Access-Edge</span><span class="sxs-lookup"><span data-stu-id="017c6-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="017c6-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="017c6-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="017c6-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="017c6-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="017c6-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="017c6-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="017c6-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="017c6-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="017c6-117">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="017c6-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="017c6-118">Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="017c6-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="017c6-119">Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="017c6-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="017c6-120">Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="017c6-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="017c6-121">A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="017c6-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="017c6-122">Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="017c6-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="017c6-123">Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="017c6-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="017c6-124">Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="017c6-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="017c6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="017c6-125">See Also</span></span>


[<span data-ttu-id="017c6-126">Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017c6-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

