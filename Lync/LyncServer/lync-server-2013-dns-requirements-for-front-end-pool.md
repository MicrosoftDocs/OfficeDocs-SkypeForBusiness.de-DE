---
title: 'Lync Server 2013: DNS-Anforderungen für den Front-End-Pool'
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
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>DNS-Anforderungen für den Front-End-Pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-07_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe angemeldet sein.

Sie müssen die erforderlichen DNS-Einträge (Domain Name System) vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator konfigurieren. Darüber hinaus sind einige der vollqualifizierten Domänennamen (FQDNs), die bei der Konfiguration einer lync Server 2013-Bereitstellung verwendet werden, logische und keine physischen Server-FQDNs, daher ist vor der Veröffentlichung eine zusätzliche DNS-Konfiguration erforderlich.

<div>


> [!WARNING]  
> Lync Server 2013 unterstützt keine Single-Labeling-Domänen. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne mit dem Namen <STRONG>contoso. local</STRONG> unterstützt, aber eine Stammdomäne mit dem Namen <STRONG>local</STRONG> wird nicht unterstützt. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einer einzelnen Bezeichnung" unter <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein kurzer Name und kein FQDN. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Verwenden Sie beim Zuweisen von FQDNs Ihrer Server mit lync Server, Edgeserver und Pools <STRONG>nur Standardzeichen</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen Zertifizierungsstellen (CAS) unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).



</div>

Bevor Sie die Topologie nach der Bereitstellung ausführen, stellen Sie sicher, dass die folgenden Active Directory-und DNS-Einträge erstellt werden (entsprechend Ihren Anforderungen für bestimmte Features):

  - Jede Serverrolle, die in der Topologie vorhanden sein wird, wird als Active Directory-Objekt veröffentlicht (die Verbindung zwischen dem Computer und der Domäne wird dies erreichen).

  - Für jeden Server ist ein DNS-a-Eintrag vorhanden.

  - Für jede SIP-Domäne ist ein DNS-SRV-Eintrag vorhanden, wenn Sie beabsichtigen, die automatische Anmeldung \_für\_Clients in Form von sipinternaltls TCP zu verwenden. \<SIP-\>Domäne. Wenn Sie die manuelle Konfiguration für Clients verwenden, ist dieser Eintrag nicht erforderlich.

  - Ein DNS-a-Eintrag für jede konfigurierte einfache URL, von der in der Regel vier vorhanden sind: Meet, Dialin, LWA und Scheduler. Darüber hinaus gibt es die einfache Administrator-URL, die eine spezielle URL für den Zugriff auf die lync Server 2013-Systemsteuerung ist.

  - Der Server, auf dem SQL Server ausgeführt wird, muss der Domäne angehören und von dem Computer erreichbar sein, von dem aus der Topologie-Generator veröffentlicht wird.

Die Tabelle folgt den Referenzarchitekturen, die im Abschnitt Planung vorgestellt werden. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in der Planungsdokumentation.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Für den Front-End-Pool erforderliche DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort</th>
<th>Typ</th>
<th>FQDN</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS-Lastenausgleich). Erfordert einen DNS-a-Eintrag für die IP-Adresse jedes Front-End-Servers innerhalb des Pools, der dem Pool-FQDN zugeordnet ist.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (Virtual IP (VIP) of Hardware Load Balancer).</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01-Front-End-Server (Knoten 1).</p>
<p>Pool01-Front-End-Server (Knoten 2).</p>
<p>Pool01-Front-End-Server (Knoten 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01-Front-End-Server (Knoten 2).</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) für Client-to-Server-Webverkehr.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01-Back-End-Server mit SQL Server 2008 R2</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Erforderlich für lync Phone Edition oder automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für strikte Domänenübereinstimmung. In allen Fällen nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Nimmt eine zweite SIP-Domäne an. Erforderlich für lync Phone Edition, automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für strikte Domänenübereinstimmung. In allen Fällen nicht erforderlich.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Einfache URL für intern veröffentlichte Einwahlkonferenzen – der Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Einfache URL für intern veröffentlichte Konferenzen – der Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>Optionaler Eintrag, einfache URL für lync Server 2013 Control Panel intern veröffentlicht-Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen. Es wird nur Hostname (kein Domänenname) empfohlen.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = virtuelle IP-Adresse für das Hardware Load Balancer



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>DNS-SRV-Einträge für den Front-End-Pool


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
<th>Ort</th>
<th>Typ</th>
<th>FQDN</th>
<th>Ziel-FQDN</th>
<th>Port</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Erforderlich für die automatische Konfiguration von lync 2013-Clients, um intern zu arbeiten.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Erforderlich für die automatische Konfiguration von lync 2013-Clients, um intern zu arbeiten.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Für Geräte, auf denen lync Phone Edition ausgeführt wird, ist eine NTP-Quelle (Network Time Protocol) erforderlich. Intern sollte dies auf den Domänencontroller verweisen. Wenn der Domänencontroller nicht definiert ist, wird versucht, den NTP-Server time.Windows.com zu verwenden.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

