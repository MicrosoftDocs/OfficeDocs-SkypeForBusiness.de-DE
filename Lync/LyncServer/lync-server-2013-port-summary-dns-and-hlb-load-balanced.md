---
title: 'Lync Server 2013: Port Zusammenfassung-DNS-und HLB-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4c691bfeb6017777441002b3248621f5408665f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Port Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen. Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server. Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server. Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Einzelne Director-Ports und-Protokolle für Firewall-Definitionen

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
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP und Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Pool oder Front-End-Server</p></td>
<td><p>Kommunikation zwischen Servern zwischen dem Director HLB VIP und dem Front-End-Server-oder Front-End-Servern.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Internal Clients</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Internal Clients</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Director</p></td>
<td><p>SIP-Kommunikation vom Edgeserver zum Director sowie zu den Front-End-Servern.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Any</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Any</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Any</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

