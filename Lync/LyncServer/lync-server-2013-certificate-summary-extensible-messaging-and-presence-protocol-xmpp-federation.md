---
title: 'Lync Server 2013: Zertifikatzusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)'
description: 'Lync Server 2013: Zertifikatzusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572341"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="1963d-103">Zertifikatzusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1963d-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1963d-104">_**Letztes Änderungsstand des Themas:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="1963d-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="1963d-p101">Zertifikatsanforderungen für das Aktivieren und Einrichten von Kommunikationen mit XMPP-Partnern (Extensible Messaging and Presence Protocol) erfordern den zusätzlichen Eintrag in Ihren XMPP-Domänen. Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann. Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1963d-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1963d-108">Zertifikatzusammenfassung für XMPP</span><span class="sxs-lookup"><span data-stu-id="1963d-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1963d-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="1963d-109">Component</span></span></th>
<th><span data-ttu-id="1963d-110">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="1963d-110">Subject name</span></span></th>
<th><span data-ttu-id="1963d-111">Alternative Antragstellernamen (SAN)/Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="1963d-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="1963d-112">Kommentare</span><span class="sxs-lookup"><span data-stu-id="1963d-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1963d-113">Zuweisen zu Zugriffs-Edgedienst von Edgeserver oder Edgepool</span><span class="sxs-lookup"><span data-stu-id="1963d-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="1963d-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1963d-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1963d-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1963d-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="1963d-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1963d-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="1963d-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1963d-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="1963d-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1963d-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1963d-119">Die ersten drei San-Einträge sind die normalen San-Einträge für eine vollständige Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="1963d-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="1963d-120">"contoso.com" ist der erforderliche Eintrag für den Partnerverbund mit dem XMPP-Partner auf Stammdomänenebene.</span><span class="sxs-lookup"><span data-stu-id="1963d-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="1963d-121">In diesem Eintrag wird XMPP für alle Domänen mit dem Suffix contoso.com zugelassen.</span><span class="sxs-lookup"><span data-stu-id="1963d-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1963d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1963d-122">See Also</span></span>


[<span data-ttu-id="1963d-123">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="1963d-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="1963d-124">Planen von Edgeserver Zertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1963d-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="1963d-125">Einrichten von Edge-Zertifikaten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1963d-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="1963d-126">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1963d-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="1963d-127">Gruppe-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1963d-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

