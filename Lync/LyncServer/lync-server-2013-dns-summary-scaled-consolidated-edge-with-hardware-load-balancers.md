---
title: DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-27_

Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach. Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.

Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013-Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die erforderlich sind, um die skalierte konsolidierte Edge-Topologie (Hardware Load Balanced) zu unterstützen. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration für lync-Clients erforderlich sind. Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen Datensätze nicht erforderlich.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>Wichtig: Anforderungen des Edge-Server-Netzwerkadapters

Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist. Beispielsweise würde das Standardgateway auf die externe Firewall verweisen, wie es in der Szenariogröße des skalierten konsolidierten Edges im [skalierten konsolidierten Edge mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)gezeigt wird.

Sie können zwei Netzwerkadapter auf allen Edge-Servern wie folgt konfigurieren:

  - **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesenem 172.25.33.10
    
    Kein Standardgateway.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Schnittstelle des Edge-Servers zu allen Netzwerken vorhanden ist, die lync Server-Clients oder-Server mit lync Server (beispielsweise von 172.25.33.0 bis 192.168.10.0) enthalten.

  - **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Access Edge Service, 131.107.155.20 for Web Conferencing Edge Service, 131.107.155.30 für A/V-Edgedienst.
    
    <div>
    

    > [!NOTE]
    > Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edge-Servers zugewiesen sind, hängen möglicherweise davon ab, welches Hardware Lastenausgleichsmodul Sie auswählen. Informationen zu den tatsächlichen IP-Adressen Anforderungen finden Sie in der Dokumentation Ihres Hardwarelastenausgleichs.<BR>Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden. Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich. Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen. Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr nicht zulässt. 5061/TCP und 444/TCP. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.

    
    </div>
    
    Die IP-Adresse des Zugriffs-Edge-Diensts ist primär mit dem Standardgateway auf Internet-Facing Router (131.107.155.1) eingestellt.
    
    Web Conferencing Edge Service und A/V Edge Service-IP-Adressen sekundär.

<div>


> [!TIP]
> Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen. Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden. Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>DNS-Einträge, die für den skalierten konsolidierten Edge erforderlich sind, Hardware Lastenausgleich (Beispiel)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Access Edge Service External Interface (Contoso). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web Conferencing Edge Service-externe Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Externe Schnittstelle A/V Edge Service</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge Service-externe Schnittstelle. Erforderlich für die automatische Konfiguration von lync 2013-und lync 2010-Clients, um extern zu arbeiten. Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP Access Edge Service-externe Schnittstelle für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push-Benachrichtigungsdienst verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Konsolidierte Edge-Schnittstelle</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

