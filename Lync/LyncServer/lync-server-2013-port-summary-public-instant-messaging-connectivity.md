---
title: 'Lync Server 2013: Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-16_

Um Ihre Firewall für Ports und Protokolle zu konfigurieren, die für die Unterstützung öffentlicher Instant Messaging-Konnektivität erforderlich sind, beachten Sie zunächst, dass SIP/MTLS/TCP 5061 bidirektional ist, um die Möglichkeit von Kontakten im öffentlichen Chat-Anbieter zu berücksichtigen, lync-Clients zu kontaktieren, oder lync Kontakt mit öffentlichen Chat Kontakten aufnehmen.

Windows Live Messenger kann an der Audio-und Videokommunikation mit lync-Clients teilnehmen. Damit wird die sehr ähnliche Firewall-Port-und-Protokollkonfiguration berücksichtigt, die Sie normalerweise auf der Firewall haben, um lync-Clients als externe Benutzer zu unterstützen.

<div>


> [!IMPORTANT]  
> Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine weiteren Benutzer-und Gerätelizenzen außerhalb der lync-Standard Client Zugriffslizenz (CAL) erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.<BR>Die Föderation mit Messenger-Client Kontakten endet am 15. März 2013, mit Ausnahme des chinesischen Festlandes. Skype wird zum Verbund Client für Föderationsbenutzer, die Messenger zuvor verwendet haben.



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

## <a name="see-also"></a>Siehe auch


[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

