---
title: Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aede53e06493fab89a843ccc2de543aed7f05dae
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5de89-102">Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de89-103">_**Letztes Änderungsdatum des Themas:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="5de89-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="5de89-104">Die Zertifikate, die Sie für die Föderation mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server benötigen, werden in der Regel von den Zertifikaten erfüllt, die Sie konfigurieren, anfordern und Ihrem Edgeserver zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5de89-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="5de89-105">Für die Zertifikatanforderungen für die Aktivierung und Einrichtung der Kommunikation mit dem Extensible Messaging and Presence Protocol (XMPP)-Partner müssen Einträge für Ihre XMPP-Domänen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5de89-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="5de89-106">Der Datensatz, der im Zertifikat als alternativer Betreff (Subject Alternative Name, San) enthalten ist, ist die Domäne, die an der XMPP-Kommunikation teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="5de89-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="5de89-107">Bei der Domäne kann es sich um die Domäne auf Stammebene (beispielsweise contoso.com) handeln, wenn Sie XMPP für Ihre gesamte Domäne aktivieren möchten oder untergeordnete Domänen (beispielsweise Corp.contoso.com, Finance.contoso.com) ausgewählt werden können, wenn Sie XMPP für eine Teilmenge der Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5de89-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="5de89-108">Wenn Sie Zertifikate für die öffentliche Instant Messaging-Konnektivität konfigurieren möchten, beachten Sie, dass sich nichts von anderen SIP-Verbundtypen oder sogar Standard-Edgeserver-Zertifikaten unterscheidet, es sei denn, dass für America Online (AOL) ein Zertifikat oder Zertifikate erforderlich ist (in der Fall eines Edge-Pools), der auch die Client-EKU enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="5de89-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="5de89-109">Die Client-EKU ist eine Ergänzung zum Zertifikat und Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5de89-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="5de89-110">Um zu bestätigen, dass Sie die richtigen Zertifikatanforderungen für Ihre Edge-Server-Bereitstellung erfüllt haben, überprüfen Sie die Themen, die im Abschnitt **Siehe auch**aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="5de89-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="5de89-111">Komponente</span><span class="sxs-lookup"><span data-stu-id="5de89-111">Component</span></span></th>
<th><span data-ttu-id="5de89-112">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="5de89-112">Subject name</span></span></th>
<th><span data-ttu-id="5de89-113">Subject Alternative Names (San)</span><span class="sxs-lookup"><span data-stu-id="5de89-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="5de89-114">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5de89-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5de89-115">Extern/Access-Edge</span><span class="sxs-lookup"><span data-stu-id="5de89-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="5de89-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5de89-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5de89-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5de89-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="5de89-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5de89-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="5de89-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5de89-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="5de89-120">So unterstützen Sie den contoso.com XMPP-Namespace</span><span class="sxs-lookup"><span data-stu-id="5de89-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="5de89-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5de89-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="5de89-122">So unterstützen Sie den fabrikam.com-SIP-Namespace</span><span class="sxs-lookup"><span data-stu-id="5de89-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="5de89-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5de89-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="5de89-124">So unterstützen Sie den fabrikam.com XMPP-Namespace</span><span class="sxs-lookup"><span data-stu-id="5de89-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="5de89-125">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5de89-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="5de89-126">Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="5de89-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="5de89-127">Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5de89-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="5de89-128">Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5de89-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="5de89-129">A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5de89-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="5de89-130">Technisch wird dem a/V-Rand kein Zertifikat zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5de89-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="5de89-131">Die sichere Kommunikation und Authentifizierung wird über den Media Relay Authentication Service (MRAS) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5de89-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="5de89-132">MRAS verwendet das Zertifikat, das der internen Schnittstelle des Edge-Servers zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5de89-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="5de89-133">Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5de89-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="5de89-134">Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="5de89-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="5de89-135">Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="5de89-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5de89-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5de89-136">See Also</span></span>


[<span data-ttu-id="5de89-137">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="5de89-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="5de89-138">Planen von Edgeserver-Zertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="5de89-139">Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="5de89-140">Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="5de89-141">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="5de89-142">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="5de89-143">Zertifikatzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de89-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

