---
title: Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
description: Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten.
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
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572141"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-15_

Die Zertifikate, die Sie für die Zusammenfassung mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server benötigen, werden normalerweise von den Zertifikaten erfüllt, die Sie konfigurieren, anfordern und Ihrem Edgeserver zuweisen.

Die Zertifikatanforderungen für das Aktivieren und Einrichten von Kommunikation mit XMPP-Partnern (Extensible Messaging and Presence Protocol) erfordern das Hinzufügen von Einträgen für Ihre XMPP-Domänen. Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann. Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.

Wenn Sie Zertifikate für die Verbindung mit öffentlichen Instant Messaging-Diensten konfigurieren möchten, beachten Sie, dass es nichts anderes als andere SIP-Verbundtypen oder sogar Standard Edgeserver Zertifikate gibt, es sei denn, dass America Online (AOL) ein Zertifikat oder Zertifikate (im Fall eines Edgepools) benötigt, die auch den Client-EKU enthalten. Die EKU des Clients ist eine Ergänzung des Zertifikats und ist Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.

Um zu bestätigen, dass Sie die richtigen Zertifikatanforderungen für Ihre Edgeserver-Bereitstellung erfüllt haben, lesen Sie die im Abschnitt **Siehe auch**aufgeführten Themen.

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
<th>Komponente</th>
<th>Antragstellername</th>
<th>Alternative Antragstellernamen</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer Edgeserver/Zugriffsedge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Zur Unterstützung des contoso.com XMPP-Namespaces


<p>sip.fabrikam.com</p>



> [!NOTE]
> So unterstützen Sie den fabrikam.com-SIP-Namespace


<p>fabrikam.com</p>



> [!NOTE]
> Zur Unterstützung des fabrikam.com XMPP-Namespaces

</td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn die Verbindung mit AOL mit öffentlichen Instant Messaging-Diensten bereitgestellt werden soll. Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>



> [!NOTE]
> In technischer Hinsicht wird dem a/V-Edge kein Zertifikat zugewiesen. Die sichere Kommunikation und Authentifizierung wird über den Media Relay-Authentifizierungsdienst (MRAS) verwaltet. MRAS verwendet das Zertifikat, das der internen Edgeserver-Schnittstelle zugewiesen ist.


<p>Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT in lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

