---
title: DNS-Zusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
TOCTitle: DNS-Zusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49293194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum Konfigurieren von XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS (Domain Name System)-Einträge auf einem externen DNS-Server der die Einträge in den Zugriffs-Edgedienst ihres Edgeserver oder Edgepool auflöst.

## DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/TYP/Port</th>
<th>FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname)</th>
<th>IP-Adresse/FQDN--Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang ggf. für alle internen SIP-Domänen mit für Lync aktivierten Benutzern, denen der Kontakt mit XMPP-Kontakten aufgrund der Konfiguration der externen Zugriffsrichtlinie durch eine globale Richtlinie, eine Standortrichtlinie für den Standort des Benutzers oder eine Benutzerrichtlinie für den für Lync aktivierten Benutzer erlaubt ist. Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner-Richtlinie konfiguriert sein. Weitere Details finden Sie in den <strong>Siehe auch</strong>-Themen.</p></td>
</tr>
<tr class="even">
<td><p>Externes DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgediensts auf Ihrem Edgeserver oder Edgepool, der den XMPP-Proxy hostet</p></td>
<td><p>Verweist auf den Zugriffs-Edgedienst oder Edgepool, der den XMPP-Proxydienst hostet. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Aufgaben

[Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  

#### Konzepte

[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

