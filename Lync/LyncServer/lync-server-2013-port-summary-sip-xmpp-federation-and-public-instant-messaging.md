---
title: Portzusammenfassung – SIP, XMPP-Partnerverbund und Chat in öffentlichen Netzen
TOCTitle: Portzusammenfassung – SIP, XMPP-Partnerverbund und Chat in öffentlichen Netzen
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49295053
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung – SIP, XMPP-Partnerverbund und Chat in öffentlichen Netzen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Port-, Protokoll- und Firewallanforderungen für den Verbund mit Microsoft Lync Server 2013, Lync Server 2010 und Office Communications Server ähneln denen für den bereitgestellten Edgeserver. Die Clients initiieren die Kommuniaktion mit dem Zugriffs-Edgedienst über TLS/SIP/TCP 443. Verbundpartner initiieren die Kommunikation mit dem Zugriffs-Edgedienst jedoch über MTLS/SIP/TCP 5061.

Beim Konfigurieren der Firewall für Ports und Protokolle, die zur Unterstützung von öffentlichen Chatverbindungen benötigt werden, sollten Sie zunächst beachten, dass SIP/MTLS/TCP 5061 bidirektional ist, damit Kontakte im Chatanbieter Lync-Clients kontaktieren können oder Lync öffentliche Chatkontakte kontaktieren kann.

Windows Live Messenger kann an A/V-Kommunikation mit Lync-Clients teilnehmen. Das erklärt die sehr ähnliche Firewallport- und -protokollkonfiguration, die Sie typischerweise auf der Firewall verwenden, um Lync-Clients als externe Benutzer zu unterstützen.


> [!IMPORTANT]
> Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard-Clientzugriffslizenz (CAL). Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht es Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.<BR>Der Partnerverbund mit Messenger-Clientkontakten endet offiziell am 15. März 2013, außer für Festlandchina. Skype wird der neue Partnerverbundclient für Partnerbenutzer, die zuvor Messenger verwendet haben.



Über die für den XMPP-Proxy festgelegten Ports und Protokolle, der für den Edgeserver bereitgestellt ist, kann der XMPP-Verbundpartner mit dem Edgeserver und der Edgeserver mit dem XMPP-Verbundpartner kommunizieren. Eine Regel ist auch in der internen Firewall von dem Front-End-Server oder dem Front-End-Pool zum Edgeserver oder zum Edgepool definiert.

## Firewallzusammenfassung – SIP-Verbund


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rolle/Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Öffentliche IP-Adresse für den Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
</tbody>
</table>


## Firewallzusammenfassung – Verbindungen mit öffentlichen Instant Messaging-Diensten


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rolle/Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Notizen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Für Partnerverbund- und öffentliche Chatverbindungen mithilfe von SIP</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten</p></td>
<td><p>Für Partnerverbund- und öffentliche Chatverbindungen mithilfe von SIP</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/SIP(TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn Verbindungen mit öffentlichen Instant Messaging-Diensten konfiguriert sind.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Für Verbindungen mit öffentlichen Chatdiensten mit Windows Live Messenger erforderlich</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Für Verbindungen mit öffentlichen Chatdiensten mit Windows Live Messenger erforderlich</p></td>
</tr>
</tbody>
</table>


## Firewallzusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


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
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Alle</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP; erlaubt Kommunikation von XMPP-Verbundpartnern zum Edgeserver-XMPP-Proxy</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Alle</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP; erlaubt Kommunikation vom Edgeserver-XMPP-Proxy zu XMPP-Verbundpartnern</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Alle</p></td>
<td><p>Interne IP der Edgeserver-Schnittstelle</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zum Edgeserver</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  

#### Weitere Ressourcen

[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

