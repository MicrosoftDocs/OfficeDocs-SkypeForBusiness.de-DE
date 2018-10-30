---
title: 'Lync Server 2013: Zertifikatzusammenfassung für Reverseproxy'
TOCTitle: Zertifikatzusammenfassung für Reverseproxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205381(v=OCS.15)
ms:contentKeyID: 49295877
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Zertifikatanforderungen für den Reverseproxy sind wesentlich einfacher als die für die Edgeserver. Das Flussdiagramm enthält die geltenden Anforderungen. Die zugehörige Tabelle zeigt typische Antragstellernamen und alternative Antragstellernamen in Bezug zu den Szenarios, die wir in den Abschnitten über Edgeserver behandelt haben. Ausführliche Informationen zu den Edgeserver-Szenarios finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Flussdiagramm für Zertifikate für den Reverseproxy**

![Zertifikatflussdiagramm für Edgeserver](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Zertifikatflussdiagramm für Edgeserver")

### Reverseproxy: Externe Schnittstelle

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
<th>Alternativer Antragstellername/Reihenfolge</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Reverseproxy</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Optional): *.contoso.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit Server-EKU (Enhanced Key Usage, erweiterte Schlüsselverwendung) ausgestellt werden. Zu den Diensten gehören folgende: Adressbuchdienst, Verteilergruppenerweiterung, Office Web Apps für Konferenzen und Lync-IP-Geräteveröffentlichungsregeln. Zu den alternativen Antragstellernamen gehören:</p>
<ul>
<li><p>Externer FQDN für Webdienste für den Front-End-Server oder den Front-End-Pool</p></li>
<li><p>Externer FQDN für Webdienste für den Director oder den Directorpool</p></li>
<li><p>Einwahlkonferenzen</p></li>
<li><p>Veröffentlichungsregel für Onlinebesprechungen</p></li>
<li><p>Office Web Apps für Konferenzen</p></li>
<li><p>&quot;lyncdiscover&quot; (AutoErmittlung)</p></li>
</ul>
<p>Der optionale Platzhalter steht für einen &quot;Meet&quot;- und einen &quot;Dialin&quot;-SAN.</p></td>
</tr>
</tbody>
</table>

