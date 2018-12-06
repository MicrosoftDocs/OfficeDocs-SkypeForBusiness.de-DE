---
title: 'Lync Server 2013: Anforderungen an das Hardwaregerät zum Lastenausgleich'
TOCTitle: Anforderungen an das Hardwaregerät zum Lastenausgleich
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49890695
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die skalierte konsolidierte Edgetopologie von Lync Server 2013 ist für den DNS-Lastenausgleich optimiert und für neue Bereitstellungen geeignet, die hauptsächlich einen Partnerverbund mit Organisationen eingehen, die Lync Server verwenden. Wenn für eines der folgenden Szenarien hohe Verfügbarkeit erforderlich ist, muss ein Hardwaregerät zum Lastenausgleich für die EdgeserverPools verwendet werden:

  - Partnerverbund mit Organisationen, in denen Office Communications Server 2007 R2 oder Office Communications Server 2007 ausgeführt wird

  - Exchange UM für Remotebenutzer, die Exchange UM vor Exchange 2010 mit SP1 verwenden

  - Verbindung mit Benutzern öffentlicher Chatdienste


> [!IMPORTANT]
> Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.




> [!NOTE]
> Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden.




> [!NOTE]
> Die Netzwerkadressenübersetzung (NAT) mit Direct Server Return (DSR) wird für Lync Server 2013 nicht unterstützt.



Informationen dazu, ob Ihr Hardwaregerät zum Lastenausgleich die von Lync Server 2013 benötigten Features unterstützt, finden Sie auf der Seite " Lync Server 2010 Load Balancer Partners" unter [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).

## Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver aufgelistet, auf denen der A/V-Edgedienst ausgeführt wird:

  - Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.

  - Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50.000 bis 59.999.

  - Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall.

  - Die interne Edgeschnittstelle muss sich in einem anderen Netzwerk befinden als die externe Edgeserver-Schnittstelle, und das Routing zwischen diesen Schnittstellen muss deaktiviert sein.

  - Die externe Schnittstelle des Edgeservers, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und darf keine Netzwerkadressen- oder Portübersetzung für die externen IP-Adressen des Edgeservers verwenden.

## Anforderungen an das Hardwaregerät zum Lastenausgleich

Die Anforderungen in Bezug auf die cookiebasierte Affinität sind in Lync Server 2013 für Webdienste erheblich reduziert worden. Wenn Sie Lync Server 2013 bereitstellen und keine Lync Server 2010- Front-End-Server oder - Front-End-Pools beibehalten, benötigen Sie keine cookiebasierte Persistenz. Wenn Sie jedoch irgendwelche Lync Server 2010- Front-End-Server oder - Front-End-Pools vorübergehend oder dauerhaft beibehalten möchten, müssen Sie weiterhin die cookiebasierte Persistenz verwenden, so wie sie für Lync Server 2010 bereitgestellt und konfiguriert ist.


> [!NOTE]
> <STRONG>Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre</STRONG>-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung.



Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:

  - Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf **True** fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.

Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:

  - Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf **True** fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als "httpOnly" gekennzeichnet sein.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).

  - Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.


> [!NOTE]
> In typischen Konfigurationen für das Hardwaregerät zum Lastenausgleich wird die Quelladressenaffinität und eine TCP-Sitzungsdauer von 20&nbsp;Minuten verwendet. Diese Konfiguration ist für Lync Server- und Lync 2013-Clients in Ordnung, da der Sitzungsstatus über die Clientverwendung und /oder Anwendungsinteraktion beibehalten wird.



Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).


> [!WARNING]
> F5-Hardwaregeräte zum Lastenausgleich sind mit einem Feature namens OneConnect ausgestattet, mit dem sichergestellt wird, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt). Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit.<BR>Detaillierte Informationen zu Drittanbieter-Hardwaregeräten zum Lastenausgleich finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>.



Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:

  - Legen Sie für interne virtuelle IP-Adressen der Webdienste die Dauerhaftigkeit von Quelladressen (interner Port 80, 443) für das Hardwaregerät zum Lastenausgleich fest. Für Lync Server 2013 bedeutet Dauerhaftigkeit von Quelladressen, dass mehrere Verbindungen von einer einzelnen IP-Adresse zur Beibehaltung des Sitzungsstatus stets an einen einzigen Server gesendet werden.

  - Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.

  - Erstellen Sie für die Firewall zwischen dem Reverseproxy und dem Hardwaregerät zum Lastenausgleich des nächsten Hoppools eine Regel zum Zulassen von https:-Datenverkehr an Port 4443 - vom Reverseproxy zum Hardwaregerät zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.

## Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Client-/Benutzerstandort</th>
<th>Affinitätsanforderungen an den externen Webdienste-FQDN</th>
<th>Affinitätsanforderungen an den internen Webdienste-FQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (interne und externe Benutzer)</p>
<p>Mobiles Gerät (interne und externe Benutzer)</p></td>
<td><p>Keine Affinität</p></td>
<td><p>Quelladressenaffinität</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (nur externe Benutzer)</p>
<p>Mobiles Gerät (interne und externe Benutzer)</p></td>
<td><p>Keine Affinität</p></td>
<td><p>Quelladressenaffinität</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (nur interne Benutzer)</p>
<p>Mobiles Gerät (nicht bereitgestellt)</p></td>
<td><p>Keine Affinität</p></td>
<td><p>Quelladressenaffinität</p></td>
</tr>
</tbody>
</table>


## Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Server-Dienst (RTCSRV) beendet wird, da der Front-End-Server oder Front-End-Pool ausgefallen ist, sollte auch die HLB-Überwachung keinen Datenverkehr mehr über den Webdienste empfangen. Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:

### Front-End-Server-Benutzerpool - Interne HLB-Schnittstelle

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Virtuelle IP/Port</th>
<th>Knoten Port</th>
<th>Knoten Computer/Monitor</th>
<th>Persistenzprofil</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-End</p>
<p>5061</p></td>
<td><p>Quelle</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-End</p>
<p>5061</p></td>
<td><p>Quelle</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### Front-End-Server-Benutzerpool - Externe HLB-Schnittstelle

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Virtuelle IP/Port</th>
<th>Knoten Port</th>
<th>Knoten Computer/Monitor</th>
<th>Persistenzprofil</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-End</p>
<p>5061</p></td>
<td><p>-</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-End</p>
<p>5061</p></td>
<td><p>-</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>

