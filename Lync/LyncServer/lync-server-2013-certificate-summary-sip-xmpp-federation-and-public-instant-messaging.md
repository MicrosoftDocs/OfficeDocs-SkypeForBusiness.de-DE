---
title: Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517872"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="c9a23-102">Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9a23-103">_**Letztes Änderungsstand des Themas:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="c9a23-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="c9a23-104">Die Zertifikate, die Sie für die Zusammenfassung mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server benötigen, werden normalerweise von den Zertifikaten erfüllt, die Sie konfigurieren, anfordern und Ihrem Edgeserver zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9a23-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="c9a23-105">Die Zertifikatanforderungen für das Aktivieren und Einrichten von Kommunikation mit XMPP-Partnern (Extensible Messaging and Presence Protocol) erfordern das Hinzufügen von Einträgen für Ihre XMPP-Domänen.</span><span class="sxs-lookup"><span data-stu-id="c9a23-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="c9a23-106">Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="c9a23-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="c9a23-107">Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9a23-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="c9a23-108">Wenn Sie Zertifikate für die Verbindung mit öffentlichen Instant Messaging-Diensten konfigurieren möchten, beachten Sie, dass es nichts anderes als andere SIP-Verbundtypen oder sogar Standard Edgeserver Zertifikate gibt, es sei denn, dass America Online (AOL) ein Zertifikat oder Zertifikate (im Fall eines Edgepools) benötigt, die auch den Client-EKU enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9a23-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="c9a23-109">Die EKU des Clients ist eine Ergänzung des Zertifikats und ist Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c9a23-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="c9a23-110">Um zu bestätigen, dass Sie die richtigen Zertifikatanforderungen für Ihre Edgeserver-Bereitstellung erfüllt haben, lesen Sie die im Abschnitt **Siehe auch**aufgeführten Themen.</span><span class="sxs-lookup"><span data-stu-id="c9a23-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9a23-111">Komponente</span><span class="sxs-lookup"><span data-stu-id="c9a23-111">Component</span></span></th>
<th><span data-ttu-id="c9a23-112">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="c9a23-112">Subject name</span></span></th>
<th><span data-ttu-id="c9a23-113">Alternative Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="c9a23-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="c9a23-114">Kommentare</span><span class="sxs-lookup"><span data-stu-id="c9a23-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9a23-115">Externer Edgeserver/Zugriffsedge</span><span class="sxs-lookup"><span data-stu-id="c9a23-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="c9a23-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9a23-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="c9a23-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="c9a23-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="c9a23-120">Zur Unterstützung des contoso.com XMPP-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c9a23-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="c9a23-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="c9a23-122">So unterstützen Sie den fabrikam.com-SIP-Namespace</span><span class="sxs-lookup"><span data-stu-id="c9a23-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="c9a23-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c9a23-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="c9a23-124">Zur Unterstützung des fabrikam.com XMPP-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c9a23-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="c9a23-125">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn die Verbindung mit AOL mit öffentlichen Instant Messaging-Diensten bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9a23-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="c9a23-126">Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="c9a23-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9a23-127">Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c9a23-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="c9a23-128">Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c9a23-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="c9a23-129">A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c9a23-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="c9a23-130">In technischer Hinsicht wird dem a/V-Edge kein Zertifikat zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c9a23-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="c9a23-131">Die sichere Kommunikation und Authentifizierung wird über den Media Relay-Authentifizierungsdienst (MRAS) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c9a23-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="c9a23-132">MRAS verwendet das Zertifikat, das der internen Edgeserver-Schnittstelle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c9a23-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="c9a23-p105">Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c9a23-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9a23-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9a23-136">See Also</span></span>


[<span data-ttu-id="c9a23-137">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="c9a23-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="c9a23-138">Planen von Edgeserver Zertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="c9a23-139">Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="c9a23-140">Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="c9a23-141">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="c9a23-142">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="c9a23-143">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9a23-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

