---
title: DNS-Anforderungen für Standard Edition-Server
TOCTitle: DNS-Anforderungen für Standard Edition-Server
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425900(v=OCS.15)
ms:contentKeyID: 49293759
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für Standard Edition-Server

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Standard Edition-Servern erforderlich sind.

## DNS-Einträge für Standard Edition-Server

In der folgenden Tabelle werden die DNS-Anforderungen für eine Lync Server 2013 Standard Edition-Serverbereitstellung beschrieben.

### DNS-Anforderungen für einen Standard Edition-Server

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
<td><p>Für jede unterstützte SIP-Domäne ein SRV-Eintrag für &quot;_sipinternaltls._tcp.<em>&lt;Domäne&gt;</em>&quot; über Port 5061, der dem FQDN des Standard Edition-Servers zugeordnet ist, der Anforderungen zur Clientanmeldung authentifiziert und weiterleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen &quot;ucupdates-r2.<em>&lt;SIP domain&gt;</em>&quot;, der in die IP-Adresse des Standard Edition-Servers aufgelöst wird, der den Geräteaktualisierungswebdienst hostet. Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Server sucht, auf dem der Geräteaktualisierungs-Webdienst gehostet wird, und Updates abruft. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</p></td>
</tr>
<tr class="even">
<td><p>Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</p></td>
<td><p>Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst. Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln von DNS-Anforderungen für Lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>

