---
title: Portzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
TOCTitle: Portzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49294200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Über die für den XMPP-Proxy festgelegten Ports und Protokolle, der für den Edgeserver bereitgestellt ist, kann der XMPP-Verbundpartner mit dem Edgeserver und der Edgeserver mit dem XMPP-Verbundpartner kommunizieren. Eine Regel ist auch in der internen Firewall von dem Front-End-Server oder dem Front-End-Pool zum Edgeserver oder zum Edgepool definiert.

## Zusammenfassung zur Firewall für XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quelle (IP-Adresse)</th>
<th>Ziel (IP-Adresse)</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Beliebig</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>XMPP-Standardport für Server-zu-Server-Kommunikation. Erlaubt die Kommunikation von XMPP-Verbundpartnern mit dem Edgeserver-XMPP-Proxy</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>XMPP-Standardport für Server-zu-Server-Kommunikation. Erlaubt die Kommunikation vom Edgeserver-XMPP-Proxy mit XMPP-Partnern</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne IP der Edgeserver-Schnittstelle</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zum Edgeserver</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Aufgaben

[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Weitere Ressourcen

[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

