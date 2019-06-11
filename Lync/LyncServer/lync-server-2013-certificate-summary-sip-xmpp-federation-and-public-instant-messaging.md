---
title: Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dccb46b9f2b6d934f1cd0960bb11a369fb585ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-15_

Die Zertifikate, die Sie für die Föderation mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server benötigen, werden in der Regel von den Zertifikaten erfüllt, die Sie konfigurieren, anfordern und Ihrem Edgeserver zuweisen.

Für die Zertifikatanforderungen für die Aktivierung und Einrichtung der Kommunikation mit dem Extensible Messaging and Presence Protocol (XMPP)-Partner müssen Einträge für Ihre XMPP-Domänen hinzugefügt werden. Der Datensatz, der im Zertifikat als alternativer Betreff (Subject Alternative Name, San) enthalten ist, ist die Domäne, die an der XMPP-Kommunikation teilnehmen kann. Bei der Domäne kann es sich um die Domäne auf Stammebene (beispielsweise contoso.com) handeln, wenn Sie XMPP für Ihre gesamte Domäne aktivieren möchten oder untergeordnete Domänen (beispielsweise Corp.contoso.com, Finance.contoso.com) ausgewählt werden können, wenn Sie XMPP für eine Teilmenge der Benutzer aktivieren.

Wenn Sie Zertifikate für die öffentliche Instant Messaging-Konnektivität konfigurieren möchten, beachten Sie, dass sich nichts von anderen SIP-Verbundtypen oder sogar Standard-Edgeserver-Zertifikaten unterscheidet, es sei denn, dass für America Online (AOL) ein Zertifikat oder Zertifikate erforderlich ist (in der Fall eines Edge-Pools), der auch die Client-EKU enthalten soll. Die Client-EKU ist eine Ergänzung zum Zertifikat und Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.

Um zu bestätigen, dass Sie die richtigen Zertifikatanforderungen für Ihre Edge-Server-Bereitstellung erfüllt haben, überprüfen Sie die Themen, die im Abschnitt **Siehe auch**aufgeführt sind.

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
<th>Name des Antragstellers</th>
<th>Subject Alternative Names (San)</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extern/Access-Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> So unterstützen Sie den contoso.com XMPP-Namespace


<p>sip.fabrikam.com</p>



> [!NOTE]
> So unterstützen Sie den fabrikam.com-SIP-Namespace


<p>fabrikam.com</p>



> [!NOTE]
> So unterstützen Sie den fabrikam.com XMPP-Namespace

</td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen. Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>



> [!NOTE]
> Technisch wird dem a/V-Rand kein Zertifikat zugewiesen. Die sichere Kommunikation und Authentifizierung wird über den Media Relay Authentication Service (MRAS) verwaltet. MRAS verwendet das Zertifikat, das der internen Schnittstelle des Edge-Servers zugewiesen ist.


<p>Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden. Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu. Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

