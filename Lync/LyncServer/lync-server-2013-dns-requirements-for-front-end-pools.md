---
title: 'Lync Server 2013: DNS-Anforderungen für Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>DNS-Anforderungen für Front-End-Pools in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-07_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Front-End-Pools erforderlich sind.

<div>

## <a name="dns-records-for-front-end-pools"></a>DNS-Einträge für Front-End-Pools

In der folgenden Tabelle werden die DNS-Anforderungen für eine lync Server 2013 Front-End-Pool-Bereitstellung angegeben.

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
<td><p>Front-End-Pool mit mehreren Front-End-Servern und Hardwaregerät zum Lastenausgleich (dieses wird unabhängig davon bereitgestellt, ob für den Pool auch der DNS-Lastenausgleich implementiert wird)</p></td>
<td><p>Wenn Sie sowohl DNS-Lastenausgleich als auch ein Hardwaregerät zum Lastenausgleich verwenden, benötigen Sie Host (A)-Einträge. Erstellen Sie einen internen A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Front-End-Pools für den DNS-Lastenausgleich aufgelöst wird. Erstellen Sie einen internen Host (A)-Eintrag für die internen Webdienste zur VIP-Adresse (virtuelle IP) des Lastenausgleichs. Sie müssen den Namen der internen Webdienste gemäß Definition im Topologie-Generator verwenden.</p>
<p>Wenn Sie beispielsweise sowohl DNS-Lastenausgleich als auch Hardwarelastenausgleich verwenden, verfügen Sie über einen a-Eintrag für jeden Front-End-Server in einem Pool für den DNS-Lastenausgleich und einen a-Eintrag für die internen Webdienste, die auf die virtuelle IP des Hardware Lastenausgleichs verweist. :</p>
<ul>
<li><p>DNS-Lastenausgleich:   Pool01.contoso.net   IP-Adresse des Pools   10.10.10.5</p>
<div>

> [!WARNING]  
> Jeder Front-End-Server hat auch einen eindeutigen a-Eintrag:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Hardwaregerät zum Lastenausgleich:   WebInternal.contoso.net   IP-Adresse des Hardwaregeräts zum Lastenausgleich_VIP   192.168.10.5</p></li>
</ul>
<p>Sämtlicher Verkehr mit Ausnahme des HTTP/HTTPS-Datenverkehrs verwendet den Pool01.contoso.net-Eintrag. HTTP/HTTPS-Datenverkehr verwendet die definierte interne Webdiensteadresse 192.168.10.5.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit DNS-Lastenausgleich</p></td>
<td><p>Ein Satz interner A-Einträge, die den Pool-FQDN in die IP-Adressen der einzelnen Server innerhalb des Pools auflösen. Für jeden Server im Pool muss mindestens ein A-Eintrag vorhanden sein.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Pool mit DNS-Lastenausgleich</p></td>
<td><p>Ein Satz interner A-Einträge, die den FQDN der einzelnen Server innerhalb des Pools in die IP-Adressen dieser Server auflösen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleich in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit einem einzelnen Front-End-Server und einer dedizierten Back-End-Datenbank, jedoch ohne Lastenausgleich</p></td>
<td><p>Ein interner A-Eintrag, der den FQDN des Front-End-Pools in die IP-Adresse des einzelnen Enterprise Edition-Front-End-Servers auflöst.</p></td>
</tr>
<tr class="odd">
<td><p>Automatische Clientanmeldung</p></td>
<td><p>Für jede unterstützte SIP-Domäne ein SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Front-End-Pool zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse der Front-End-Pool aufgelöst wird, die den Geräte Update-Webdienst hostet. Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Front-End-Pool sucht, auf dem der Geräteaktualisierungswebdienst gehostet wird, und Updates abruft. Andernfalls rufen Geräte diese Informationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</p>
<div>

> [!IMPORTANT]  
> Wenn Sie eine vorhandene Bereitstellung des Geräte Update-Webdiensts in lync Server 2010 haben, haben Sie bereits einen internen A-Eintrag mit dem Namen ucupdates erstellt. &lt;SIP-&gt;Domäne. Für Microsoft Office Communications Server 2007 R2 müssen Sie einen zusätzlichen DNS-A-Eintrag mit dem Namen ucupdates-R2 erstellen. &lt;SIP-&gt;Domäne.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</p></td>
<td><p>Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst. Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle zeigt ein Beispiel für DNS-Einträge, die für den FQDN der internen Webfarm erforderlich sind.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Beispiele für DNS-Einträge für den FQDN der internen Webfarm

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN der internen Webfarm</th>
<th>Pool-FQDN</th>
<th>DNS-A-Einträge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS-A-Eintrag für "ee-pool.contoso.com", der in die VIP-Adresse des Systems zum Lastenausgleich aufgelöst wird, das von den Front-End-Servern verwendet wird.</p>
<p>DNS-A-Eintrag für "webcon.contoso.com", der in die VIP-Adresse des Systems zum Lastenausgleich aufgelöst wird, das von den Front-End-Servern verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS-A-Eintrag für "ee-pool.contoso.com", der in die virtuelle IP-Adresse (VIP) des Systems zum Lastenausgleich aufgelöst wird, das von den Enterprise Edition-Front-End-Servern im Front-End-Pool verwendet wird.</p>
<p>Hinweis: bei Verwendung des DNS-Lastenausgleichs für diesen Pool können Ihr Front-End-Pool und die interne Webfarm nicht denselben FQDN aufweisen.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

