---
title: Zertifikatzusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatdienste
TOCTitle: Zertifikatzusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatdienste
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49294772
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatdienste

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die für den Partnerverbund mit Microsoft Lync Server 2013, Lync Server 2010 und Office Communications Server benötigten Zertifikate werden normalerweise durch die Zertifikate abgedeckt, die Sie für Ihren Edgeserver konfigurieren, anfordern und diesem zuweisen.

Für Zertifikatanforderungen zum Aktivieren und Einrichten von Kommunikationen mit XMPP-Partnern (Extensible Messaging and Presence Protocol) sind zusätzliche Einträge für Ihre XMPP-Domänen erforderlich. Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann. Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.

Beachten Sie beim Konfigurieren von Zertifikaten für die Verbindung mit öffentlichen Chatdiensten, dass kein Unterschied zu anderen SIP-Partnerverbundtypen oder sogar Edgeserver-Standardzertifikaten besteht, mit Ausnahme von AOL (America Online), für die das Zertifikat bzw. die Zertifikate (im Fall eines Edgepools) außerdem die Client-EKU enthalten muss. Die Client-EKU ist ein Zusatz zum Zertifikat und stellt einen Teil des externen öffentlichen Zertifikats dar, das Ihrem Edgeserver zugewiesen ist.

Ob Sie die Zertifikatanforderungen für Ihre Edgeserver-Bereitstellung erfüllen, erfahren Sie in den Themen im Abschnitt **Siehe auch**.



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Komponenten</th>
<th>Antragstellername</th>
<th>Alternative Antragstellernamen</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extern/Zugriffsedge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>
<div>

> [!NOTE]
> Zur Unterstützung des contoso.com-XMPP-Namespaces


</div>
<p>sip.fabrikam.com</p>
<div>

> [!NOTE]
> Zur Unterstützung des fabrikam.com-SIP-Namespaces


</div>
<p>fabrikam.com</p>
<div>

> [!NOTE]
> Zur Unterstützung des fabrikam.com-XMPP-Namespaces


</div></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und Client-EKU verfügen, wenn eine Verbindung mit einem öffentlichen Chatdienst mit AOL bereitgestellt werden soll. Das Zertifikat wird den externen Edgeserver-Schnittstellen für folgende Dienste zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<div>

> [!NOTE]
> Technisch gesehen, wird dem A/V Edge kein Zertifikat zugewiesen. Die sichere Kommunikation und Authentifizierung wird mithilfe von MRAS (Media Relay Authentication Service, Authentifizierungsdienst für Medienrelay) verwaltet. MRAS verwendet das Zertifikat, das der internen Edgeserver-Schnittstelle zugeordnet ist.


</div>
<p>Beachten Sie, dass SANs basierend auf Ihren Definitionen im Topologie-Generator automatisch dem Zertifikat hinzugefügt werden. Sie fügen SAN-Einträge bei Bedarf für zusätzliche SIP-Domänen und sonstige Einträge, die unterstützt werden müssen, hinzu. Der Antragstellername wird im SAN repliziert und muss für den ordnungsgemäßen Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Aufgaben

[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Konzepte

[Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Zertifikatzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

