---
title: 'Lync Server 2013: DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich'
TOCTitle: DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398670(v=OCS.15)
ms:contentKeyID: 49294615
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Anforderungen für DNS-Einträge für den Remotezugriff auf Lync Server 2013 sind im Vergleich zu den Anforderungen für Zertifikate und Ports recht einfach. Darüber hinaus sind viele Einträge optional, je nachdem, wie Sie Clients, auf denen Lync 2013 ausgeführt wird, konfigurieren und ob Sie einen Partnerverbund aktivieren.

Ausführliche Informationen zu den DNS-Anforderungen für Lync 2013 finden Sie unter [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zur automatischen Konfiguration von Lync 2013-Clients bei nicht konfiguriertem Split-Brain-DNS finden Sie im Abschnitt "Automatische Konfiguration ohne Split-Brain-DNS" in [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle zeigt eine Übersicht über die DNS-Einträge, die erforderlich sind, um die in der Abbildung "Skalierte konsolidierte Edgetopologie (mit Hardwarelastenausgleich)" gezeigte Topologie zu unterstützen. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von Lync-Clients erforderlich sind. Wenn Sie Lync-Clients mithilfe von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) konfigurieren möchten, sind die zugeordneten Einträge nicht erforderlich.

## WICHTIG: Netzwerkadapteranforderungen für Edgeserver

Zur Vermeidung von Routingproblemen müssen Sie sicherstellen, dass mindestens zwei Netzwerkadapter auf den Edgeservern vorhanden sind, und dass das Standardgateway nur für den Netzwerkadapter konfiguriert wurde, der der externen Schnittstelle zugeordnet ist. Wie in der Abbildung "Skaliertes konsolidiertes Edgeszenario" unter [Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) gezeigt, würde das Standardgateway beispielsweise auf die externe Firewall zeigen.

Sie können auf jedem Ihrer Edgeserver wie folgt zwei Netzwerkadapter konfigurieren:

  - **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Kein Standardgateway.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeserver-Schnittstelle zu beliebigen Netzwerken mit Lync Server-Clients oder Servern vorhanden ist, auf denen Lync Server ausgeführt wird (z. B. von 172.25.33.0 zu 192.168.10.0).

  - **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter wurden drei öffentliche IP-Adressen zugewiesen, zum Beispiel 131.107.155.10 für den Zugriffs-Edgedienst, 131.107.155.20 für den Webkonferenz-Edgedienst und 131.107.155.30 für den A/V-Edgedienst.
    

    > [!NOTE]
    > Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edgeservers zugewiesen werden, hängen u.&nbsp;U. davon ab, welches Hardwaregerät zum Lastenausgleich Sie wählen. Lesen Sie die Dokumentation für Ihr Hardwaregerät zum Lastenausgleich, um die tatsächlichen IP-Adressenanforderungen zu verstehen.<BR>Es ist möglich, jedoch nicht zu empfehlen, eine einzelne IP-Adresse für alle drei Edgedienst-Schnittstellen zu verwenden. Dadurch werden zwar IP-Adressen gespart, aber für jeden Dienst sind unterschiedliche Portnummern erforderlich. Die Standardportnummer ist 443/TCP, womit sichergestellt wird, dass die meisten Remotefirewalls den Datenverkehr zulassen. Wenn Sie die Portwerte z.&nbsp;B. in 5061/TCP für den Zugriffs-Edgedienst ändern, könnten 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst Probleme für Remotebenutzer verursachen, wenn deren Firewall den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Darüber hinaus wird durch drei eindeutige IP-Adressen die Problembehandlung vereinfacht, da nach der IP-Adresse gefiltert werden kann.

    
    Die IP-Adresse des Zugriffs-Edgediensts ist als primär und das Standardgateway auf den integrierten Router festgelegt (131.107.155.1).
    
    IP-Adressen für den Webkonferenz-Edgedienst und den A/V-Edgedienst sind als sekundär festgelegt.


> [!TIP]
> Das Konfigurieren von zwei Netzwerkadaptern für den Edgeserver ist eine von zwei möglichen Optionen. Die andere Option besteht darin, einen einzigen Netzwerkadapter für die interne Schnittstelle und drei Netzwerkadapter für die externe Schnittstelle des Edgeservers zu verwenden. Der wichtigste Vorteil dieser Option ist ein separater Netzwerkadapter pro Edgeserverdienst und eine möglicherweise präzisere Datenerfassung, falls eine Problembehandlung erforderlich ist.



### Erforderliche DNS-Einträge für eine skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich (Beispiel)

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
<td><p>Externe Zugriffs-Edgedienst-Schnittstelle (Contoso). Wiederholen Sie dies nach Bedarf für alle SIP-Domänen mit Lync-aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Externe Schnittstelle des Webkonferenz-Edgediensts</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>Externe SIP- Zugriffs-Edgedienst-Schnittstelle. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als &quot;Zugelassene SIP-Domäne&quot; (in Vorgängerversionen als erweiterter Verbund bezeichnet). Wiederholen Sie dies nach Bedarf für alle SIP-Domänen mit Lync-aktivierten Benutzern und Microsoft Lync Mobile-Clients, die entweder den Pushbenachrichtigungsdienst oder den Apple-Pushbenachrichtigungsdienst verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>

