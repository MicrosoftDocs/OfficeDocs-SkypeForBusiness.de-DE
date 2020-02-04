---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)'
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
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Die Firewall-Portanforderungen für einen Director-Pool bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director aus der internen Schnittstelle des Edge-Servers oder der internen Schnittstelle des Reverse-Proxys herzustellen. Microsoft lync Server 2013 erwartet standardmäßig, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverse-Proxy an den Director sowie den Front-End-Pool und den Front-End-Server geöffnet werden. Darüber hinaus muss die SIP-Kommunikation (Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers mit dem Director und dem Front-End-Pool und dem Front-End-Server erfolgen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver auf dem Front-End-Pool und dem Front-End-Server. Eine Regel, die die SIP/MTLS/TCP 5061-Kommunikation vom Director, Front-End-Pool und Front-End-Server zur internen Edge-Server-Schnittstelle ermöglicht, muss ebenfalls erstellt werden.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Director-Ports und-Protokolle für Firewall-Definitionen

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
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interne Proxy-Schnittstelle</p></td>
<td><p>Director Hardware Load Balancer VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Proxy-Schnittstelle</p></td>
<td><p>Director Hardware Load Balancer VIP</p></td>
<td><p>Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director HLB VIP-und Front-End-Server-Webdienste gesendet.</p></td>
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
<td><p>Director Hardware Load Balancer VIP</p></td>
<td><p>Der Director stellt Webdienste sowohl internen als auch externen Clients zur Verfügung.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Interne Clients</p></td>
<td><p>Director Hardware Load Balancer VIP</p></td>
<td><p>Der Director stellt Webdienste sowohl internen als auch externen Clients zur Verfügung.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Director Hardware Load Balancer VIP</p></td>
<td><p>SIP-Kommunikation vom Edgeserver an den Director und die Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClsAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

