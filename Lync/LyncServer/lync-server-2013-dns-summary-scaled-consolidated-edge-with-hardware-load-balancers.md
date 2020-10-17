---
title: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5847a43c6d07cf188c97cd8de6a47dfb83e1468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501282"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-27_

Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert. Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.

Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Die folgende Tabelle zeigt eine Übersicht über die DNS-Einträge, die erforderlich sind, um die in der Abbildung "Skalierte konsolidierte Edgetopologie (mit Hardwarelastenausgleich)" gezeigte Topologie zu unterstützen. Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration für lync-Clients erforderlich sind. Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter

Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist. Beispielsweise zeigt das Standardgateway wie im Szenario skalierte konsolidierte Edgeserver in [skaliertem konsolidierten Edgeserver mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)auf die externe Firewall hin.

Sie können zwei Netzwerkadapter auf jedem ihrer Edgeserver wie folgt konfigurieren:

  - **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.
    
    Kein Standardgateway.
    
    Stellen Sie sicher, dass es eine Route vom Netzwerk mit der Edgeserver internen Schnittstelle zu Netzwerken gibt, die lync Server Clients oder Server mit lync Server (beispielsweise von 172.25.33.0 nach 192.168.10.0) enthalten.

  - **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Zugriffs-Edgedienst, 131.107.155.20 für Webkonferenz-Edgedienst, 131.107.155.30 für A/V-Edgedienst.
    
    <div>
    

    > [!NOTE]
    > Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edgeserver zugewiesen werden, hängen möglicherweise von dem von Ihnen ausgewählten Hardwaregerät für den Lastenausgleich ab. Lesen Sie in der Dokumentation zum Hardwaregerät zum Lastenausgleich nach, um die tatsächlichen Anforderungen an IP-Adressen zu verstehen.<BR>Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben. Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen. Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für die Zugriffs-Edgedienst, 444/TCP für die Webkonferenz-Edgedienst und 443/TCP für die A/V-Edgedienst kann Probleme für Remotebenutzer verursachen, bei denen eine Firewall, hinter der Sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.

    
    </div>
    
    Zugriffs-Edgedienst IP-Adresse ist primär, wobei das Standardgateway auf den Internet-Router (131.107.155.1) festgelegt ist.
    
    Webkonferenz-Edgedienst-und A/V-Edgedienst-IP-Adressen sekundär.

<div>


> [!TIP]
> Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen. Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden. Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Erforderliche DNS-Einträge für eine skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich (Beispiel)

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
<td><p>Zugriffs-Edgedienst externe Schnittstelle (Contoso). Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Webkonferenz-Edgedienst externe Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V-Edgedienst externe Schnittstelle</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst externe Schnittstelle. Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich. Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</p></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung von Verbundpartnern erforderlich ist, die als "zugelassene SIP-Domäne" bezeichnet werden (als erweiterter Verbund in früheren Versionen bezeichnet). Wiederholen Sie diese Schritte bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push Notification-Dienst verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interne Schnittstelle des konsolidierten Edgeservers</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

