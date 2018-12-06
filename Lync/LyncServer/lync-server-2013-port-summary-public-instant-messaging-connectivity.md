---
title: Portzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten
TOCTitle: Portzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49295902
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Beim Konfigurieren der Firewall für Ports und Protokolle, die zur Unterstützung von öffentlichen Chatverbindungen benötigt werden, sollten Sie zunächst beachten, dass SIP/MTLS/TCP 5061 bidirektional ist, damit Kontakte im Chatanbieter Lync-Clients kontaktieren können oder Lync öffentliche Chatkontakte kontaktieren kann.

Windows Live Messenger kann an A/V-Kommunikation mit Lync-Clients teilnehmen. Das erklärt die sehr ähnliche Firewallport- und -protokollkonfiguration, die Sie typischerweise auf der Firewall verwenden, um Lync-Clients als externe Benutzer zu unterstützen.


> [!IMPORTANT]
> Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard-Clientzugriffslizenz (CAL). Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht es Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.<BR>Der Partnerverbund mit Messenger-Clientkontakten endet offiziell am 15. März 2013, außer für Festlandchina. Skype wird der neue Partnerverbundclient für Partnerbenutzer, die zuvor Messenger verwendet haben.



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
<th>Anmerkungen</th>
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
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Edgeserver-Zugriffs-Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn Verbindungen mit öffentlichen Chatdiensten konfiguriert sind.</p></td>
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


## Siehe auch

#### Konzepte

[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

