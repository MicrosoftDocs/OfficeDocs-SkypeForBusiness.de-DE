---
title: 'Lync Server 2013: Ermitteln der Anforderungen für externe A/V-Firewalls und Ports'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Die Kommunikation zwischen Audio und Video (a/V) kann komplex sein. Aufgrund der Art der in A/V verwendeten Protokolle und der Verwendung der Protokolle durch Clients und Server wird ein spezieller Abschnitt für die Erläuterung der Unterschiede zwischen Client-und Server Versionen gerechtfertigt.

Verwenden Sie die folgende A/V-Firewall und Port Tabelle, um die Firewall-Anforderungen und die zu öffnenden Ports zu ermitteln. Überprüfen Sie dann die NAT-Terminologie (Network Address Translation), da NAT auf viele verschiedene Arten implementiert werden kann. Ein detailliertes Beispiel für Firewall-Porteinstellungen finden Sie in den Referenzarchitekturen in [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Allgemeine Protokollverwendung für UDP und TCP im Audio/Video-und Mediendatenverkehr

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Audio/Video-Transport</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Bevorzugtes Transportschichtprotokoll für Audio und Video</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Fall Back Transport-Layer-Protokoll für Audio und Video</p>
<p>Erforderliches Transportschichtprotokoll für die Anwendungsfreigabe für Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013</p>
<p>Erforderliches Transportschichtprotokoll für die Dateiübertragung an lync Server 2010 und lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Externe A/V-Firewall-Port Anforderungen für den Zugriff durch externe Benutzer

Die Firewall-Portanforderungen für externe (und interne) SIP-und Konferenz Schnittstellen sind unabhängig von der Version des Clients oder der Version des Verbundpartners konsistent.

Dies gilt nicht für die externe Schnittstelle Audio/Video Edge. Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass externe Firewallregeln den RTP/TCP-und RTP/UDP-Datenverkehr im 50.000 bis 59.999-Portbereich in beide Richtungen fließen lassen. In der vorhergehenden Tabelle wird davon ausgegangen, dass lync Server 2013 der primäre Föderationspartner ist und für die Kommunikation mit einem der anderen Föderationspartner Typen konfiguriert ist, die aufgelistet werden.

Bei der Konfiguration des Audio/Video-Portbereichs von 50000-59.999 muss berücksichtigt werden, dass der Portbereich die Quell Anschlüsse für die Kommunikation mit Verbundpartnern enthält. Bedenken Sie im Detail, dass eine Kommunikation von einem Föderationspartner initiiert wird. Die Kommunikation der a/v-Edgedienst-Ports im Bereich 50000-59.999 stellt eine Verbindung mit dem erwarteten Port TCP 443 des a/v-Edgedienst des Partners her. Umgekehrt hat der eingehende Datenverkehr zu Ihrem A/V Edge Service Port TCP 443 einen Quell Port im Bereich von 50000-59.999.

Bei unterschiedlichen Firewalls und Richtlinien für die Firewall-Verwaltung müssen möglicherweise nur Zielregeln konfiguriert werden, oder es ist möglich, dass Quelle und Ziel konfiguriert werden müssen. Wenn Ihre Anforderungen nur für Zielanschlüsse gelten, gelten die Anforderungen für Audio/Video:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Quell-IP</th>
<th>Ziel-IP</th>
<th>Zielport</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Wenn für Ihre Richtlinien sowohl eingehende als auch ausgehende Firewall-Regeldefinitionen erforderlich sind, gelten die Anforderungen für Audio/Video:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Quell-IP</th>
<th>Ziel-IP</th>
<th>Quellport</th>
<th>Zielport</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 50.000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 erfordert eine etwas andere Konfiguration. Der TCP-und UDP-Portbereich von 50000-59.999 muss ein-und ausgehendes öffnen sein. Diese Anforderung gilt nur für Office Communicator 2007. Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 erfordern nur den TCP-Bereich 50000-59.999 Open Outbound.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>NAT-Anforderungen für den Edgedienst

Die folgenden NAT-Anforderungen gelten, wenn Sie sich entscheiden, nicht routingfähige private IP-Adressen für den Edgedienst zu konfigurieren:

  - NAT kann nur mit dem DNS-Lastenausgleich verwendet werden. NAT wird von einer Edge-Topologie (Hardware Load Balancing) nicht unterstützt.

  - NAT kann nur auf der Schnittstelle des externen Edge verwendet werden. NAT wird auf der Schnittstelle für den internen Edge nicht unterstützt.

  - NAT muss für eingehenden und ausgehenden Datenverkehr symmetrisch sein.
    
  - Für Datenverkehr aus dem Internet muss NAT die Ziel-IP-Adresse von der NAT-aktivierten öffentlichen IP-Adresse des A/V-Edge-Diensts in die externe IP-Adresse ändern. Die Quell-IP-Adresse muss intakt bleiben, damit der A/V-Edgedienst den optimalen Medienpfad finden kann.
  
  In der folgenden Abbildung wird beispielsweise in der eingehenden Richtung die öffentliche IP-Adresse 131.107.155.30 in die externe IP-Adresse 10.45.16.10 (privat) geändert. Die Quell-IP-Adresse blieb unverändert.
  
  - Für Datenverkehr vom a/v-Edgedienst zum Internet muss NAT die Quell-IP-Adresse von der externen IP-Adresse des a/v-Edgedienst in die NAT-fähige öffentliche IP-Adresse ändern.

In der folgenden Abbildung wird beispielsweise die externe (private) IP-Adresse 10.45.16.10 in die öffentliche IP-Adresse 131.107.155.30 geändert.

**Die folgende Abbildung zeigt, wie NAT die Ziel-IP-Adresse für eingehenden Datenverkehr und die Quell-IP-Adresse für ausgehenden Datenverkehr ändert.**

![Ändern von Ziel-/Quell-IP-Adressen] (images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern von Ziel-/Quell-IP-Adressen")

Die wichtigsten Punkte sind:

  - Datenverkehr, der sich auf dem Server mit dem A/V-Edgedienst befindet, ändert sich die Quell-IP-Adresse nicht, aber die Ziel-IP-Adresse wird von 131.107.155.30 in die übersetzte IP-Adresse von 10.45.16.10 geändert.

  - Datenverkehr von dem Server, auf dem der a/v-Edgedienst zurück zur Workstation läuft, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers zur öffentlichen IP-Adresse des Servers, auf dem der a/v-Edgedienst ausgeführt wird. Die Ziel-IP-Adresse bleibt die öffentliche IP-Adresse der Workstation. Nachdem das Paket das erste NAT-Gerät ausgehoben hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem die externe Schnittstellen-IP-Adresse (10.45.16.10) des Edge-Diensts ausgeführt wird, in die öffentliche IP-Adresse (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

