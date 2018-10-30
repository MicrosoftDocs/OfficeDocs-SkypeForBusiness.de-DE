---
title: Zertifikatzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten
TOCTitle: Zertifikatzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49293514
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum Konfigurieren von Zertifikaten für die Verbindung mit öffentlichen Chatdiensten sollten Sie zunächst beachten, dass es keinen Unterschied zu anderen SIP-Partnerverbundtypen oder sogar Edgeserver-Standardzertifikaten gibt, außer dass für America Online (AOL) eine spezielle Zertifikatkonfiguration erforderlich ist. Neben der normalen erweiterten Schlüsselverwendung (EKU) für Server muss das Zertifikat oder die Zertifikate (im Fall eines Edgepools) für America Online auch die Client-EKU enthalten. Die Client-EKU ist eine Ergänzung zum Zertifikat und Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserverzugewiesen ist.

## Zertifikatzusammenfassung – Verbindung mit öffentlichem Chatdienst


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
<th>Alternative Antragstellernamen (SANs)/Reihenfolge</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extern/Zugriffsedge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und Client-EKU verfügen, wenn eine Verbindung mit einem öffentlichen Chatdienst mit AOL bereitgestellt werden soll. Das Zertifikat wird den externen Edgeserver-Schnittstellen für folgende Dienste zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<p>Beachten Sie, dass SANs dem Zertifikat automatisch basierend auf Ihren Definitionen im Topologie-Generator hinzugefügt werden. Bei Bedarf können Sie SAN-Einträge für weitere SIP-Domänen und andere Einträge hinzufügen, die Sie unterstützen müssen. Der Antragstellername wird im SAN repliziert und muss für den korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

