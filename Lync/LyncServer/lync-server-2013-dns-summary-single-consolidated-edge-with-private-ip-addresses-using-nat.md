---
title: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97c44b0d199ec257b6e8b8e1d5f4c6d7fa307b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501242"
---
# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-09_

Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert. Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.

Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zur automatischen Konfiguration von Clients, auf denen lync 2013, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie unter "automatische Konfiguration ohne Split-Brain DNS" in [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 und lync 2010 Clients erforderlich sind. Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten automatischen Konfigurationseinträge nicht erforderlich.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter

Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist. Beispielsweise würde das Standardgateway wie in der einzelnen konsolidierten Edge-Topologie in [einem einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)zeigt auf die externe Firewall (10.45.16.1) zeigen.

Sie können die zwei Netzwerkadapter auf Ihrem Edgeserver folgendermaßen konfigurieren:

  - **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.

  - **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 10.45.16.10 für Access Edge, 10.45.16.20 für Webkonferenz-Edge, 10.45.16.30 für AV-Edge
    
    <div>
    

    > [!NOTE]
    > Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben. Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen. Wenn Sie die Portwerte (beispielsweise) auf 5061/TCP für den Zugriffs-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst ändern, kann dies für Remotebenutzer zu Problemen führen, falls eine Firewall, hinter der sich die Benutzer befinden, keinen Datenverkehr über 5061/TCP und 444/TCP zulässt. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.

    
    </div>
    
    Die Zugriffs-Edge-IP-Adresse ist primär, wobei Standardgateway auf integrierter Router (10.45.16.1) festgelegt ist.
    
    Webkonferenz-und A/V-Edge-IP-Adressen sekundär.

<div>


> [!TIP]
> Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen. Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden. Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>Erforderliche DNS-Einträge für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT (Beispiel)

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
<td><p>Externe DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgeservers (Contoso); bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Externe Schnittstelle des Edgeservers für Webkonferenzen</p></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Externe Schnittstelle des A/V-Edgeservers</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des Zugriffs-Edgeservers. Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich. Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</p></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als „Zugelassene SIP-Domäne“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> Die in der vorangegangenen Tabelle aufgeführten Einträge sind entweder mit der Erweiterung <EM>.net</EM> oder der Erweiterung <EM>.com</EM> aufgeführt, um hervorzuheben, in welcher Zone sie platziert werden müssen, wenn kein Split-Brain-DNS verwendet wird. Wenn Sie das Split-Brain-DNS verwenden, befinden sich alle Datensätze in derselben <EM>. com</EM> -Zone, wobei die einzige Unterscheidung darin besteht, ob Sie sich in der internen oder externen DNS-Zonenversion befinden. Ausführliche Informationen finden Sie unter "Split-Brain DNS" in <A href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</A>.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>Für Partnerverbund erforderliche Datensätze


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
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche Ihres Partnerverbungs nach anderen Verbundpartnern, bezeichnet als „Zugelassene SIP-Domänen“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</p>



> [!IMPORTANT]
> Dieser SRV-Eintrag ist für die Mobilitätsfunktion und die Pushbenachrichtigung für Clearinghouse erforderlich.

</td>
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
<td><p>_xmpp-Server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder eine auf den lync-aktivierten Benutzer angewendete Benutzerrichtlinie zulässig ist. Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden. Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</p></td>
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

