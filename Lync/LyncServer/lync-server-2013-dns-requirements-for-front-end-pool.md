---
title: 'Lync Server 2013: DNS-Anforderungen für Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 882ffb0597b0dbd4f4be5b25a86facdda4367734
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>DNS-Anforderungen für Front-End-Pool in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-07_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.

Sie müssen die erforderlichen Domain Name System (DNS) Einträge vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator konfigurieren. Darüber hinaus sind einige der vollqualifizierten Domänennamen (FQDNs), die in der Konfiguration einer lync Server 2013-Bereitstellung verwendet werden, logische und keine physischen Server-FQDNs, daher ist vor der Veröffentlichung eine zusätzliche DNS-Konfiguration erforderlich.

<div>


> [!WARNING]  
> Lync Server 2013 bietet keine Unterstützung für Domänen mit einfacher Bezeichnung. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens <STRONG>contoso.local</STRONG> unterstützt, eine Stammdomäne namens <STRONG>local</STRONG> hingegen nicht. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung" unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs Ihrer Server, auf denen lync Server, Edge-Server und Pools verwendet werden. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.



</div>

Stellen Sie vor dem Betrieb der Topologie nach der Bereitstellung sicher, dass die folgenden Active Directory-und DNS-Einträge erstellt wurden (entsprechend den Anforderungen bestimmter Features):

  - Jede Serverrolle, die in der Topologie vorhanden sein wird, wird als Active Directory Objekt veröffentlicht (das Hinzufügen des Computers zur Domäne wird dies erreichen).

  - Für jeden Server ist ein DNS-A-Eintrag vorhanden.

  - Für jede SIP-Domäne ist ein DNS-SRV-Eintrag vorhanden, wenn Sie die automatische Anmeldung für Clients in \_Form\_von sipinternaltls TCP verwenden möchten. \<SIP-\>Domäne. Wenn Sie für Clients eine manuelle Konfiguration verwenden, ist dieser Eintrag nicht erforderlich.

  - Ein DNS-A-Eintrag für jede konfigurierte einfache URL, für die es im Allgemeinen vier Typen gibt: "Meet", "Dialin", "LWA" und "Scheduler". Darüber hinaus gibt es die einfache admin-URL, die eine spezielle URL für den Zugriff auf die lync Server 2013-Systemsteuerung ist.

  - Der Server mit SQL Server muss der Domäne beigetreten sein und von dem Computer, auf dem der Topologie-Generator veröffentlicht wird, erreichbar sein.

Die Tabelle folgt den Referenzarchitekturen aus dem Abschnitt zur Planung. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in der Planungsdokumentation.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Für die Front-End-Pool erforderliche DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort</th>
<th>Typ</th>
<th>FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS-Lastenausgleich). Erfordert einen DNS-a-Eintrag für die IP-Adresse der einzelnen Front-End-Server im Pool, die dem Pool-FQDN zugeordnet werden.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (virtuelle IP [VIP] des Hardwaregeräts für den Lastenausgleich)</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 Front-End-Server (Knoten 1).</p>
<p>Pool01 Front-End-Server (Knoten 2).</p>
<p>Pool01 Front-End-Server (Knoten 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 Front-End-Server (Knoten 2).</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) für Webdatenverkehr vom Client zum Server</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01-Back-End-Server mit SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Für lync-Phone Edition oder automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für eine strenge Domänenübereinstimmung erforderlich. Nicht in allen Fällen erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Setzt eine zweite SIP-Domäne voraus. Für lync-Phone Edition, automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für eine strenge Domänenübereinstimmung erforderlich. Nicht in allen Fällen erforderlich.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Einfache URL für intern veröffentlichte Einwahlkonferenzen – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Einfache URL für intern veröffentlichte Konferenzen – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>Optionaler Datensatz, einfache URL für lync Server 2013 Systemsteuerung, die intern veröffentlicht wird – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen. Es wird empfohlen, nur Hostname (kein Domänenname) zu nennen.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = Virtuelle IP-Adresse für ein Hardwaregerät zum Lastenausgleich



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>DNS-SRV-Einträge für die Front-End-Pool


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort</th>
<th>Typ</th>
<th>FQDN</th>
<th>Ziel-FQDN</th>
<th>Port</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Für die automatische Konfiguration von lync 2013 Clients für die interne Verwendung erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Für die automatische Konfiguration von lync 2013 Clients für die interne Verwendung erforderlich.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_ntp. _udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>NTP-Quelle (Network Time Protocol) erforderlich für Geräte, die lync Phone Edition ausführen. Intern sollte dieser Eintrag auf den Domänencontroller verweisen. Wenn der Domänencontroller nicht definiert ist, wird der NTP-Server "time.windows.com" verwendet.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

