---
title: Portanforderungen für lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584d1c8391f0393711b2caf6de46a0df6c437c51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="053a0-102">Port Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="053a0-103">_**Letztes Änderungsdatum des Themas:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="053a0-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="053a0-104">Für lync Server ist es erforderlich, dass bestimmte Ports der Firewall geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="053a0-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="053a0-105">Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="053a0-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="053a0-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="053a0-106">In This Section</span></span>

<span data-ttu-id="053a0-107">Dieser Abschnitt enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="053a0-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="053a0-108">Ports und Protokolle für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="053a0-109">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="053a0-110">Portzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="053a0-111">Portzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="053a0-112">Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="053a0-113">Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="053a0-114">Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="053a0-115">Portzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="053a0-116">Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="053a0-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

