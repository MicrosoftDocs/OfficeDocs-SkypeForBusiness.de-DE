---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
TOCTitle: DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205319(v=OCS.15)
ms:contentKeyID: 49295621
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die Anforderungen für DNS-Einträge für den Remotezugriff auf Lync Server 2013 sind im Vergleich zu den Anforderungen für Zertifikate und Ports recht einfach. Darüber hinaus sind viele Einträge optional, je nachdem, wie Sie Clients, auf denen Lync 2013 ausgeführt wird, konfigurieren und ob Sie einen Partnerverbund aktivieren.

Ausführliche Informationen zu den DNS-Anforderungen für Lync 2013 finden Sie unter [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zur automatischen Konfiguration von Lync 2013-Clients bei nicht konfiguriertem Split-Brain-DNS finden Sie im Abschnitt "Automatische Konfiguration ohne Split-Brain-DNS" in [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung "Topologie mit einem einzelnen konsolidierten Edgeserver" gezeigt wird. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von Lync 2013-Clients erforderlich sind. Wenn Sie Lync-Clients mithilfe von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) konfigurieren möchten, sind die zugeordneten Einträge nicht erforderlich.

## WICHTIG: Netzwerkadapteranforderungen für Edgeserver

Zur Vermeidung von Routingproblemen müssen Sie sicherstellen, dass mindestens zwei Netzwerkadapter auf den Edgeservern vorhanden sind, und dass das Standardgateway nur für den Netzwerkadapter konfiguriert wurde, der der externen Schnittstelle zugeordnet ist. Wie in der Abbildung "Skaliertes konsolidiertes Edgeszenario" unter [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) gezeigt, würde das Standardgateway beispielsweise auf die externe Firewall zeigen.

Sie können die zwei Netzwerkadapter auf jedem Ihrer Edgeserver folgendermaßen konfigurieren:

  - **Netzwerkadapter 1 - Knoten 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu beliebigen Netzwerken mit Servern vorhanden ist, auf denen Lync Server 2013- oder Lync Server 2013-Clients ausgeführt werden (z. B. von 172.25.33.0 zu 192.168.10.0).

  - **Netzwerkadapter 1 - Knoten 2 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.11.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu beliebigen Netzwerken mit Servern vorhanden ist, auf denen Lync Server 2013- oder Lync Server 2013-Clients ausgeführt werden (z. B. von 172.25.33.0 zu 192.168.10.0).

  - **Netzwerkadapter 2 - Knoten 1 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen. Beispielsweise 131.107.155.10 für den Zugriffs-Edgedienst, 131.107.155.20 für den Webkonferenz-Edgedienst, 131.107.155.30 für den A/V-Edgedienst.
    
    Die öffentliche IP-Adresse des Zugriffs-Edgediensts ist als primär, das Standardgateway ist auf den öffentlichen Router festgelegt (131.107.155.1).
    
    Die privaten IP-Adressen des Webkonferenz-Edgediensts und A/V-Edgediensts sind zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** in **Eigenschaften von LAN-Verbindung** von Windows Server.
    

    > [!NOTE]
    > Es ist möglich, jedoch nicht zu empfehlen, eine einzelne IP-Adresse für alle drei Edgedienst-Schnittstellen zu verwenden. Dadurch werden zwar IP-Adressen gespart, aber für jeden Dienst sind unterschiedliche Portnummern erforderlich. Die Standardportnummer ist 443/TCP, womit sichergestellt wird, dass die meisten Remotefirewalls den Datenverkehr zulassen. Wenn Sie die Portwerte z.&nbsp;B. in 5061/TCP für den Zugriffs-Edgedienst ändern, könnten 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst Probleme für Remotebenutzer verursachen, wenn deren Firewall den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Darüber hinaus wird durch drei eindeutige IP-Adressen die Problembehandlung vereinfacht, da nach der IP-Adresse gefiltert werden kann.



  - **Netzwerkadapter 2 - Knoten 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen. Beispielsweise 131.107.155.11 für den Zugriffs-Edgedienst, 131.107.155.21 für den Webkonferenz-Edgedienst, 131.107.155.31 für den A/V-Edgedienst.
    
    Die öffentliche IP-Adresse des Zugriffs-Edgediensts ist als primär, das Standardgateway ist auf den öffentlichen Router festgelegt (131.107.155.1).
    
    Die privaten IP-Adressen des Webkonferenz-Edgediensts und A/V-Edgediensts sind zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** in **Eigenschaften von LAN-Verbindung** von Windows Server.


> [!TIP]
> Das Konfigurieren von zwei Netzwerkadaptern für den Edgeserver ist eine von zwei möglichen Optionen. Die andere Option besteht darin, einen einzigen Netzwerkadapter für die interne Schnittstelle und drei Netzwerkadapter für die externe Schnittstelle des Edgeservers zu verwenden. Der wichtigste Vorteil dieser Option ist ein separater Netzwerkadapter pro Edgeserverdienst und eine möglicherweise präzisere Datenerfassung, falls eine Problembehandlung erforderlich ist.



### Erforderliche DNS-Einträge für einen skalierten konsolidierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen (Beispiel)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 und 131.107.155.11</p></td>
<td><p>Externe Zugriffs-Edgedienst-Schnittstelle (Contoso). Wird ggf. für alle SIP-Domänen mit Lync-fähigen Benutzern wiederholt.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 und 131.107.155.21</p></td>
<td><p>Externe Schnittstelle des Webkonferenz-Edgediensts</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 und 131.107.155.31</p></td>
<td><p>Externe Schnittstelle des A/V-Edgediensts</p></td>
</tr>
<tr class="even">
<td><p>Externes DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgediensts. Erforderlich, damit die automatische Konfiguration von Lync 2013- und Lync 2010-Clients extern funktionsfähig ist. Wird ggf. für alle SIP-Domänen mit Lync-fähigen Benutzern wiederholt.</p></td>
</tr>
<tr class="odd">
<td><p>Externes DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgediensts. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als &quot;Zugelassene SIP-Domäne&quot; (in Vorgängerversionen als erweiterter Verbund bezeichnet). Wird ggf. für alle SIP-Domänen mit Lync-fähigen Benutzern wiederholt.</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 und 172.25.33.11</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>


## Erforderliche Einträge für den Partnerverbund


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des SIP- Zugriffs-Edgediensts. Erforderlich für die automatische DNS-Suche eines Verbunds mit anderen potenziellen Verbundpartnern, bezeichnet als &quot;Zugelassene SIP-Domäne&quot; (in Vorgängerversionen als erweiterter Verbund bezeichnet).</p>
<div>

> [!IMPORTANT]
> Wird ggf. für alle SIP-Domänen mit Lync-fähigen Benutzern und Microsoft Lync Mobile-Clients wiederholt, die entweder den Pushbenachrichtigungsdienst oder den Apple-Pushbenachrichtigungsdienst verwenden.


</div></td>
</tr>
</tbody>
</table>


## DNS-Zusammenfassung - Verbindung mit öffentlichen Chatdiensten


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Externe Zugriffs-Edgedienst-Schnittstelle (Contoso). Wird ggf. für alle SIP-Domänen mit Lync-fähigen Benutzern wiederholt.</p></td>
</tr>
</tbody>
</table>


## DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wird ggf. für alle internen SIP-Domänen mit Lync-fähigen Benutzern wiederholt, bei denen der Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff mittels einer globalen Richtlinie, einer Standortrichtlinie für den Standort des Benutzers oder einer Benutzerrichtlinie, die auf den Lync-fähigen Benutzer angewendet wird, zulässig ist. Eine zugelassene XMPP-Domäne muss außerdem in der Richtlinie für XMPP-Verbundpartner konfiguriert werden. Weitere Informationen hierzu finden Sie in den Themen unter <strong>Siehe auch</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgediensts auf Ihrem Edgeserver oder Edgepool, von dem der XMPP-Proxy gehostet wird</p></td>
<td><p>Verweist auf den Zugriffs-Edgedienst oder Edgepool, von dem der XMPP-Proxydienst gehostet wird. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>

