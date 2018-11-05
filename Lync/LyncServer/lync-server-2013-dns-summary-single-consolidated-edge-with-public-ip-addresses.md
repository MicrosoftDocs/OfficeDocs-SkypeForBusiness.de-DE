---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen'
TOCTitle: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205025(v=OCS.15)
ms:contentKeyID: 49294506
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die Anforderungen für DNS-Einträge für den Remotezugriff auf Lync Server 2013 sind im Vergleich zu den Anforderungen für Zertifikate und Ports recht einfach. Darüber hinaus sind viele Einträge optional, je nachdem, wie Sie Clients, auf denen Lync 2013 ausgeführt wird, konfigurieren und ob Sie einen Partnerverbund aktivieren.

Ausführliche Informationen zu den DNS-Anforderungen für Lync 2013 finden Sie unter [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zur automatischen Konfiguration von Clients, auf denen Lync 2013ausgeführt wird, wenn Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "Automatische Konfiguration ohne Split-Brain-DNS" in [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich sind, wie sie in der Abbildung "Topologie mit einem einzelnen konsolidierten Edgeserver" gezeigt wird. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von Lync 2013- und Lync 2010-Clients erforderlich sind. Wenn Sie Lync-Clients mithilfe von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) konfigurieren möchten, sind die zugeordneten automatischen Konfigurationseinträge nicht erforderlich.

## WICHTIG: Netzwerkadapteranforderungen für Edgeserver

Zur Vermeidung von Routingproblemen müssen Sie sicherstellen, dass mindestens zwei Netzwerkadapter auf den Edgeserver vorhanden sind, und dass das Standardgateway nur für den Netzwerkadapter konfiguriert wurde, der der externen Schnittstelle zugeordnet ist. Wie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen“ in [Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md) gezeigt, würde das Standardgateway beispielsweise auf den externen Router in Ihrem Internetperimeter oder eine externe Firewall zeigen, die eine öffentliche IP-Adresse angibt. Bei dem Netzwerkverhältnis für Edgeserver-Schnittstellen handelt es sich um ein Routenverhältnis, nicht um ein NAT-Verhältnis.

Sie können die zwei Netzwerkadapter auf Ihrem Edgeserver folgendermaßen konfigurieren:

  - **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu beliebigen Netzwerken mit Servern vorhanden ist, auf denen Lync Server 2013- oder Lync Server 2013-Clients ausgeführt werden (z. B. von 172.25.33.0 zu 192.168.10.0).

  - **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter sind drei öffentliche IP-Adressen zugewiesen, z. B. 131.107.155.10 für den Zugriffs-Edgeserver, 131.107.155.20 für den Webkonferenz-Edgeserver und 131.107.155.30 für den A/V-Edgeserver.
    

    > [!NOTE]
    > Es ist möglich, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Dies wird jedoch nicht empfohlen. Obwohl Sie dadurch IP-Adressen sparen können, sind für jeden Dienst andere Portnummern erforderlich. Die Standardportnummer lautet 443/TCP. Dadurch wird sichergestellt, dass die meisten Remotefirewalls den Datenverkehr zulassen. Eine Änderung der Portwerte in (beispielsweise) 5061/TCP für den Zugriffs-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den AV-Edgedienst kann zu Problemen für Remotebenutzer führen, wenn eine Firewall, hinter der sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Zudem wird die Fehlerbehebung bei Verwendung von drei eindeutiger IP-Adressen vereinfacht, da in diesem Fall nach IP-Adressen gefiltert werden kann.

    
    Die öffentliche IP-Adresse des Zugriffs-Edgeservers ist als primär, das Standardgateway ist auf den öffentlichen Router (131.107.155.1) festgelegt.
    
    Bei den öffentlichen IP-Adressen für den Webkonferenz- und A/V-Edgeserver handelt es sich um zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der **Eigenschaften von LAN-Verbindung** in Windows Server.


> [!TIP]
> Das Konfigurieren von zwei Netzwerkadaptern für den Edgeserver ist eine von zwei möglichen Optionen. Die andere Option besteht darin, einen einzigen Netzwerkadapter für die interne Schnittstelle und drei Netzwerkadapter für die externe Schnittstelle des Edgeservers zu verwenden. Der wichtigste Vorteil dieser Option ist ein separater Netzwerkadapter pro Edgeserverdienst und eine möglicherweise präzisere Datenerfassung, falls eine Problembehandlung erforderlich ist.



### Für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen erforderliche DNS-Einträge (Beispiel)

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
<td><p>131.107.155.10</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgeservers (Contoso). Wiederholen Sie den Vorgang ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Externe Schnittstelle des Edgeservers für Webkonferenzen</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Externe Schnittstelle des A/V-Edgeservers</p></td>
</tr>
<tr class="even">
<td><p>Externes DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgeservers. Für die externe Funktion der automatischen Konfiguration von Lync 2013- und Lync 2010-Clients erforderlich. Wiederholen Sie den Vorgang ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern.</p></td>
</tr>
<tr class="odd">
<td><p>Externes DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als &quot;Zugelassene SIP-Domäne&quot; (in Vorgängerversionen als erweiterter Verbund bezeichnet). Wiederholen Sie den Vorgang ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> Die in der vorangegangenen Tabelle aufgeführten Einträge sind entweder mit der Erweiterung <EM>.net</EM> oder der Erweiterung <EM>.com</EM> aufgeführt, um hervorzuheben, in welcher Zone sie platziert werden müssen, wenn kein Split-Brain-DNS verwendet wird. Bei Verwendung von Split-Brain-DNS befinden sich alle Einträge in derselben Zone und unterscheiden sich nur durch die interne oder externe Version. Ausführliche Informationen finden Sie im Abschnitt „Split-Brain-DNS“ unter <A href="lync-server-2013-determine-dns-requirements.md">Ermitteln von DNS-Anforderungen für Lync Server 2013</A>.



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
<td><p>Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche Ihres Verbunds nach weiteren potenziellen Verbundpartnern, bezeichnet als &quot;Zugelassene SIP-Domäne&quot; (in Vorgängerversionen als erweiterter Verbund bezeichnet). Wiederholen Sie den Vorgang ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern.</p>
<div>

> [!IMPORTANT]
> Dieser SRV-Eintrag ist für die Mobilität und das Clearing House für Pushbenachrichtigungen erforderlich


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
<td><p>Externe Schnittstelle des Zugriffs-Edgeservers (Contoso). Wiederholen Sie den Vorgang ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern.</p></td>
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
<td><p>Externe Schnittstelle des XMPP-Proxys für den Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang ggf. für alle internen SIP-Domänen mit für Lync aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten über die Konfiguration der externen Zugriffsrichtlinie per globaler Richtlinie, Richtlinie des Standorts, an dem sich der Benutzer befindet, oder per Benutzerrichtlinie zulässig ist, die auf den für Lync aktivierten Benutzer angewendet wird. Eine zulässige XMPP-Domäne muss zudem in der XMPP-Verbundpartnerrichtlinie konfiguriert werden. Siehe Themen in <strong>Siehe auch</strong> für weitere Einzelheiten</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgediensts auf Ihrem Edgeserver oder Edgepool, von dem der XMPP-Proxy gehostet wird</p></td>
<td><p>Verweist auf den Zugriffs-Edgedienst oder Edgepool, von dem der XMPP-Proxydienst gehostet wird. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>

