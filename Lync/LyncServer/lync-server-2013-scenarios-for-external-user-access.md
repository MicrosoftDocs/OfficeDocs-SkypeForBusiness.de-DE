---
title: 'Lync Server 2013: Szenarien für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Das Bereitstellen des Zugriffs externer Benutzer für lync Server 2013 setzt voraus, dass Sie mindestens einen Edgeserver und einen Reverse-Proxy in Ihrem Umkreisnetzwerk bereitstellen. Optional können Sie einen Director-oder Director-Pool in Ihrem internen Netzwerk bereitstellen.

Wenn Sie eine größere Kapazität benötigen, als ein einzelner Edgeserver bereitstellen kann, oder wenn Sie eine hohe Verfügbarkeit für Ihre Edge-Server Bereitstellung benötigen, können Sie den Lastenausgleich konfigurieren und mehrere Edgeserver in einem Lastenausgleichspool bereitstellen. Wenn Ihre Organisation über mehrere Rechenzentren verfügt, können Sie Edge-Server-oder Edge-Pool-Bereitstellungen an mehr als einem Standort haben. Allerdings kann nur eine der Edge-Server-Bereitstellungen als Verbund Route festgelegt werden.

In diesem Abschnitt werden die Szenarien für die Bereitstellung von Edge-Servern definiert und die Planungsabschnitte den möglichen Szenarien zugeordnet. Wenn Ihre Bereitstellung beispielsweise eine höhere Verfügbarkeit erfordert, Föderation mit den Funktionen für erweiterbare Messaging und Anwesenheitsinformationen (XMPP) und lync Mobility, würden Sie die übereinstimmenden Einträge in der folgenden Tabelle auswählen, die diese Anforderungen erfüllen, und die Verwendung der referenzierte Planungsabschnitte, um Ihre Bereitstellung zu definieren, wie im folgenden Flussdiagramm dargestellt.

**Auswahlverfahren für Edge-Server-Bereitstellungsszenarien**

![Beispiel Bereitstellungs Flussdiagramm] (images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Beispiel Bereitstellungs Flussdiagramm")

Mithilfe dieses Vorgangs können Sie die Konfiguration aller potenziellen Features planen und dokumentieren, die Sie für Ihre Benutzer bereitstellen möchten. Sie können jedoch Föderations-und Mobilitätsdienste hinzufügen, nachdem Sie den Edgeserver bereitgestellt und den richtigen Vorgang bestätigt haben, bevor Sie weitere Features hinzufügen. Der Vorgang zum Hinzufügen von Features zu einer vorhandenen Edge-Server-Bereitstellung wird im Abschnitt Bereitstellung behandelt. Details zur Bereitstellung finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) durch einschließen der Planung für diese Features während des anfänglichen Planungsprozesses können Sie die DNS-, Firewall-und Zertifikatanforderungen für die hinzugefügten Features vorbereiten. Damit können Sie die Zertifikate erwerben und die DNS-und Port/Protocol-Anforderungen im Voraus konfigurieren.

<div>


> [!TIP]  
> Wenn Sie beabsichtigen, die Edgeserver und Reverse Proxy zu installieren und später Features hinzuzufügen (beispielsweise Föderation und Mobilität), legen Sie fest, welche Zertifikate für alle Dienste nach der Bereitstellung erforderlich sind. Wenn Sie die Zertifikate für alle Features im Voraus planen und erwerben, zunächst bereitgestellt oder nicht, müssen Sie keine neuen Zertifikate mehr anfordern, um die Anforderungen des Verbandes (also auf den Edgeserver) oder des Reverse-Proxys (also für Mobilität) zu erfüllen. Services).



</div>

<div>


> [!NOTE]  
> Alle Edge-Dienste werden auf jedem Edgeserver ausgeführt. Dienste können nicht zwischen zwei verschiedenen Edge-Servern aufgeteilt werden. Wenn Sie einen Edge-Pool für Skalierbarkeit bereitstellen, werden alle Edge-Dienste auf jedem Edgeserver im Pool bereitgestellt. XMPP Federation, Office Communications Server und lync Server Federation, öffentliche Chat Verbindungen und Clientmobilität sind zusätzliche Dienste, die bereitgestellt werden können, nachdem Sie Ihren First Edge-Server oder Edge-Pool bereitgestellt haben. Mobility Services ist ein Feature, das den Reverse-Proxy verwendet. Die Installation von Mobility Services fügt Ihren Edge-Servern keine Features hinzu, erfordert aber eine Neukonfiguration Ihres Reverse-Proxys. In der Spalte " <STRONG>Installationsziel</STRONG> ", in der diese Features aufgelistet sind, finden Sie Planungsanleitungen in der zugehörigen Spalte unter <STRONG>Edge-Server-Planning-Abschnitt oder Abschnitte</STRONG> für die gleichzeitige Planung der bereitzustellenden Features, wenn die Edgeserver verwendet werden. installiert und konfiguriert.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identifizieren und Zuordnen von Bereitstellungszielen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Installationsziel</th>
<th>Dokumentation zur Edge-Server-Planung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sie haben entschieden, dass ein einzelner Server für Edge-Dienste in Ihrer Infrastruktur ausreicht. Darüber hinaus beabsichtigen Sie, private IP-Adressen für die externen Edge-Server-Schnittstellen mit NAT in das Internet zu verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen einen Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden NAT, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass ein einzelner Server für Edge-Dienste in Ihrer Infrastruktur ausreicht. Sie beabsichtigen auch, öffentliche IP-Adressen für die externen Edge-Server-Schnittstellen für das Internet zu verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen einzelnen Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen einen Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind. Anstelle von NAT verwenden Sie Routing in diesem Szenario. Die tatsächliche öffentliche IP-Adresse des Edge-Servers wird für externe Benutzer Verbindungen bereitgestellt.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass eine höhere Verfügbarkeit der Edge-Dienste für Ihre Benutzer wichtig ist, und Sie werden zwei oder mehr Edgeserver in diesem Pool bereitstellen. Darüber hinaus beabsichtigen Sie, private IP-Adressen für die externen Edge-Server-Schnittstellen mit NAT in das Internet zu verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit privaten IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen. Sie verwenden NAT, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Sie haben entschieden, dass eine höhere Verfügbarkeit der Edge-Dienste für Ihre Benutzer wichtig ist, und Sie werden zwei oder mehr Edgeserver in diesem Pool bereitstellen. Sie beabsichtigen auch, öffentliche IP-Adressen für die externen Edge-Server-Schnittstellen für das Internet zu verwenden.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, indem Sie den DNS-Lastenausgleich verwenden, um die Kommunikation über den Pool zu verteilen. Anstelle von NAT verwenden Sie Routing, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Sie haben entschieden, dass die hohe Verfügbarkeit der Edge-Dienste für Ihre Benutzer wichtig ist, und dass Sie zwei oder mehr Edgeserver in diesem Pool mithilfe eines Hardwarelastenausgleichs bereitstellen.</p>
<p>Verwenden Sie diesen Planungsabschnitt, wenn Sie einen Pool von Edgeserver in Ihrem Umkreis bereitstellen. Sie stellen die Edgeserver mit öffentlichen IP-Adressen bereit, die dem Edgeserver zugewiesen sind, und verwenden Hardwarelastenausgleichs, um die Kommunikation über den Pool zu verteilen. Anstelle von NAT verwenden Sie Routing, um die öffentlichen IP-Adressen für die externen Benutzer im Internet bereitzustellen.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>In den Verbundszenarien können Sie das Feature planen, mit dem die Typen von Partnern erweitert werden, mit denen Ihre Benutzer kommunizieren können.</p>
<ul>
<li><p>Lync Server-Verbund</p></li>
<li><p>Office Communications Server-Föderation</p></li>
<li><p>Verbindung mit öffentlichen Chatdiensten</p></li>
<li><p>XMPP-Föderation</p></li>
</ul></td>
<td><p>Planen von Verbundszenarien</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planen der lync Server 2013-und Office Communications Server-Föderation</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planen der öffentlichen Instant Messaging-Konnektivität in lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planen der erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP)-Föderation in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Mobilitätsdienste werden über den Reverse-Proxy angeboten. Dienste, die die Mobilität für externe Benutzer ermöglichen, werden auf dem Front-End-Server oder im Front-End-Pool bereitgestellt. Sie erstellen oder ändern vorhandene Veröffentlichungsregeln auf dem Reverse-Proxy, um Mobilitätsdienste für Ihre externen Benutzer zu aktivieren.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> In den folgenden Szenarien sind Abschnitte Referenzarchitekturen, Beispiel-DNS, Port/Protokoll-Definitionen und Zertifikatanforderungen. Ebenfalls enthalten sind Diagramme für Ihre DNS-, Port/Protocol-Definitionen und Zertifikatanforderungen. In den Diagrammen wird eine Vorlage bereitgestellt, die Sie ausfüllen und an andere Teams verteilen können (beispielsweise das Netzwerkteam Ihrer Organisation, das Team für öffentliche Schlüsselinfrastruktur und das Server Bereitstellungsteam). Das Ziel der Diagramme besteht darin, die Kommunikation zu verbessern und den Erfolg zu gewährleisten, wenn die erforderlichen Edge-Server-Konfigurationselemente den Personen mitgeteilt werden, die die eigentliche Konfigurationsarbeit durchführen. Wir empfehlen, dass Sie die Diagramme und zugehörigen Referenzarchitekturen verwenden, um Ihre Bereitstellung zu planen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

