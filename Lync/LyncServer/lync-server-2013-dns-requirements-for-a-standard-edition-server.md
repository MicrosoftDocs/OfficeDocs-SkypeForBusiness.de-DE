---
title: 'Lync Server 2013: DNS-Anforderungen für einen Standard Edition-Server'
TOCTitle: DNS-Anforderungen für einen Standard Edition-Server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204936(v=OCS.15)
ms:contentKeyID: 49294138
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für einen Standard Edition-Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Standard Edition-Servern erforderlich sind.

## DNS-Einträge für Standard Edition-Server

In der folgenden Tabelle sind die DNS-Anforderungen für die Bereitstellung von Lync Server 2013 Standard Edition-Servern angegeben.


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
<td><p>Standard Edition-Server</p></td>
<td><p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p></td>
</tr>
<tr class="even">
<td><p>Automatische Clientanmeldung</p></td>
<td><p>Für jede unterstützte SIP-Domäne ein SRV-Eintrag für &quot;_sipinternaltls._tcp.&lt;Domäne&gt;&quot; über Port 5061, der dem FQDN des Standard Edition-Servers zugeordnet ist, der Anforderungen zur Clientanmeldung authentifiziert und weiterleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen &quot;ucupdates-r2.&lt;SIP-Domäne&gt;&quot;, der in die IP-Adresse des Standard Edition-Servers aufgelöst wird, der den Geräteaktualisierungs-Webdienst hostet. Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Server sucht, auf dem der Geräteaktualisierungs-Webdienst gehostet wird, und Updates abruft. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet. Genauere Informationen finden Sie unter <a href="lync-server-2013-device-update-web-service.md">Geräteaktualisierungs-Webdienst in Lync Server 2013</a> in der Betriebsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p>Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</p></td>
<td><p>Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst. Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln von DNS-Anforderungen für Lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[DNS-Anforderungen für die automatische Clientanmeldung](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Weitere Ressourcen

[Geräteaktualisierungs-Webdienst in Lync Server 2013](lync-server-2013-device-update-web-service.md)

