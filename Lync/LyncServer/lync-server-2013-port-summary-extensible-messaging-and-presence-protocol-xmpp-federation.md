---
title: Port Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
description: Port Summary – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543091"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="5d7db-103">Port Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7db-103">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d7db-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5d7db-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5d7db-105">Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation zwischen dem XMPP-Verbundpartner und der Edgeserver und erlauben auch die Kommunikation von Ihrem Edgeserver zum XMPP-Verbundpartner.</span><span class="sxs-lookup"><span data-stu-id="5d7db-105">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="5d7db-106">Eine Regel wird auch in der internen Firewall aus dem Front-End-Server oder Front-End-Pool zum Edgeserver oder Edgepool definiert.</span><span class="sxs-lookup"><span data-stu-id="5d7db-106">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="5d7db-107">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="5d7db-107">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d7db-108">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5d7db-108">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5d7db-109">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5d7db-109">Source (IP address)</span></span></th>
<th><span data-ttu-id="5d7db-110">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5d7db-110">Destination (IP address)</span></span></th>
<th><span data-ttu-id="5d7db-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5d7db-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d7db-112">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5d7db-112">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5d7db-113">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5d7db-113">Any</span></span></p></td>
<td><p><span data-ttu-id="5d7db-114">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d7db-114">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5d7db-115">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5d7db-115">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5d7db-116">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="5d7db-116">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d7db-117">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5d7db-117">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5d7db-118">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d7db-118">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5d7db-119">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5d7db-119">Any</span></span></p></td>
<td><p><span data-ttu-id="5d7db-120">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5d7db-120">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5d7db-121">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="5d7db-121">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d7db-122">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="5d7db-122">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="5d7db-123">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5d7db-123">Any</span></span></p></td>
<td><p><span data-ttu-id="5d7db-124">Interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="5d7db-124">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="5d7db-125">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zum Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5d7db-125">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d7db-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d7db-126">See Also</span></span>


[<span data-ttu-id="5d7db-127">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="5d7db-127">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="5d7db-128">Verwalten von XMPP-Verbundpartnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7db-128">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

