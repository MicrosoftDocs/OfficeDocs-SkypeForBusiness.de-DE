---
title: 'Lync Server 2013: Bestimmen der Anforderungen für externe A/V-Firewalls und Ports'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7b117f68719230151fd19050dbb080f6acde14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522582"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Kommunikation mit Audio/Video (a/V) kann komplex sein. Aufgrund der Art der in A/V verwendeten Protokolle und der Verwendung der Protokolle durch Clients und Server wird ein spezieller Abschnitt gerechtfertigt, um die Unterschiede zwischen Client-und Server Versionen zu erläutern.

Verwenden Sie die folgende A/V-Firewall und Port Tabelle, um die Firewall-Anforderungen zu ermitteln und welche Ports geöffnet werden sollen. Lesen Sie anschließend die Hinweise zur Netzwerkadressenübersetzung (Network Address Translation, NAT), da NAT auf viele verschiedene Arten implementiert werden kann. Ein ausführliches Beispiel für Firewall-Porteinstellungen finden Sie in den Referenzarchitekturen in [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Allgemeine Protokollnutzung für UDP und TCP im Audio/Video-und Mediendatenverkehr

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
<td><p>Fallback-Transportschichtprotokoll für Audio und Video</p>
<p>Erforderliches Transportschichtprotokoll für die Anwendungsfreigabe für Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013</p>
<p>Erforderliches Transportschichtprotokoll für die Dateiübertragung an lync Server 2010 und lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Portanforderungen für die externe A/V-Firewall für den externen Benutzerzugriff

Die Firewall-Portanforderungen für externe (und interne) SIP-und Konferenz Schnittstellen sind unabhängig von der Version des Clients oder der Version des Partnerverbund Partners konsistent.

Das gleiche gilt nicht für die externe Audio/Video-Edge-Schnittstelle. Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass externe Firewallregeln den RTP/TCP-und RTP/UDP-Datenverkehr im 50.000-bis 59.999-Portbereich in beide Richtungen fließen lassen. In der vorherigen Tabelle wird davon ausgegangen, dass lync Server 2013 der primäre Verbundpartner ist und für die Kommunikation mit einem der aufgeführten Partnerverbund Partnertypen konfiguriert ist.

Bei der Konfiguration des Audio/Video-Portbereichs von 50000-59.999 muss berücksichtigt werden, dass der Portbereich die Quell Ports für die Kommunikation mit Partnerverbund Partnern enthält. Im einzelnen ist zu prüfen, ob eine Kommunikation von einem Partnerverbund initiiert wird. Die Kommunikation von den A/V-Edgedienst Ports im 50000-59.999-Bereich stellt eine Verbindung mit dem erwarteten Port TCP 443 der A/V-Edgedienst des Partners her. Umgekehrt verfügt der eingehende Datenverkehr zu Ihrem A/V-Edgedienst Port TCP 443 über einen Quell Port im Bereich von 50000-59.999.

Für unterschiedliche Firewalls und Richtlinien für die Firewallverwaltung müssen möglicherweise nur die Zielregeln konfiguriert werden, oder es ist möglicherweise erforderlich, dass Quelle und Ziel konfiguriert werden. Wenn Ihre Anforderungen nur für Zielports gelten, sind die Anforderungen an Audio/Video:


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
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Wenn Ihre Richtlinien sowohl eingehende als auch ausgehende Firewall-Regeldefinitionen erfordern, sind die Anforderungen an Audio/Video:


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
<td><p>TCP 50000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 erfordert eine etwas andere Konfiguration. Der TCP-und UDP-Portbereich von 50000-59.999 muss Open eingehend und Outbound sein. Diese Anforderung gilt nur für Office Communicator 2007. Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 benötigen nur den TCP-Bereich 50000-59.999 Open Outbound.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>NAT-Anforderungen für den Edgedienst

Die folgenden NAT-Anforderungen gelten, wenn Sie nicht routingfähige private IP-Adressen für den Edgedienst konfigurieren:

  - NAT kann nur mit dem DNS-Lastenausgleich verwendet werden. NAT wird mit einer HLB-Edge-Topologie (Hardware Lastenausgleich) nicht unterstützt.

  - NAT kann nur für die externe Edge-Schnittstelle verwendet werden. NAT wird auf der internen Edge-Schnittstelle nicht unterstützt.

  - NAT muss für einen eingehenden und ausgehenden Datenverkehr symmetrisch sein.
    
  - Für Datenverkehr aus dem Internet muss NAT die Ziel-IP-Adresse von der NAT-fähigen öffentlichen IP-Adresse des A/V-Edgedienst in die externe IP-Adresse ändern. Die Quell-IP-Adresse muss intakt bleiben, damit der A/V-Edgedienst den optimalen Medienpfad finden kann.
  
  In der folgenden Abbildung wurde beispielsweise die öffentliche IP-Adresse 131.107.155.30 in die externe IP-Adresse 10.45.16.10 (privat) geändert. Die Quell-IP-Adresse blieb unverändert.
  
  - Für den Datenverkehr vom A/V-Edgedienst zum Internet muss NAT die Quell-IP-Adresse von der externen IP-Adresse des A/V-Edgedienst in die NAT-fähige öffentliche IP-Adresse ändern.

Beispiel: in der ausgehenden Richtung in der Abbildung unten wurde die externe IP-Adresse (privat) 10.45.16.10 in die öffentliche IP-Adresse 131.107.155.30 geändert.

**Die folgende Abbildung zeigt, wie NAT die Ziel-IP-Adresse für eingehenden Datenverkehr und die Quell-IP-Adresse für ausgehenden Datenverkehr ändert.**

![Ändern von Ziel-/Quell-IP-Adressen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern von Ziel-/Quell-IP-Adressen")

Die wichtigsten Punkte hierbei sind:

  - Datenverkehr, der auf dem Server mit dem A/V-Edgedienst eingehenden wird, ändert sich die Quell-IP-Adresse nicht, aber die IP-Zieladresse wird von 131.107.155.30 in die übersetzte IP-Adresse von 10.45.16.10 geändert.

  - Datenverkehr, der vom Server ausgeht, auf dem der A/V-Edgedienst zurück zur Arbeitsstation führt, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers zur öffentlichen IP-Adresse des Servers, auf dem der A/V-Edgedienst läuft. Die Ziel-IP bleibt die öffentliche IP-Adresse der Arbeitsstation. Nachdem das Paket das erste NAT-Gerät ausgehend verlassen hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem die A/V-Edgedienst-IP-Adresse der externen Schnittstelle (10.45.16.10) angegeben wird, in die öffentliche IP-Adresse (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

