---
title: 'Lync Server 2013: Port Zusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: Port Summary – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543141"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Port Zusammenfassung-AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-05_

Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann, wenn er in DNS mit den `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` Hosteinträgen veröffentlicht wird, von Clients zum Auffinden von lync Server Features verwendet werden. Damit Mobile Geräte, die lync Mobile ausführen, die AutoErmittlung verwenden, müssen Sie möglicherweise zuerst die Liste alternativer Zertifikatsantrags Teller Namen auf einem beliebigen Director ändern und Front-End-Server den AutoErmittlungsdienst ausführen. Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.

Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht am Port 80**     Für mobile Geräte sind keine Zertifikat Änderungen erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt. Dies liegt daran, dass Mobile Geräte, auf denen lync läuft, extern auf den Reverseproxy auf Port 80 zugreifen und dann an Port 8080 intern an einen Director oder Front-End-Server weitergeleitet werden.

  - **Veröffentlicht am Port 443**     Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss einen `lyncdiscover.<sipdomain>` Eintrag für jede SIP-Domäne in Ihrer Organisation enthalten.
    
    <div>
    

    > [!IMPORTANT]  
    > Für neue Installationen oder Upgrades von lync Server 2010, in denen Sie Mobility bereitgestellt haben, haben Sie entweder Port 80 für die AutoErmittlung des mobilitätsdiensts oder erneute Zertifikate mit dem richtigen Antragstellernamen und den alternativen Antragstellernamen verwendet. Überprüfen Sie die Zertifikate auf Ihrem Director und Front-End-Server, um zu bestätigen, welchen Pfad Sie ausgewählt haben.

    
    </div>

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
<td><p>Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; . Auch erforderlich, wenn Office-webapps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet werden, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</p></td>
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
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</p></td>
<td><p>Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte. Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</p></td>
<td><p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

