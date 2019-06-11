---
title: 'Lync Server 2013: DNS-Anforderungen für Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>DNS-Anforderungen für Front-End-Pools in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-07_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die für die Bereitstellung von Front-End-Pools erforderlich sind.

<div>

## <a name="dns-records-for-front-end-pools"></a>DNS-Einträge für Front-End-Pools

In der folgenden Tabelle sind die DNS-Anforderungen für eine lync Server 2013-Front-End-Pool Bereitstellung angegeben.

### <a name="dns-requirements-for-a-front-end-pool"></a>DNS-Anforderungen für einen Front-End-Pool

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bereitstellungsszenario</th>
<th>DNS-Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Pool mit mehreren Front-End-Servern und einem Hardware-Lastenausgleichsmodul (unabhängig davon, ob der DNS-Lastenausgleich auch in diesem Pool bereitgestellt wird)</p></td>
<td><p>Bei Verwendung des DNS-Lastenausgleichs und eines Hardware Lastenausgleichs müssen Sie (a)-Datensätze hosten. Erstellen Sie einen internen A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools für den DNS-Lastenausgleich behebt. Erstellen Sie einen internen Host (A)-Eintrag für die internen Webdienste an die virtuelle IP-Adresse (VIP) des Load Balancer. Sie müssen den internen Webdienste-Namen verwenden, wie in Topology Builder definiert.</p>
<p>Wenn Sie beispielsweise sowohl den DNS-Lastenausgleich als auch den Hardwarelastenausgleich verwenden, verfügen Sie über einen a-Eintrag für jeden Front-End-Server in einem Pool für den DNS-Lastenausgleich und einen a-Eintrag für die internen Webdienste, die auf die virtuelle IP des Hardwarelastenausgleichs verweisen. :</p>
<ul>
<li><p>DNS-Lastenausgleich: Pool01.contoso.NET IP-Adresse des Pool-10.10.10.5</p>
<div>

> [!WARNING]  
> Für jeden Front-End-Server gibt es auch einen eindeutigen a-Eintrag:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Hardware Lastenausgleich: WebInternal.contoso.NET IP address of HLB VIP 192.168.10.5</p></li>
</ul>
<p>Für den gesamten Datenverkehr mit Ausnahme des HTTP/HTTPS-Datenverkehrs wird der Pool01.contoso.net-Eintrag verwendet. Der HTTP/HTTPS-Datenverkehr verwendet die definierte interne Webdienste-Adresse von 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit Bereitstellung des DNS-Lastenausgleichs</p></td>
<td><p>Eine Gruppe interner a-Datensätze, die den FQDN des Pools in die IP-Adresse jedes Servers im Pool auflösen. Für jeden Server im Pool muss ein Eintrag vorhanden sein.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Pool mit Bereitstellung des DNS-Lastenausgleichs</p></td>
<td><p>Eine Gruppe interner a-Datensätze, die den FQDN jedes Servers im Pool in die IP-Adresse dieses Servers auflösen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleich in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit einem einzelnen Front-End-Server und einer dedizierten Back-End-Datenbank, aber ohne Lastenausgleichsmodul</p></td>
<td><p>Ein interner A-Eintrag, der den FQDN des Front-End-Pools in die IP-Adresse des Single Enterprise Edition-Front-End-Servers auflöst.</p></td>
</tr>
<tr class="odd">
<td><p>Automatische Clientanmeldung</p></td>
<td><p>Für jede unterstützte SIP-Domäne einen SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Front-End-Pools zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Device Update-Webdienst Ermittlung durch Unified Communications (UC)-Geräte</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Front-End-Pools aufgelöst wird, der den Geräte Update-Webdienst hostet. In der Situation, in der ein UC-Gerät aktiviert ist, sich ein Benutzer aber noch nie beim Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät das Erkennen des Front-End-Pools, auf dem der Geräte Update-Webdienst gehostet wird, und das Abrufen von Updates. Andernfalls erhalten Geräte diese Informationen zwar in-Band-Bereitstellung, wenn sich der Benutzer zum ersten Mal anmeldet.</p>
<div>

> [!IMPORTANT]  
> Wenn Sie über eine vorhandene Bereitstellung des Geräte Update-Webdiensts in lync Server 2010 verfügen, haben Sie bereits einen internen A-Eintrag mit dem Namen ucupdates erstellt. &lt;SIP-&gt;Domäne. Für Microsoft Office Communications Server 2007 R2 müssen Sie einen zusätzlichen DNS-A-Eintrag mit dem Namen ucupdates-R2 erstellen. &lt;SIP-&gt;Domäne.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Reverse-Proxy zur Unterstützung des HTTP-Datenverkehrs</p></td>
<td><p>Ein externer A-Eintrag, der den FQDN der externen Webfarm in die externe IP-Adresse des Reverse-Proxys auflöst. Clients und UC-Geräte verwenden diesen Eintrag, um eine Verbindung mit dem Reverse-Proxy herzustellen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle zeigt ein Beispiel für die DNS-Einträge, die für den FQDN der internen Webfarm erforderlich sind.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Beispiel-DNS-Einträge für den FQDN der internen Webfarm

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interner FQDN der Webfarm</th>
<th>Pool-FQDN</th>
<th>DNS-A-Eintrag (e)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>EE-Pool.contoso.com</p></td>
<td><p>DNS einen Eintrag für den EE-Pool.contoso.com, der in die VIP-Adresse des Load Balancer der Front-End-Server aufgelöst wird.</p>
<p>DNS-A-Eintrag für webcon.contoso.com, der in die VIP-Adresse des Load Balancer der Front-End-Server aufgelöst wird.</p></td>
</tr>
<tr class="even">
<td><p>EE-Pool.contoso.com</p></td>
<td><p>EE-Pool.contoso.com</p></td>
<td><p>DNS-A-Eintrag für EE-Pool.contoso.com, der in die virtuelle IP-Adresse (VIP) des Load Balancer aufgelöst wird, der von den Front-End-Servern der Enterprise Edition im Front-End-Pool verwendet wird.</p>
<p>Beachten Sie, dass bei Verwendung des DNS-Lastenausgleichs in diesem Pool der Front-End-Pool und die interne Webfarm nicht den gleichen FQDN aufweisen können.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

