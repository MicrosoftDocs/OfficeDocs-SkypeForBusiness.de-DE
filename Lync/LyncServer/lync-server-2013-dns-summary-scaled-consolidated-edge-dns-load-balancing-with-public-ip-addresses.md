---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach. Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.

Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013-Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung der einzelnen konsolidierten Edge-Topologie erforderlich sind, die in der einzelnen konsolidierten Edge-Topologie-Abbildung dargestellt ist. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013-Clients erforderlich sind. Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen Datensätze nicht erforderlich.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>Wichtig: Anforderungen des Edge-Server-Netzwerkadapters

Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist. Beispielsweise würde das Standardgateway auf die externe Firewall verweisen, wie es in der Szenariogröße des skalierten konsolidierten Rands in der [skalierten konsolidierten Kante, dem DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) gezeigt wird.

Sie können zwei Netzwerkadapter auf jedem Edgeserver wie folgt konfigurieren:

  - **Netzwerkadapter 1 – Knoten 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesenem 172.25.33.10
    
    Es wurde kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).

  - **Netzwerkadapter 1 – Knoten 2 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesenem 172.25.33.11
    
    Es wurde kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).

  - **Netzwerkadapter 2 Knoten 1 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Access Edge Service, 131.107.155.20 for Web Conferencing Edge Service, 131.107.155.30 für A/V-Edgedienst.
    
    Die öffentliche IP-Adresse des Zugriffs-Edge-Diensts ist primär mit dem Standardgateway auf den öffentlichen Router (131.107.155.1) eingestellt.
    
    Web Conferencing Edge Service und A/V Edge Service private IP-Adressen sind zusätzliche IP-Adressen im **erweiterten** Abschnitt der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** der **Eigenschaften der LAN-Verbindung** in Windows Server.
    
    <div>
    

    > [!NOTE]  
    > Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden. Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich. Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen. Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.

    
    </div>

  - **Netzwerkadapter 2 Knoten 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.11 für Access Edge Service, 131.107.155.21 for Web Conferencing Edge Service, 131.107.155.31 für A/V-Edgedienst.
    
    Die öffentliche IP-Adresse des Zugriffs-Edge-Diensts ist primär mit dem Standardgateway auf den öffentlichen Router (131.107.155.1) eingestellt.
    
    Web Conferencing Edge Service und A/V Edge Service private IP-Adressen sind zusätzliche IP-Adressen im **erweiterten** Abschnitt der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** der **Eigenschaften der LAN-Verbindung** in Windows Server.

<div>


> [!TIP]  
> Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen. Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden. Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>DNS-Einträge, die für den skalierten konsolidierten Edge erforderlich sind, DNS-Lastenausgleich mit öffentlichen IP-Adressen (Beispiel)

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
<td><p>131.107.155.10 und 131.107.155.11</p></td>
<td><p>Access Edge Service External Interface (Contoso) wiederholen Sie diese nach Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 und 131.107.155.21</p></td>
<td><p>Web Conferencing Edge Service-externe Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 und 131.107.155.31</p></td>
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
<td><p>Für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen), ist die externe Schnittstelle des Zugriffs-Edge-Diensts erforderlich. Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 und 172.25.33.11</p></td>
<td><p>Konsolidierte Edge-Schnittstelle</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Für den Verbund erforderliche Datensätze


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Die externe Schnittstelle für den SIP-Zugriffs-Edgedienst ist für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (genannt Enhanced Federation in früheren Versionen).</p>
<div>

> [!IMPORTANT]  
> Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push-Benachrichtigungsdienst verwenden.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>DNS-Zusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten durch die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf die Lync-fähiger Benutzer. Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden. Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</p></td>
<td><p>Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

