---
title: 'Lync Server 2013: Portzusammenfassung für Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Portzusammenfassung für Reverseproxy in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-15_

Der Reverse-Proxy bietet minimale Anforderungen für Firewall und Port/Protokoll.

  - Die Anforderungen externer Firewalls lauten HTTPS/TCP/443 und die optionale http/TCP/80-Anforderung. HTTPS wird für SSL-und TLS-sichere Kommunikation über den Reverse-Proxy verwendet. HTTP wird verwendet, wenn Sie den Zugriff auf den AutoErmittlungsdienst zulassen möchten, wenn sich das Ändern von Zertifikaten als schwierig oder nicht gerechtfertigt erweisen kann.

  - Clients erwarten, dass Sie sich mit dem Office Web Apps-Server auf HTTPS in Verbindung setzen. Der Office Web Apps-Server erwartet die Kommunikation von internen Clients auf HTTPS/TCP/443. Die empfohlene Konfiguration ist das Zulassen von HTTPS/TCP/443 vom Reverse-Proxy zum Office Web Apps-Server.

  - Port 8080 wird verwendet, um den Datenverkehr von der internen Schnittstelle des Reverse Proxys an den Front-End-Server, Virtual IP-Front-End-Pool (VIP) oder den optionalen Director oder Director Pool VIP weiterzuleiten. Port TCP 8080 ist für mobile Geräte erforderlich, auf denen lync ausgeführt wird, um den AutoErmittlungsdienst in Situationen zu finden, in denen die Änderung des Zertifikats für die Veröffentlichung von externen Webdiensten unerwünscht ist (beispielsweise, wenn Sie über eine große Anzahl von SIP-Domänen verfügen). Wenn Sie sich entscheiden, neue Zertifikate mit den erforderlichen San-Einträgen zu erwerben, wird der Port TCP 8080 nicht benötigt und ist optional.

  - Port 4443 wird für den Datenverkehr von der internen Reverse Proxy-Schnittstelle zum Front-End-Server, Virtual IP-Front-End-Pool (VIP) oder dem optionalen Director oder Director Pool VIP verwendet.
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Verwechseln Sie die 4443 nicht über TCP vom Reverse-Proxy zur internen Bereitstellung für den Port 4443 über TCP-Datenverkehr vom Standard Edition-Server oder dem Front-End-Pool, der die Rolle des zentralen Verwaltungsspeichers verwaltet.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Firewall-Details für Reverse Proxy Server: externe Schnittstelle

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
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverse Proxy-Listener</p></td>
<td><p>Optional Umleitung zu HTTPS, wenn der Benutzer http://&lt;publishedSiteFQDN&gt;eingibt.</p>
<p>Dies ist auch bei Verwendung von Office Web Apps für Conferencing und dem AutoErmittlungsdienst für mobile Geräte, die lync ausführen, in Situationen erforderlich, in denen die Organisation das Zertifikat des externen Webdienst-Veröffentlichungsregel nicht ändern möchte.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverse Proxy-Listener</p></td>
<td><p>Adressbuch Downloads, Adressbuch-Webabfrage Dienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräte Updates, Gruppenerweiterung, Office Web Apps für Konferenzen, Einwahlkonferenzen und Besprechungen.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Firewall-Details für Reverse Proxy Server: interne Schnittstelle

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
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interne Reverse-Proxy-Schnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Director-Pool</p></td>
<td><p>Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte mit lync in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</p>
<p>Datenverkehr, der an Port 80 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 8080 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverse-Proxy-Schnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Director-Pool</p></td>
<td><p>Datenverkehr, der an Port 443 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 4443 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interne Reverse-Proxy-Schnittstelle</p></td>
<td><p>Office Web Apps für Konferenzen</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

