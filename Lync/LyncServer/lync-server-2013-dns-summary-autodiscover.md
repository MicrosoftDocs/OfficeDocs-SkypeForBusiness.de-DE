---
title: DNS-Zusammenfassung – AutoErmittlung in Lync Server 2013
TOCTitle: DNS-Zusammenfassung – AutoErmittlung in Lync Server 2013
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945644(v=OCS.15)
ms:contentKeyID: 52056416
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung – AutoErmittlung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der AutoErmittlungsdienst ist flexibel, da der die Kommunikation über HTTP oder HTTPS akzeptiert. Hierzu müssen das Domain Name System (DNS) und die Zertifikate der Server, die den AutoErmittlungsdienst hosten, korrekt konfiguriert werden. Die Zertifikatanforderungen werden unter [Zertifikatübersicht – AutoErmittlung](lync-server-2013-certificate-summary-autodiscover.md) behandelt.


> [!IMPORTANT]
> Die DNS-Abfragelogik für die Lync Server-Clients verwendet eine bestimmte Auflösungsreihenfolge. Sie sollten immer sowohl den Eintrag "lyncdiscoverinternal.&lt;domain&gt;" als auch den Eintrag "lyncdiscover.&lt;domain&gt;" in Ihr DNS einfügen. Wenn Sie den Eintrag "lyncdiscoverinternal.&lt;domain&gt;" nicht einfügen, können interne Clients keine Verbindung mit den gewünschten Diensten herstellen oder erhalten die falsche Antwort vom AutoErmittlungsdienst.



### Interne DNS-Einträge

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.<em>&lt;interner domänenname&gt;</em></p></td>
<td><p>Interner Webdienste-FQDN für den Directorpool, falls vorhanden, oder für den Front-End-Pool , wenn kein Director vorhanden ist</p></td>
</tr>
<tr class="even">
<td><p>A (Host für IPv6 AAAA)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;interner domänenname&gt;</em></p></td>
<td><p>Interne Webdienste-IP-Adresse (virtuelle IP-Adresse bei Verwendung eines Lastenausgleichs) des Directorpools, sofern vorhanden, oder des Front-End-Pools, wenn kein Director vorhanden ist</p></td>
</tr>
</tbody>
</table>


Sie müssen einen der folgenden externen DNS-Einträge erstellen:

### Externe DNS-Einträge

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>Externer Webdienste-FQDN für den Directorpool, falls vorhanden, oder für den Front-End-Pool , wenn kein Director vorhanden ist</p></td>
</tr>
<tr class="even">
<td><p>A (Host für IPv6 AAAA)</p></td>
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>Externe oder öffentliche IP-Adresse des Reverseproxys</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Externer Datenverkehr wird über den Reverseproxy geleitet.




> [!NOTE]
> Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen. Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt. Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird. Für die nachfolgenden Anforderungen wird dann HTTPS verwendet. Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port&nbsp;80 (HTTP) konfigurieren. Ausführliche Informationen finden Sie im Abschnitt "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</A>. Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt. In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.



## Siehe auch

#### Aufgaben

[Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### Konzepte

[Zertifikatübersicht – AutoErmittlung](lync-server-2013-certificate-summary-autodiscover.md)

