---
title: Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7119bfd6209ac9a7d8eb2c4adfddb75c3601116d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508752"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-15_

Port-, Protokoll-und Firewall-Anforderungen für den Verbund mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server ähneln denen für die bereitgestellte Edgeserver. Clients initiieren die Kommunikation mit dem Zugriffs-Edgedienst über TLS/SIP/TCP 443. Verbundpartner initiieren jedoch die Kommunikation mit dem Zugriffs-Edgedienst über MTLS/SIP/TCP 5061.

Wenn Sie die Firewall für Ports und Protokolle konfigurieren möchten, die für die Unterstützung von öffentlichen Instant Messaging-Verbindungen erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Fähigkeit von Kontakten im öffentlichen Sofortnachrichtenanbieter zum Kontaktieren von lync-Clients zu berücksichtigen, oder dass lync Kontakt mit öffentlichen Chat Kontakten aufnehmen kann.

Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen. Dies berücksichtigt die sehr ähnliche Firewall-Port-und Protokollkonfiguration, die Sie in der Regel für die Firewall zur Unterstützung von lync-Clients als externe Benutzer haben würden.

<div>


> [!IMPORTANT]
> Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.<BR>Partnerverbund mit Messenger-Client Kontakten wird offiziell am 15. März 2013 mit Ausnahme des chinesischen Festland enden. Skype wird zum Verbund Client für Verbundbenutzer, die zuvor Messenger verwendet haben.



</div>

Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation zwischen dem XMPP-Verbundpartner und der Edgeserver und erlauben auch die Kommunikation von Ihrem Edgeserver zum XMPP-Verbundpartner. Eine Regel wird auch in der internen Firewall aus dem Front-End-Server oder Front-End-Pool zum Edgeserver oder Edgepool definiert.

<div>

## <a name="firewall-summary---sip-federation"></a>Firewall-Zusammenfassung-SIP-Partnerverbund


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
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Öffentliche IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Firewallzusammenfassung – Öffentlicher Chat


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
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Partner für Verbindung mit öffentlichem Chatdienst</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Partner für Verbindung mit öffentlichem Chatdienst</p></td>
<td><p>Für Verbund-und öffentliche Instant Messaging-Verbindungen, die SIP verwenden.</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Edgeserver Zugriffs Schnittstelle</p></td>
<td><p>Für öffentliche Chat Verbindungen mit Windows Live Messenger erforderlich.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Zusammenfassung der Firewall – xmpp (Extensible Messaging and Presence Protocol)


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
<td><p>Beliebig</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP. Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP. Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edgeserver-Schnittstellen-IP</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zum Edgeserver</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

