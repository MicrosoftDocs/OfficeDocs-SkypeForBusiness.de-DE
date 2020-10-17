---
title: 'Lync Server 2013: Zertifikatzusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512782"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="5190c-102">Zertifikatzusammenfassung für die Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5190c-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5190c-103">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="5190c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="5190c-104">Um Zertifikate für die Verbindung mit öffentlichen Instant Messaging-Diensten zu konfigurieren, sollten Sie zunächst bemerken, dass es nichts anderes als andere SIP-Verbundtypen oder sogar Standard Edgeserver Zertifikate gibt, es sei denn, dass America Online (AOL) eine eindeutige Zertifikatkonfiguration erfordert.</span><span class="sxs-lookup"><span data-stu-id="5190c-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="5190c-105">Zusätzlich zur üblichen Server Enhanced Key Usage (EKU) erfordert America Online, dass das Zertifikat oder die Zertifikate (im Fall eines Edgepool) auch den Client-EKU enthalten.</span><span class="sxs-lookup"><span data-stu-id="5190c-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="5190c-106">Die EKU des Clients ist eine Ergänzung des Zertifikats und ist Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5190c-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5190c-107">Zertifikatzusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="5190c-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5190c-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="5190c-108">Component</span></span></th>
<th><span data-ttu-id="5190c-109">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="5190c-109">Subject name</span></span></th>
<th><span data-ttu-id="5190c-110">Alternative Antragstellernamen (SAN)/Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="5190c-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="5190c-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5190c-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5190c-112">Externer Edgeserver/Zugriffsedge</span><span class="sxs-lookup"><span data-stu-id="5190c-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="5190c-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5190c-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5190c-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5190c-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="5190c-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5190c-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="5190c-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5190c-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5190c-117">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn die Verbindung mit AOL mit öffentlichen Instant Messaging-Diensten bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5190c-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="5190c-118">Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="5190c-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="5190c-119">Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5190c-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="5190c-120">Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5190c-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="5190c-121">A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5190c-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="5190c-p103">Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="5190c-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5190c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5190c-125">See Also</span></span>


[<span data-ttu-id="5190c-126">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5190c-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

