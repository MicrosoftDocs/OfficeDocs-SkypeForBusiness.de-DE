---
title: 'Lync Server 2013: DNS-Anforderungen für den Front-End-Pool'
TOCTitle: DNS-Anforderungen für den Front-End-Pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398082(v=OCS.15)
ms:contentKeyID: 49293001
ms.date: 12/16/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für den Front-End-Pool in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-15_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.

Sie müssen die erforderlichen DNS-Einträge (Domain Name System) konfigurieren, bevor Sie Ihre Topologie im Topologie-Generator veröffentlichen. Bei einigen der in der Konfiguration einer Lync Server 2013-Bereitstellung verwendeten vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) handelt es sich nicht um physische Server-FQDNs, sondern um logische FQDNs. Daher ist vor der Veröffentlichung eine zusätzliche DNS-Konfiguration erforderlich.


> [!WARNING]
> Lync Server 2013 unterstützt keine Domänen mit einfacher Bezeichnung. Beispielsweise wird eine Gesamtstruktur mit der Stammdomäne <STRONG>contoso.local</STRONG> unterstützt, die Stammdomäne <STRONG>local</STRONG> hingegen nicht. Ausführliche Informationen finden Sie im Microsoft&nbsp;Knowledge Base-Artikel&nbsp;300684, „Informationen zur Konfiguration von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung“, unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=300684</A>.




> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet FQDNs und keine Kurznamen. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A&nbsp;-&nbsp;Z, a&nbsp;-&nbsp;z, 0&nbsp;-&nbsp;9 und Bindestriche) beim Zuweisen der FQDNs von Servern mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.



Bevor Sie die Topologie nach ihrer Bereitstellung in Betrieb nehmen, sollten Sie sicherstellen, dass die folgenden Active Directory- und DNS-Einträge erstellt wurden (die jeweiligen Anforderungen richten sich nach den verwendeten Funktionen):

  - Jede Serverrolle in der Topologie wird als Active Directory-Objekt veröffentlicht (die Veröffentlichung erfolgt beim Computerbeitritt zur Domäne).

  - Für jeden Server ist ein DNS-A-Eintrag vorhanden.

  - Für jede Domäne ist ein DNS-SRV-Eintrag vorhanden, wenn Sie die automatische Anmeldung für Clients in der Form "\_sipinternaltls\_tcp. *\<SIP-Domäne\>* " verwenden möchten. Wenn Sie für Clients eine manuelle Konfiguration verwenden, ist dieser Eintrag nicht erforderlich.

  - Ein DNS-A-Eintrag für jede konfigurierte einfache URL, für die es im Allgemeinen vier Typen gibt: "Meet", "Dialin", "LWA" und "Scheduler". Zusätzlich gibt es die einfache URL "Admin", bei der es sich um eine spezielle URL für den Zugriff auf die Systemsteuerung für Lync Server 2013 handelt.

  - Der Server, auf dem SQL Server ausgeführt wird, muss der Domäne beigetreten und für den Computer erreichbar sein, über den der Topologie-Generator die Veröffentlichung durchführt.

Die Tabelle folgt den Referenzarchitekturen aus dem Abschnitt zur Planung. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in der Planungsdokumentation.

### Für den Front-End-Pool benötigte DNS-Einträge

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
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS-Lastenausgleich). Erfordert einen DNS-A-Eintrag für die IP-Adresse jedes Front-End-Servers im Pool mit Zuordnung zum Pool-FQDN.</p></td>
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
<td><p>Pool01 Front-End-Server (KNOTEN 1)</p>
<p>Pool01 Front-End-Server (KNOTEN 2)</p>
<p>Pool01 Front-End-Server (KNOTEN 3)</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 Front-End-Server (KNOTEN 2)</p></td>
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
<td><p>Pool01, Back-End-Server mit SQL Server 2008 R2</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Erforderlich für Lync Phone Edition, für die automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für den exakten Domänenabgleich. Nicht in allen Fällen erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Setzt eine zweite SIP-Domäne voraus. Erforderlich für Lync Phone Edition, für die automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für den exakten Domänenabgleich. Nicht in allen Fällen erforderlich.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Einfache URL für Einwahlkonferenzen, die intern veröffentlicht wird. Der Front-End-Server (oder Director, sofern installiert) antwortet auf Anforderungen einfacher URLs.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Einfache URL für Konferenzen, die intern veröffentlicht wird. Der Front-End-Server (oder Director, sofern installiert) antwortet auf Anforderungen einfacher URLs.</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>Optionaler Eintrag. Einfache URL für den Zugriff auf die Systemsteuerung für Lync Server 2013, die intern veröffentlicht wird. Der Front-End-Server (oder Director, sofern installiert) antwortet auf Anforderungen einfacher URLs. Es wird empfohlen, nur den Hostnamen zu verwenden (keinen Domänennamen).</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> VIP = Virtuelle IP-Adresse für ein Hardwaregerät zum Lastenausgleich



## DNS-SRV-Einträge für den Front-End-Pool


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
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Erforderlich, damit die automatische Konfiguration von Lync 2013-Clients intern funktioniert</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Erforderlich, damit die automatische Konfiguration von Lync 2013-Clients intern funktioniert</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS-Konfiguration</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>NTP-Quelle (Network Time Protocol), die für Geräte mit Lync Phone Edition erforderlich ist. Intern sollte dieser Eintrag auf den Domänencontroller verweisen. Wenn der Domänencontroller nicht definiert ist, wird der NTP-Server &quot;time.windows.com&quot; verwendet.</p></td>
</tr>
</tbody>
</table>

