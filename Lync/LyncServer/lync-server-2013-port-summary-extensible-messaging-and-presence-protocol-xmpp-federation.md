---
title: Port Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
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
ms.openlocfilehash: ebb2eb7695cfcc3b1ed6166f7768128dc48fb8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="725ad-102">Port Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725ad-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="725ad-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="725ad-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="725ad-104">Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation vom XMPP-Verbundpartner zum Edgeserver und erlauben auch die Kommunikation von Ihrem Edgeserver zur xmpp. Verbundpartner.</span><span class="sxs-lookup"><span data-stu-id="725ad-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="725ad-105">Eine Regel wird auch in der internen Firewall aus dem Front-End-Server oder Front-End-Pool zum Edgeserver oder Edgepool definiert.</span><span class="sxs-lookup"><span data-stu-id="725ad-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="725ad-106">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="725ad-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="725ad-107">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="725ad-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="725ad-108">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="725ad-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="725ad-109">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="725ad-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="725ad-110">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="725ad-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="725ad-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="725ad-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="725ad-112">Any</span><span class="sxs-lookup"><span data-stu-id="725ad-112">Any</span></span></p></td>
<td><p><span data-ttu-id="725ad-113">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="725ad-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="725ad-114">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="725ad-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="725ad-115">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="725ad-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="725ad-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="725ad-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="725ad-117">IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="725ad-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="725ad-118">Any</span><span class="sxs-lookup"><span data-stu-id="725ad-118">Any</span></span></p></td>
<td><p><span data-ttu-id="725ad-119">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="725ad-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="725ad-120">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="725ad-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="725ad-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="725ad-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="725ad-122">Any</span><span class="sxs-lookup"><span data-stu-id="725ad-122">Any</span></span></p></td>
<td><p><span data-ttu-id="725ad-123">Interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="725ad-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="725ad-124">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zum Edgeserver</span><span class="sxs-lookup"><span data-stu-id="725ad-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="725ad-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="725ad-125">See Also</span></span>


[<span data-ttu-id="725ad-126">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="725ad-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="725ad-127">Verwalten von XMPP-Verbundpartnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725ad-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

