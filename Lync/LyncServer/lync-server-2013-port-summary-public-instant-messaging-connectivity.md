---
title: 'Lync Server 2013: Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bce3413e7e41e3784cb0ba300c621a7c042b618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534162"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-16_

Wenn Sie die Firewall für Ports und Protokolle konfigurieren möchten, die für die Unterstützung von öffentlichen Instant Messaging-Verbindungen erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Fähigkeit von Kontakten im öffentlichen Sofortnachrichtenanbieter zum Kontaktieren von lync-Clients zu berücksichtigen, oder dass lync Kontakt mit öffentlichen Chat Kontakten aufnehmen kann.

Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen. Dies berücksichtigt die sehr ähnliche Firewall-Port-und Protokollkonfiguration, die Sie in der Regel für die Firewall zur Unterstützung von lync-Clients als externe Benutzer haben würden.

<div>


> [!IMPORTANT]  
> Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.<BR>Partnerverbund mit Messenger-Client Kontakten wird offiziell am 15. März 2013 mit Ausnahme des chinesischen Festland enden. Skype wird zum Verbund Client für Verbundbenutzer, die zuvor Messenger verwendet haben.



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

## <a name="see-also"></a>Siehe auch


[Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

