---
title: 'Lync Server 2013: Port Summary-Reverse Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfe8a797fa926899774386101ff57fa5733b9918
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534152"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Port Zusammenfassung-Reverseproxy in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-15_

Die Firewall- und die Port- bzw. Protokollanforderungen des Reverseproxys sind minimal.

  - Externe Firewall-Anforderungen sind die HTTPS/TCP/443 und die optionale http/TCP/80. HTTPS wird für die sichere SSL-und TLS-Kommunikation über den Reverseproxy verwendet. HTTP wird verwendet, wenn Sie den Zugriff auf den AutoErmittlungsdienst gewähren möchten, wenn sich das Ändern von Zertifikaten als schwierig oder nicht Kosten berechtigt erweisen kann.

  - Clients erwarten, dass Sie den Office-webapps-Server unter https kontaktieren. Der Office-webapps-Server erwartet die Kommunikation von internen Clients unter https/TCP/443. Die empfohlene Konfiguration besteht darin, HTTPS/TCP/443 vom Reverseproxy zum Office-webapps-Server zuzulassen.

  - Port 8080 wird verwendet, um Datenverkehr von der internen Reverse Proxy-Schnittstelle an den Front-End-Server, Front-End-Pool virtuelle IP (VIP) oder den optionalen Director oder Directorpool VIP weiterzuleiten. Port TCP 8080 ist erforderlich, damit Mobile Geräte, auf denen lync ausgeführt wird, den AutoErmittlungsdienst in Situationen finden, in denen das Ändern des Veröffentlichungsregel Zertifikats für externe Webdienste nicht erwünscht ist (beispielsweise, wenn Sie eine große Anzahl von SIP-Domänen haben). Wenn Sie neue Zertifikate mit den erforderlichen San-Einträgen erwerben möchten, ist der Port TCP 8080 nicht erforderlich und ist optional.

  - Port 4443 wird für Datenverkehr von der internen Reverseproxy-Schnittstelle zum Front-End-Server, Front-End-Pool Virtual IP (VIP) oder dem optionalen Director oder Directorpool VIP verwendet.
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Verwechseln Sie nicht die 4443 über TCP vom Reverseproxy zur internen Bereitstellung für den Port 4443 über TCP-Datenverkehr von der Standard Edition-Server oder der Front-End-Pool, die die Rolle des zentralen Verwaltungsspeichers verwaltet.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Port-und Protokoll Details

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Firewalldetails für Reverseproxyserver: externe Schnittstelle

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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverseproxylistener</p></td>
<td><p>Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; .</p>
<p>Auch erforderlich, wenn Office-webapps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet werden, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverseproxylistener</p></td>
<td><p>Adressbuch Downloads, Adressbuch-Webabfragedienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräteaktualisierungen, Gruppenerweiterung, Office-Webanwendungen für Konferenzen, Einwahlkonferenzen und Besprechungen.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Firewalldetails für Reverseproxyserver: interne Schnittstelle

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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director Directorpool</p></td>
<td><p>Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</p>
<p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director Directorpool</p></td>
<td><p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Office-Webanwendungen für Konferenzen</p></td>
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

