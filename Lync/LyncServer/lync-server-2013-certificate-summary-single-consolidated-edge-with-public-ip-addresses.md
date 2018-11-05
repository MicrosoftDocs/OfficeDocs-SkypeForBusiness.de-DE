---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen'
TOCTitle: Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204747(v=OCS.15)
ms:contentKeyID: 49293452
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Microsoft Lync Server 2013 verwendet Zertifikate zum gegenseitigen Authentifizieren von Servern und zum Verschlüsseln von Daten zwischen Servern sowie zwischen Server und Client. Bei Zertifikaten müssen die Namen der DNS-Einträge (Domain Name System), die den Servern zugeordnet sind, sowie der Antragstellername (Subject Name, SN) und der alternative Antragstellername (Subject Alternative Name, SAN) im Zertifikat übereinstimmen. Für die erfolgreiche Zuordnung von Servern, DNS-Einträgen und Zertifikateinträgen müssen Sie die vollqualifizierten Domänennamen des vorgesehenen Servers wie im DNS und in den SN- und SAN-Einträgen im Zertifikat registriert sorgfältig planen.

Das Zertifikat, das den externen Schnittsellen des Edgeservers zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert. Öffentliche Zertifizierungsstellen, die nachweislich erfolgreich Zertifikate für Unified Communications bereitgestellt haben, sind im folgenden Artikel aufgeführt: [http://go.microsoft.com/fwlink/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/?linkid=3052%26kbid=929395). Beim Anfordern des Zertifikats können Sie die vom Lync Server-Bereitstellungs-Assistenten generierte Zertifikatanforderung verwenden oder aber das Zertifikat manuell oder mithilfe eines Prozesses der öffentlichen Zertifizierungsstelle anfordern. Das Zertifikat wird der Zugriffs-Edgedienst-Schnittstelle, der Webkonferenz-Edgedienst-Schnittstelle und dem Audio-/Video-Authentifizierungsdienst zugewiesen. Der Audio-/Video-Authentifizierungsdienst sollte nicht mit dem A/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio- und Videostreams verwendet. Die interne Edgeserverschnittstelle kann ein Zertifikat von einer internen Zertifizierungsstelle (innerhalb Ihrer Organisation) oder ein Zertifikat von einer öffentlichen Zertifizierungsstelle verwenden. Das Zertifikat der internen Schnittstelle verwendet nur den SN-Eintrag und benötigt bzw. verwendet keine SAN-Einträge.


> [!NOTE]
> Die folgende Tabelle zeigt zu Referenzzwecken einen sekundären SIP-Eintrag ( sip.fabrikam.com ) in der Liste für alternative Antragstellernamen. Für jede SIP-Domäne in Ihrer Organisation müssen Sie einen entsprechenden FQDN in der Liste der alternativen Antragstellernamen des Zertifikats hinzufügen.



## Erforderliche Zertifikate für eine Umgebung mit einem einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen


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
<th>Alternative Antragstellernamen (SAN)/Reihenfolge</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einzelner konsolidierter Edgeserver (externer Edge)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und benötigt die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für den Server und den Client, falls die Verbindung mit den öffentlichen Chatdiensten von AOL bereitgestellt werden soll. Das Zertifikat wird den externen Edgeschnittstellen zugewiesen für:</p>
<ul>
<li><p>Zugriffsedgedienst</p></li>
<li><p>Konferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<p>Beachten Sie, dass SANs basierend auf Ihren Definitionen im Topologie-Generator automatisch dem Zertifikat hinzugefügt werden. Sie fügen SAN-Einträge bei Bedarf für zusätzliche SIP-Domänen und sonstige Einträge, die unterstützt werden müssen, hinzu. Der Antragstellername wird im SAN repliziert und muss für den ordnungsgemäßen Betrieb vorhanden sein.</p></td>
</tr>
<tr class="even">
<td><p>Einzelner konsolidierter Edgeserver (interner Edge)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Kein SAN erforderlich</p></td>
<td><p>Das Zertifikat kann von einer öffentlichen oder privaten Zertifizierungsstelle ausgestellt werden und muss die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für den Server enthalten. Das Zertifikat wird der internen Edgeschnittstelle zugewiesen.</p></td>
</tr>
</tbody>
</table>


## Zertifikatszusammenfassung - Verbindung mit öffentlichen Chatdiensten


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
<th>Alternative Antragstellernamen (SAN)/Reihenfolge</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extern/Zugriffsedge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und benötigt die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für den Server und den Client, falls die Verbindung mit den öffentlichen Chatdiensten von AOL bereitgestellt werden soll. Das Zertifikat wird den externen Edgeschnittstellen zugewiesen für:</p>
<ul>
<li><p>Zugriffsedgedienst</p></li>
<li><p>Konferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<p>Beachten Sie, dass SANs basierend auf Ihren Definitionen im Topologie-Generator automatisch dem Zertifikat hinzugefügt werden. Sie fügen SAN-Einträge bei Bedarf für zusätzliche SIP-Domänen und sonstige Einträge, die unterstützt werden müssen, hinzu. Der Antragstellername wird im SAN repliziert und muss für den ordnungsgemäßen Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


## Zertifikatszusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


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
<th>Alternative Antragstellernamen (SAN)/Reihenfolge</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zuweisung zu Zugriffs-Edgedienst von Edgeserver oder Edgepool</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Die ersten drei SAN-Einträge sind die regulären SAN-Einträge für einen vollständigen Edgeserver. contoso.com ist der für den Partnerverbund mit dem XMPP-Partner auf der Stammdomänenebene erforderliche Eintrag. Dieser Eintrag ermöglicht XMPP für alle Domänen mit dem Suffix *.contoso.com.</p></td>
</tr>
</tbody>
</table>

