---
title: 'Lync Server 2013: Portzusammenfassung für einen einzelnen Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0179d6fd27207d28caa10ffa01bea155f9b00c03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Portzusammenfassung für einen einzelnen Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Die Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director aus der internen Schnittstelle oder dem internen Netzwerk des Reverse-Proxys herzustellen. Microsoft lync Server 2013 erwartet standardmäßig, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverse-Proxy an den Director sowie den Front-End-Pool und den Front-End-Server geöffnet werden. Darüber hinaus muss die SIP-Kommunikation (Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers mit dem Director und dem Front-End-Pool und dem Front-End-Server erfolgen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver auf dem Front-End-Pool und dem Front-End-Server. Eine Regel, die die SIP/MTLS/TCP 5061-Kommunikation vom Director, Front-End-Pool und Front-End-Server zur internen Edge-Server-Schnittstelle ermöglicht, muss ebenfalls erstellt werden.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Single Director-Ports und-Protokolle für Firewall-Definitionen

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
<td><p>Director</p></td>
<td><p>Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director und die Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Proxy-Schnittstelle</p></td>
<td><p>Director</p></td>
<td><p>Zunächst von der externen Seite des Reverse-Proxys empfangen, wird die Kommunikation an den Director und die Front-End-Server-Webdienste gesendet.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Server oder Front-End-Pool</p></td>
<td><p>Inter-Server-Kommunikation zwischen dem Director und dem Front-End-Server</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Interne Clients</p></td>
<td><p>Director-Webdienste</p></td>
<td><p>Der Director bietet Web Services für interne und externe Clients.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Interne Clients</p></td>
<td><p>Director-Webdienste</p></td>
<td><p>Der Director bietet Web Services für interne und externe Clients.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Director</p></td>
<td><p>SIP-Kommunikation vom Edgeserver an den Director und den Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClasAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClasAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierte Protokollierungsdienst Controller (ClsController. exe) oder Agent (ClasAgent. exe)-Befehle und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

