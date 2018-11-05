---
title: 'Lync Server 2013: Szenarien für den Zugriff durch externe Benutzer'
TOCTitle: Szenarien für den Zugriff durch externe Benutzer
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425727(v=OCS.15)
ms:contentKeyID: 49293453
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zur Bereitstellung des externen Benutzerzugriffs für Lync Server 2013 ist es erforderlich, dass Sie mindestens einen Edgeserver und einen Reverseproxy in Ihrem Umkreisnetzwerk bereitstellen. Optional können Sie einen Director oder Directorpool in Ihrem internen Netzwerk bereitstellen.

Wenn Sie eine höhere Kapazität benötigen, als ein einzelner Edgeserver bieten kann, oder wenn Sie hohe Verfügbarkeit für Ihre Edgeserver-Bereitstellung sicherstellen müssen, können Sie Lastenausgleich konfigurieren und mehrere Edgeserver in in einem Pool mit Lastenausgleich bereitstellen. Wenn Ihre Organisation über mehrere Rechenzentren verfügt, können Sie Edgeserver- oder Edgepool-Bereitstellungen an mehr als einem Standort konfigurieren. Es kann jedoch nur eine der Edgeserver-Bereitstellungen als Route für den Verbundpartner zugewiesen werden.

In diesem Abschnitt werden die Szenarien für Edgeserver-Bereitstellungen definiert und die Planungsabschnitte den möglichen Szenarien zugeordnet. Wenn für Ihre Bereitstellung beispielsweise hohe Verfügbarkeit, ein Verbund mit XMPP (Extensible Messaging and Presence Protocol)-Kontakten und Lync-Mobilität erforderlich sind, würden Sie die entsprechenden Einträge in der folgenden Tabelle auswählen, die diese Anforderungen erfüllen, und die referenzierten Planungsabschnitte verwenden, um die Bereitstellung zu definieren (siehe folgendes Flussdiagramm).

**Auswahl des Szenarios für die Bereitstellung von Edgeservers**

![Beispielbereitstellung (Flussdiagramm)](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Beispielbereitstellung (Flussdiagramm)")

Bei Verwendung dieses Prozesses können Sie die Konfiguration aller möglichen Features planen und dokumentieren, die Sie für Ihre Benutzer bereitstellen möchten. Sie können jedoch Verbund- und Mobilitätsdienste hinzufügen, nachdem Sie den Edgeserver bereitgestellt und den fehlerfreien Betrieb überprüft haben, bevor Sie weitere Features hinzufügen. Der Prozess zum Hinzufügen von Features zu einer vorhandenen Edgeserver-Bereitstellung wird im Abschnitt zur Bereitstellung erläutert. Ausführliche Informationen zum Bereitstellen finden Sie unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Indem Sie Pläne für diese Features in den anfänglichen Planungsprozess aufnehmen, können Sie Vorbereitungen für die DNS-, Firewall- und Zertifikatanforderungen für die hinzugefügten Features treffen. Dadurch wird das Erwerben von Zertifikaten und Konfigurieren von DNS- und Port-/Protokollanforderungen im Voraus ermöglicht.


> [!TIP]
> Wenn die Edgeserver und den Reverseproxy installieren und Features (z.&nbsp;B. Verbund und Mobilität) später hinzufügen möchten, ermitteln Sie, welche Zertifikate Sie für alle Dienste nach der Bereitstellung benötigen. Wenn Sie die Zertifikate für alle Features im Voraus planen und erwerben (unabhängig davon, ob sie anfänglich bereitgestellt werden), müssen Sie später keine neuen Zertifikate bestellen, um die Anforderungen des Verbunds (d.&nbsp;h. auf den Edgeservern) oder des Reverseproxys (d.&nbsp;h. für Mobilitätsdienste) zu erfüllen.




> [!NOTE]
> Alle Edgedienste werden auf jedem Edgeserver ausgeführt. Dienste können nicht auf zwei unterschiedliche Edgeserver aufgeteilt werden. Wenn Sie aus Gründen der Skalierbarkeit einen Edgepool bereitstellen, werden alle Edgedienste auf jedem Edgeserver im Pool bereitgestellt. XMPP-Verbund, Office Communications Server und Lync Server-Verbund, Verbindungen zu öffentlichen Instant&nbsp;Messaging-Diensten und Clientmobilität sind zusätzliche Dienste, , die nach der Bereitstellung des ersten Edgeservers oder Edgepools bereitgestellt werden können. Bei den Mobilitätsdiensten handelt es sich um ein Feature, das den Reverseproxy verwendet. Bei der Installation der Mobilitätsdienste werden den Edgeservern keine Features hinzugefügt, es ist jedoch eine Neukonfiguration des Reverseproxys erforderlich. Die Spalte <STRONG>Installationsziel</STRONG>, in der diese Features aufgeführt sind, enthält eine Planungsanweisung in der zugehörigen Spalte unter <STRONG>Abschnitt(e) zur Planung von Edgeservern</STRONG> für die gleichzeitige Planung dieser Features, die bei der Installation und Konfiguration der Edgeserver bereitgestellt werden sollen.



## Ermitteln und Zuordnen der Bereitstellungsziele


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Installationssziel</th>
<th>Planungsdokumentation für Edgeserver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sie haben entschieden, dass ein einzelner Server für die Edgedienste in Ihrer Infrastruktur ausreichend ist. Außerdem möchten Sie private IP-Adressen für die externen Schnittstellen des Edgeservers mit NAT zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen einen Edgeserver mit privater, dem Edgeserver zugewiesener IP-Adresse bereit und geben mit NAT die öffentlichen IP-Adressen für die externen Benutzer im Internet an.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass ein einzelner Server für die Edgedienste in Ihrer Infrastruktur ausreichend ist. Außerdem möchten Sie öffentliche IP-Adressen für die externen Schnittstellen des Edgeservers zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen einen Edgeserver mit öffentlicher, dem Edgeserver zugewiesener IP-Adresse bereit. Anstelle von NAT verwenden Sie Routing in diesem Szenario. Die tatsächliche öffentliche IP-Adresse des Edgeservers wird für Verbindungen von externen Benutzern verfügbar gemacht.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit. Sie möchten außerdem private IP-Adressen für die externen Schnittstellen der Edgeserver mit NAT zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeservern in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit privaten, dem Edgeserver zugewiesenen IP-Adressen bereit und verwenden den DNS-Lastenausgleich, um die Kommunikation im Pool zu ermöglichen. Mit NAT stellen Sie die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit. Sie möchten außerdem öffentliche IP-Adressen für die externen Schnittstellen des Edgeservers zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeservern in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen, dem Edgeserver zugewiesenen IP-Adressen bereit und verwenden den DNS-Lastenausgleich, um die Kommunikation im Pool zu ermöglichen. Anstelle von NAT stellen Sie mithilfe von Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool mit einem Hardwaregerät zum Lastenausgleich bereit.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeservern in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen, dem Edgeserver zugewiesenen IP-Adressen bereit und verwenden Hardwaregeräte zum Lastenausgleich, um die Kommunikation im Pool zu ermöglichen. Anstelle von NAT stellen Sie mit Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Die Verbundszenarien ermöglichen die Planung für das Feature, das die Typen der Partner erweitert, mit denen Ihre Benutzer kommunizieren können.</p>
<ul>
<li><p>Lync Server-Verbund</p></li>
<li><p>Office Communications Server-Verbund</p></li>
<li><p>Verbindung mit öffentlichen Instant Messaging-Diensten</p></li>
<li><p>XMPP-Verbund</p></li>
</ul></td>
<td><p>Planen von Verbundszenarien</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planen von Lync Server- und Office Communications Server-Partnerverbünden</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planen von Verbindungen mit öffentlichen Instant Messaging-Diensten</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planen eines XMPP-Partnerverbunds (Extensible Messaging and Presence Protocol) in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Mobilitätdienste werden über den Reverseproxy bereitgestellt. Dienste, die Mobilität für externe Benutzer ermöglichen, werden auf dem Front-End-Server oder im Front-End-Pool bereitgestellt. Sie erstellen oder ändern vorhandene Veröffentlichungsregeln auf dem Reverseproxy, um Mobilitätsdienste für Ihre externen Benutzer zu aktivieren.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>



> [!TIP]
> Die folgenden Szenarioabschnitte enthalten Referenzarchitekturen, Beispiel-DNS, Port-/Protokolldefinitionen und Zertifikatanforderungen. Darüber hinaus sind Diagramme für Ihr DNS, Ihre Port-/Protokolldefinitionen und Zertifikatanforderungen enthalten. Die Diagramme enthalten eine Vorlage, die Sie ausfüllen und an andere Teams (z.&nbsp;B. das Netzwerkteam, PKI (Public Key Infrastructure)-Team oder Serverbereitstellungsteam) weiterleiten können. Das Ziel der Diagramme besteht darin, die Kommunikation zu verbessern und eine erfolgreiche Weiterleitung der erforderlichen Edgeserver-Konfigurationselemente an die Personen zu gewährleisten, die die Konfiguration tatsächlich vornehmen. Es wird empfohlen, die Diagramme und zugehörigen Referenzarchitekturen zum Planen der Bereitstellung zu verwenden.


