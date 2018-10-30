---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)'
TOCTitle: Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204846(v=OCS.15)
ms:contentKeyID: 49293865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Zertifikatanforderungen für einen Director mit einem Hardwaregerät zum Lastenausgleich verwenden ein Standardzertifikat mit einem Antragstellernamen sowie alternativen Antragstellernamen für Dienste, die vom Directorpool angenommen werden können. Für jeden Director im Pool wird ein Zertifikat angefordert. Darüber hinaus ist ein OAuth-Tokenzertifikat für die Authentifizierung zwischen Servern verfügbar, das auf jedem Server installiert wird.

### Zertifikate für einen skalierten Director mit einem Hardwaregerät zum Lastenausgleich

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
<td><p>Standard</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Optional) *.contoso.com</p></td>
<td><p>Director-Zertifikate können entweder von einer intern verwalteten Zertifizierungsstelle oder einer öffentlichen Zertifizierungsstelle angefordert werden.</p>
<p>Der Director antwortet auf Anforderungen vom Reverseproxy im Umkreisnetzwerk oder vom Edgeserver.</p>
<p>Oder ein Platzhaltereintrag für die einfachen URLs</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Kein Eintrag</p></td>
<td><div>

> [!IMPORTANT]
> Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.


</div>
<p>Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</p></td>
</tr>
</tbody>
</table>

