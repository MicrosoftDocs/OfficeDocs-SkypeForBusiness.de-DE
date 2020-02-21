---
title: DNS-Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 688438e07416895f5c8070830e4bc0467325de14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="4935d-102">DNS-Zusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4935d-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4935d-103">_**Letztes Änderungsstand des Themas:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="4935d-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="4935d-104">Zum Konfigurieren von xmpp (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei Domain Name System (DNS)-Datensätze auf einem externen DNS-Server, mit dem die Datensätze in den Zugriffs-Edgedienst Ihres Edgeserver oder Edgepool aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4935d-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4935d-105">DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="4935d-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4935d-106">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="4935d-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4935d-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="4935d-107">FQDN</span></span></th>
<th><span data-ttu-id="4935d-108">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="4935d-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4935d-109">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="4935d-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4935d-110">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="4935d-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="4935d-111">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4935d-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4935d-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4935d-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4935d-113">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie diese Schritte bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf den Lync-aktivierter Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4935d-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="4935d-114">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4935d-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="4935d-115">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="4935d-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4935d-116">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="4935d-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4935d-117">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="4935d-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="4935d-118">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="4935d-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="4935d-119">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="4935d-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="4935d-120">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="4935d-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4935d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4935d-121">See Also</span></span>


[<span data-ttu-id="4935d-122">Einrichten des XMPP-Verbunds in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4935d-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="4935d-123">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4935d-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

