---
title: 'Lync Server 2013: Szenarien für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a237a971bbf98636b81fa028c9b64721364fca07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Szenarien für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Für die Bereitstellung von externem Benutzer Zugriff für lync Server 2013 müssen Sie mindestens einen Edgeserver und einen Reverseproxy im Umkreisnetzwerk bereitstellen. Optional können Sie einen Director oder Directorpool im internen Netzwerk bereitstellen.

Wenn Sie mehr Kapazität benötigen, als ein einzelnes Edgeserver bereitstellen kann, oder wenn Sie hohe Verfügbarkeit für Ihre Edgeserver-Bereitstellung benötigen, können Sie den Lastenausgleich konfigurieren und mehrere Edgeserver in einem Lastenausgleichspool bereitstellen. Wenn Ihre Organisation über mehrere Rechenzentren verfügt, können Sie Edgeserver-oder Edgepool-Bereitstellungen an mehr als einem Standort haben. Es kann jedoch nur eine der Edgeserver-Bereitstellungen als Verbund Route festgelegt werden.

In diesem Abschnitt werden die Szenarien für Edgeserver Bereitstellungen definiert und die Planungsabschnitte den möglichen Szenarien zugeordnet. Wenn Ihre Bereitstellung beispielsweise eine hohe Verfügbarkeit, einen Partnerverbund mit XMPP-Kontakten (Extensible Messaging and Presence) und lync Mobility erfordert, wählen Sie in der folgenden Tabelle die übereinstimmenden Einträge aus, die diese Anforderungen erfüllen würden, und verwenden Sie die referenzierte Planungsabschnitte zur Definition Ihrer Bereitstellung, wie im folgenden Flussdiagramm dargestellt.

**Auswahl des Szenarios für die Bereitstellung von Edgeservers**

![Beispiel Bereitstellungs Flussdiagramm](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Beispiel Bereitstellungs Flussdiagramm")

Mit diesem Verfahren können Sie die Konfiguration aller potenziellen Features planen und dokumentieren, die Sie für Ihre Benutzer bereitstellen möchten. Sie können jedoch Verbund-und Mobilitätsdienste hinzufügen, nachdem Sie die Edgeserver bereitgestellt und den korrekten Vorgang vor dem Hinzufügen anderer Features bestätigt haben. Der Vorgang des Hinzufügens von Features zu einer vorhandenen Edgeserver-Bereitstellung wird im Abschnitt Bereitstellung behandelt. Ausführliche Informationen zur Bereitstellung finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) durch einschließen der Planung für diese Features während des anfänglichen Planungsprozesses können Sie die DNS-, Firewall-und Zertifikatanforderungen für die hinzugefügten Features vorbereiten, mit denen Sie die Zertifikate erwerben und die DNS-und Port/Protocol-Anforderungen vorab konfigurieren können.

<div>


> [!TIP]  
> Wenn Sie planen, die Edgeserver und den Reverseproxy zu installieren und später Features hinzuzufügen (beispielsweise "Verbund" und "Mobilität"), legen Sie fest, welche Zertifikate für alle Dienste nach der Bereitstellung erforderlich sind. Das Planen und erwerben der Zertifikate für alle Features im voraus, die anfänglich bereitgestellt werden oder nicht, erspart Ihnen das Anfordern neuer Zertifikate, um die Anforderungen des Verbunds (also auf den Edgeserver) oder des Reverseproxys (also für Mobilität) zu erfüllen. Dienste).



</div>

<div>


> [!NOTE]  
> Alle Edge-Dienste werden auf jeder Edgeserver ausgeführt. Dienste können nicht zwischen zwei unterschiedlichen Edge-Servern aufgeteilt werden. Wenn Sie eine Edgepool für die Skalierbarkeit bereitstellen, werden alle Edgedienst auf jeder Edgeserver im Pool bereitgestellt. XMPP-Partnerverbund, Office Communications Server und lync Server-Verbund, öffentliche Chat-Konnektivität und Clientmobilität sind zusätzliche Dienste, die bereitgestellt werden können, nachdem Sie Ihre erste Edgeserver oder Edgepool bereitgestellt haben. Bei den Mobilitätsdiensten handelt es sich um ein Feature, das den Reverseproxy verwendet. Durch die Installation von Mobilitätsdiensten werden keine Funktionen zu ihren Edgeserver hinzugefügt, es ist jedoch eine Neukonfiguration des Reverseproxys erforderlich. Die Spalte <STRONG>Installationsziel</STRONG> , in der diese Features aufgeführt sind, enthält Planungsanleitungen in der zugehörigen Spalte unter <STRONG>Edgeserver Planning-Abschnitt oder in Abschnitten</STRONG> zur gleichzeitigen Planung dieser Features, die bei der Installation und Konfiguration der Edgeserver bereitgestellt werden sollen.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Ermitteln und Zuordnen der Bereitstellungsziele


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
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen eine Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden NAT, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass ein einzelner Server für die Edgedienste in Ihrer Infrastruktur ausreichend ist. Außerdem möchten Sie öffentliche IP-Adressen für die externen Schnittstellen des Edgeservers zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen eine Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind. Anstelle von NAT verwenden Sie Routing in diesem Szenario. Die tatsächliche öffentliche IP-Adresse des Edgeservers wird für externe Benutzer Verbindungen zur Verfügung gestellt.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit. Sie möchten außerdem private IP-Adressen für die externen Schnittstellen der Edgeserver mit NAT zum Internet verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen. Mit NAT stellen Sie die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass hohe Verfügbarkeit der Edgedienste für Ihre Benutzer wichtig ist und stellen mindestens zwei Edgeserver in diesem Pool bereit. Sie beabsichtigen auch, öffentliche IP-Adressen für die Edgeserver externen Schnittstellen mit dem Internet zu verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen. Anstelle von NAT stellen Sie mit Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass die hohe Verfügbarkeit der Edge-Dienste für Ihre Benutzer wichtig ist, und Sie werden zwei oder mehr Edgeserver in diesem Pool mit einem Hardwaregerät zum Lastenausgleich bereitstellen.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden Hardwarelastenausgleichs zum Verteilen der Kommunikation über den Pool. Anstelle von NAT stellen Sie mit Routing die öffentlichen IP-Adressen für die externen Benutzer im Internet bereit.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Die Verbundszenarien ermöglichen die Planung für das Feature, das die Typen der Partner erweitert, mit denen Ihre Benutzer kommunizieren können.</p>
<ul>
<li><p>Lync Server Partnerverbund</p></li>
<li><p>Office Communications Server Partnerverbund</p></li>
<li><p>Verbindung mit öffentlichen Instant Messaging-Diensten</p></li>
<li><p>XMPP-Verbund</p></li>
</ul></td>
<td><p>Planen von Verbundszenarien</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planung für lync Server 2013 und Office Communications Server Partnerverbund</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planen der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planen des XMPP-Verbunds (Extensible Messaging and Presence Protocol) in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Mobilitätdienste werden über den Reverseproxy bereitgestellt. Dienste, die die Mobilität für externe Benutzer ermöglichen, werden im Front-End-Server oder Front-End-Pool bereitgestellt. Sie erstellen oder ändern vorhandene Veröffentlichungsregeln auf dem Reverseproxy, um Mobilitätsdienste für Ihre externen Benutzer zu aktivieren.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Die folgenden Szenarioabschnitte enthalten Referenzarchitekturen, Beispiel-DNS, Port-/Protokolldefinitionen und Zertifikatanforderungen. Darüber hinaus sind Diagramme für Ihr DNS, Ihre Port-/Protokolldefinitionen und Zertifikatanforderungen enthalten. Die Diagramme enthalten eine Vorlage, die Sie ausfüllen und an andere Teams (z. B. das Netzwerkteam, PKI (Public Key Infrastructure)-Team oder Serverbereitstellungsteam) weiterleiten können. Das Ziel der Diagramme besteht darin, die Kommunikation zu verbessern und den Erfolg zu gewährleisten, wenn die erforderlichen Edgeserver Konfigurationselemente an die Personen kommuniziert werden, die die eigentliche Konfigurationsarbeit erledigen. Es wird empfohlen, die Diagramme und zugehörigen Referenzarchitekturen zum Planen der Bereitstellung zu verwenden.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

