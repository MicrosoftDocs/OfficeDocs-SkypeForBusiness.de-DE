---
title: DNS-Anforderungen für Front-End-Pools
TOCTitle: DNS-Anforderungen für Front-End-Pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412910(v=OCS.15)
ms:contentKeyID: 49295220
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für Front-End-Pools

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Front-End-Pools erforderlich sind.

## DNS-Einträge für Front-End-Pools

In der folgenden Tabelle werden die DNS-Anforderungen für die Bereitstellung eines Lync Server 2013-Front-End-Pools beschrieben.

### DNS-Anforderungen für einen Front-End-Pool

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
<td><p>Wenn sowohl ein DNS-Lastenausgleich als auch ein Hardwaregerät für den Lastenausgleich verwendet wird, benötigen Sie Host (A)-Einträge. Erstellen Sie einen internen A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Front-End-Pools für den DNS-Lastenausgleich aufgelöst wird. Erstellen Sie einen internen Host (A)-Eintrag für die internen Webdienste, der auf die virtuelle IP-Adresse (VIP) des Lastenausgleichs zeigt. Sie müssen den im Topologie-Generator definierten Namen der internen Webdienste verwenden.</p>
<p>Wenn Sie beispielsweise sowohl den DNS-Lastenausgleich als auch ein Hardwaregerät für den Lastenausgleich verwenden, haben Sie einen A-Eintrag für jeden Front-End-Server in einem Pool für den DNS-Lastenausgleich sowie einen A-Eintrag für die internen Webdienste, der auf die virtuelle IP des Hardwaregeräts für den Lastenausgleich zeigt:</p>
<ul>
<li><p>DNS-Lastenausgleich:   Pool01.contoso.net   IP-Adresse des Pools   10.10.10.5</p>
<div>

> [!WARNING]
> Jeder Front-End-Server verfügt auch über einen eindeutigen A-Eintrag:


</div>
<ol>
<li><p>FE01.contoso.net    10.10.10.1</p></li>
<li><p>FE02.contoso.net    10.10.10.2</p></li>
<li><p>FE03.contoso.net    10.10.10.3</p></li>
<li><p>FE04.contoso.net    10.10.10.4</p></li>
</ol></li>
<li><p>Hardwaregerät zum Lastenausgleich:   WebInternal.contoso.net   Virtuelle IP-Adresse (VIP) des Hardwaregeräts zum Lastenausgleich   192.168.10.5</p></li>
</ul>
<p>Für den gesamten Datenverkehr, außer für den HTTP/HTTPS-Datenverkehr, wird der Eintrag &quot;Pool01.contoso.net&quot; verwendet. Für den HTTP/HTTPS-Datenverkehr wird die definierte IP-Adresse der internen Webdienste verwendet: 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit DNS-Lastenausgleich</p></td>
<td><p>Ein Satz interner A-Einträge, die den Pool-FQDN in die IP-Adressen der einzelnen Server innerhalb des Pools auflösen. Für jeden Server im Pool muss mindestens ein A-Eintrag vorhanden sein.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Pool mit DNS-Lastenausgleich</p></td>
<td><p>Ein Satz interner A-Einträge, die den FQDN der einzelnen Server innerhalb des Pools in die IP-Adressen dieser Server auflösen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleich in Lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Pool mit einem einzelnen Front-End-Server und einer dedizierten Back-End-Datenbank, jedoch ohne Lastenausgleich</p></td>
<td><p>Ein interner A-Eintrag, der den FQDN des Front-End-Pools in die IP-Adresse des einzelnen Enterprise Edition-Front-End-Servers auflöst.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Automatische Clientanmeldung</p></td>
<td><p>Für jede unterstützte SIP-Domäne ein SRV-Eintrag für &quot;_sipinternaltls._tcp.&lt;Domäne&gt;&quot; über Port 5061, der dem FQDN des Front-End-Pools zugeordnet ist, der Anforderungen zur Clientanmeldung authentifiziert und weiterleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung</a>.</p></td>
</tr>
<tr class="even">
<td><p>Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen &quot;ucupdates-r2.&lt;SIP-Domäne&gt;&quot;, der in die IP-Adresse des Front-End-Pools aufgelöst wird, der den Geräteaktualisierungswebdienst hostet. Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Front-End-Pool sucht, auf dem der Geräteaktualisierungswebdienst gehostet wird, und Updates abruft. Andernfalls rufen Geräte diese Informationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</p>
<div>

> [!IMPORTANT]
> Wenn Sie über eine vorhandene Bereitstellung des Geräteaktualisierungswebdiensts in Lync Server 2010 verfügen, haben Sie bereits einen internen A-Eintrag mit dem Namen "ucupdates.<EM>&lt;SIP-Domäne&gt;</EM>" erstellt. Für Microsoft Office Communications Server 2007 R2 müssen Sie einen zusätzlichen DNS-A-Eintrag mit dem Namen "ucupdates-r2.<EM>&lt;SIP-Domäne&gt;</EM>" erstellen.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</p></td>
<td><p>Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst. Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln von DNS-Anforderungen für Lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle zeigt ein Beispiel für DNS-Einträge, die für den FQDN der internen Webfarm erforderlich sind.

### Beispiele für DNS-Einträge für den FQDN der internen Webfarm

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
<td><p>DNS-A-Eintrag für &quot;ee-pool.contoso.com&quot;, der in die VIP-Adresse des Systems zum Lastenausgleich aufgelöst wird, das von den Front-End-Servern verwendet wird.</p>
<p>DNS-A-Eintrag für &quot;webcon.contoso.com&quot;, der in die VIP-Adresse des Systems zum Lastenausgleich aufgelöst wird, das von den Front-End-Servern verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS-A-Eintrag für &quot;ee-pool.contoso.com&quot;, der in die virtuelle IP-Adresse (VIP) des Systems zum Lastenausgleich aufgelöst wird, das von den Enterprise Edition-Front-End-Servern im Front-End-Pool verwendet wird.</p>
<p>Hinweis: bei Verwendung des DNS-Lastenausgleichs für diesen Pool können Ihr Front-End-Pool und die interne Webfarm nicht denselben FQDN aufweisen.</p></td>
</tr>
</tbody>
</table>

