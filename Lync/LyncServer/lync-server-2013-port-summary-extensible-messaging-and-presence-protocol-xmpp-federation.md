---
title: Port Zusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e8e58-102">Port Zusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e58-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8e58-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e8e58-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e8e58-104">Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation vom XMPP-Partner zum Edgeserver und ermöglichen auch die Kommunikation von Ihrem Edgeserver zur xmpp. Federated-Partner.</span><span class="sxs-lookup"><span data-stu-id="e8e58-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="e8e58-105">Eine Regel wird auch für die interne Firewall vom Front-End-Server oder Front-End-Pool für den Edge-Server oder den Edge-Pool definiert.</span><span class="sxs-lookup"><span data-stu-id="e8e58-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e8e58-106">Zusammenfassung der Firewall für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="e8e58-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8e58-107">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e8e58-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e8e58-108">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="e8e58-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="e8e58-109">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="e8e58-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e8e58-110">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e8e58-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8e58-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e8e58-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e8e58-112">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e8e58-112">Any</span></span></p></td>
<td><p><span data-ttu-id="e8e58-113">Access Edge Service Interface-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8e58-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e8e58-114">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="e8e58-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e8e58-115">Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="e8e58-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8e58-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e8e58-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e8e58-117">Access Edge Service Interface-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8e58-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e8e58-118">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e8e58-118">Any</span></span></p></td>
<td><p><span data-ttu-id="e8e58-119">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="e8e58-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e8e58-120">Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</span><span class="sxs-lookup"><span data-stu-id="e8e58-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8e58-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="e8e58-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="e8e58-122">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e8e58-122">Any</span></span></p></td>
<td><p><span data-ttu-id="e8e58-123">Interne Edge-Server-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="e8e58-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e8e58-124">Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zum Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e8e58-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8e58-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8e58-125">See Also</span></span>


[<span data-ttu-id="e8e58-126">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="e8e58-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="e8e58-127">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e58-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

