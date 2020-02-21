---
title: 'Lync Server 2013: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
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
ms.openlocfilehash: 48dab867ac7ae408f544e4dbc6bc55ff555e20a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-09_

Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert. Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.

Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 Clients erforderlich sind. Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter

Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist. Beispielsweise zeigt das Standardgateway, wie im Szenario "skalierte konsolidierte Edgeserver" im [skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , auf die externe Firewall hin.

Sie können auf jedem Ihrer Edgeserver wie folgt zwei Netzwerkadapter konfigurieren:

  - **Netzwerkadapter 1 - Knoten 1 (Interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.

  - **Netzwerkadapter 1 - Knoten 2 (Interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.11.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.

  - **Netzwerkadapter 2 - Knoten 1 (Externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Zugriffs-Edgedienst, 131.107.155.20 für Webkonferenz-Edgedienst, 131.107.155.30 für A/V-Edgedienst.
    
    Die Zugriffs-Edgedienst öffentliche IP-Adresse ist primär, wobei das Standardgateway auf den öffentlichen Router (131.107.155.1) festgelegt ist.
    
    Webkonferenz-Edgedienst und A/V-Edgedienst private IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der Eigenschaften für die **LAN-Verbindung** in Windows Server.
    
    <div>
    

    > [!NOTE]  
    > Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben. Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen. Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für die Zugriffs-Edgedienst, 444/TCP für die Webkonferenz-Edgedienst und 443/TCP für die A/V-Edgedienst kann Probleme für Remotebenutzer verursachen, bei denen eine Firewall, hinter der Sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Darüber hinaus wird durch drei eindeutige IP-Adressen die Problembehandlung vereinfacht, da nach der IP-Adresse gefiltert werden kann.

    
    </div>

  - **Netzwerkadapter 2 – Knoten 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.11 für Zugriffs-Edgedienst, 131.107.155.21 für Webkonferenz-Edgedienst, 131.107.155.31 für A/V-Edgedienst.
    
    Die Zugriffs-Edgedienst öffentliche IP-Adresse ist primär, wobei das Standardgateway auf den öffentlichen Router (131.107.155.1) festgelegt ist.
    
    Webkonferenz-Edgedienst und A/V-Edgedienst private IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der Eigenschaften für die **LAN-Verbindung** in Windows Server.

<div>


> [!TIP]  
> Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen. Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden. Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>Erforderliche DNS-Einträge für einen skalierten konsolidierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen (Beispiel)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS-Eintrag</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 und 131.107.155.11</p></td>
<td><p>Zugriffs-Edgedienst externe Schnittstelle (Contoso) bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern wiederholen</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 und 131.107.155.21</p></td>
<td><p>Webkonferenz-Edgedienst externe Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/A-Eintrag</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 und 131.107.155.31</p></td>
<td><p>A/V-Edgedienst externe Schnittstelle</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst externe Schnittstelle. Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich. Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</p></td>
</tr>
<tr class="odd">
<td><p>Externes DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung von Verbundpartnern erforderlich ist, die als "zugelassene SIP-Domäne" bezeichnet werden (als erweiterter Verbund in früheren Versionen bezeichnet). Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 und 172.25.33.11</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Für den Verbund erforderliche Einträge


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/Typ/Port</th>
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung ihres Verbunds für andere potenzielle Verbundpartner erforderlich ist, und wird als "zugelassene SIP-Domänen" bezeichnet ("Enhanced Federation" in früheren Versionen genannt).</p>
<div>

> [!IMPORTANT]  
> Wiederholen Sie diese Schritte bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push Notification-Dienst verwenden.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/Typ/Port</th>
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe DNS/SRV/5269</p></td>
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie diese Schritte bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf den Lync-aktivierter Benutzer. Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden. Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</p></td>
<td><p>Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten. Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

