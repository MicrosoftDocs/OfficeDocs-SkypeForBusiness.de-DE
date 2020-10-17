---
title: 'Lync Server 2013: Port Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich'
description: 'Lync Server 2013: Port Summary – skalierte Directorpool, Hardwaregerät zum Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564551"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Port Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Firewall-Portanforderungen für eine Directorpool bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle des Edgeserver oder der internen Schnittstelle des Reverseproxys herzustellen. Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server. Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server. Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Director-Ports und -Protokolle für Firewall-Definitionen

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
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Server oder Front-End-Pool</p></td>
<td><p>Inter-Server-Kommunikation zwischen dem Director HLB VIP und den Front-End-Servern</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Interne Clients</p></td>
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
<td><p>Director Hardware-Lastenausgleich-VIP</p></td>
<td><p>SIP-Kommunikation vom Edgeserver zum Director und zu den Front-End-Servern.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Befehle für den zentralisierten Protokollierungsdienst-Controller (ClsController.exe) oder Agent (ClsAgent.exe) und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

