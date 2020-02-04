---
title: Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging
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
ms.openlocfilehash: 3ae19fb2477f61c0e408ebad3a8abf97fb75b9c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-15_

Port-, Protokoll-und Firewall-Anforderungen für den Verbund mit Microsoft lync Server 2013, lync Server 2010 und Office Communications Server ähneln denen für den bereitgestellten Edgeserver. Clients initiieren die Kommunikation mit dem Access Edge Service über TLS/SIP/TCP 443. Föderationspartner initiieren jedoch die Kommunikation mit dem Access Edge-Dienst über MTLS/SIP/TCP 5061.

Wenn Sie Ihre Firewall für Ports und Protokolle konfigurieren möchten, die für die Unterstützung öffentlicher Instant Messaging-Konnektivität erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Möglichkeit von Kontakten im öffentlichen Chat-Anbieter zu berücksichtigen, lync-Clients zu kontaktieren, oder dass lync Kontakte mit öffentlichen Chat Kontakten aufnehmen soll.

Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen. Damit wird die sehr ähnliche Firewall-Port-und-Protokollkonfiguration berücksichtigt, die Sie normalerweise auf der Firewall haben, um lync-Clients als externe Benutzer zu unterstützen.

<div>


> [!IMPORTANT]
> Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine weiteren Benutzer-und Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.<BR>Die Föderation mit Messenger-Client Kontakten endet am 15. März 2013, mit Ausnahme des chinesischen Festlandes. Skype wird zum Verbund Client für Föderationsbenutzer, die Messenger zuvor verwendet haben.



</div>

Die Ports und Protokolle, die für den auf dem Edgeserver bereitgestellten XMPP-Proxy (Extensible Messaging and Presence Protocol) definiert sind, ermöglichen die Kommunikation vom XMPP-Partner zum Edgeserver und ermöglichen auch die Kommunikation von Ihrem Edgeserver zur xmpp. Federated-Partner. Eine Regel wird auch für die interne Firewall vom Front-End-Server oder Front-End-Pool für den Edge-Server oder den Edge-Pool definiert.

<div>

## <a name="firewall-summary---sip-federation"></a>Zusammenfassung der Firewall – SIP-Föderation


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Access Edge Service (öffentliche IP-Adresse)</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Verbindungspartner für öffentliche Chats</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen, die SIP verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Verbindungspartner für öffentliche Chats</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen, die SIP verwenden.</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Edge-Server-Zugriffs Schnittstelle</p></td>
<td><p>Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Zusammenfassung der Firewall – erweiterbares Messaging und Anwesenheits Protokoll (XMPP)


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
<td><p>Access Edge Service Interface-IP-Adresse</p></td>
<td><p>Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP. Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge Service Interface-IP-Adresse</p></td>
<td><p>Beliebig</p></td>
<td><p>Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP. Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstellen-IP</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zum Edgeserver</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

