---
title: Lync Server 2013 Anforderungen an das Hardwaregerät zum Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4aac657dd1e472068474a3a70d17f1a2a38c63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530872"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Anforderungen an das Hardware Gerät zum Lastenausgleich für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-05-11_

Die lync Server 2013 skalierte konsolidierte Edge-Topologie ist für den DNS-Lastenausgleich für neue Bereitstellungen, die hauptsächlich mit anderen Organisationen mit lync Server zusammenfassen, optimiert. Wenn für eines der folgenden Szenarien hohe Verfügbarkeit erforderlich ist, muss ein Hardwaregerät zum Lastenausgleich in Edgeserver Pools für Folgendes verwendet werden:

  - Partnerverbund mit Organisationen, die Office Communications Server 2007 R2 oder Office Communications Server 2007 verwenden

  - Exchange um für Remotebenutzer, die Exchange um vor dem Exchange 2010 mit SP1 verwenden

  - Verbindung mit Benutzern öffentlicher Chatdienste

<div>


> [!IMPORTANT]  
> Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.



</div>

<div>


> [!NOTE]  
> Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden.



</div>

<div>


> [!NOTE]  
> Die DSR-NAT (Direct Server Return) wird von lync Server 2013 nicht unterstützt.



</div>

Informationen zum ermitteln, ob Ihr Hardwaregerät zum Lastenausgleich die für lync Server 2013 erforderlichen Features unterstützt, finden Sie unter "lync Server 2010 Lastenausgleichs Partner" unter [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Im folgenden finden Sie die Hardwareanforderungen für den Lastenausgleich für Edgeserver mit dem A/V-Edgedienst:

  - Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.

  - Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50.000 bis 59.999.

  - Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall.

  - Die interne Edge-Schnittstelle muss sich in einem anderen Netzwerk befinden als die Edgeserver externe Schnittstelle und das Routing zwischen diesen muss deaktiviert sein.

  - Die externe Schnittstelle des Edgeserver, auf dem der A/V-Edgedienst verwendet wird, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für eine externe IP-Adresse der Edge verwenden.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Die Anforderungen an die Cookie-basierte Affinität werden in lync Server 2013 für Webdienste stark reduziert. Wenn Sie lync Server 2013 bereitstellen und keine lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, benötigen Sie keine Cookie-basierte Persistenz. Wenn Sie jedoch lync Server 2010-Front-End-Server oder Front-End-Pools vorübergehend oder dauerhaft beibehalten, verwenden Sie weiterhin Cookie-basierte Persistenz, da Sie für lync Server 2010 bereitgestellt und konfiguriert wird.

<div>


> [!NOTE]  
> <STRONG>Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre </STRONG>-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung.



</div>

Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:

  - Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 4443 **Forward Hostheader** auf true fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.

Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:

  - Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 4443 **Forward Hostheader** auf true fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als "httpOnly" gekennzeichnet sein.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.

  - Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).

  - Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.

<div>


> [!NOTE]  
> Typische Hardware Lastenausgleichskonfigurationen verwenden die Quell Adress Affinität und eine 20-minütige TCP-Sitzungslebensdauer, was für lync Server-und lync 2013-Clients in Ordnung ist, da der Sitzungsstatus über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird.



</div>

Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).

<div>


> [!WARNING]  
> F5-Hardwaregeräte zum Lastenausgleich sind mit einem Feature namens OneConnect ausgestattet, mit dem sichergestellt wird, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt). Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit.<BR>Ausführliche Informationen zu Lastenausgleichsgeräten von Drittanbietern finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:

  - Für interne Webdienste VIPs legen Sie die Quell- \_ addr-Persistenz (interner Port 80, 443) auf dem Hardwaregerät zum Lastenausgleich fest. Für lync Server 2013 \_ bedeutet die Quell-addr-Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse stammen, immer an einen Server gesendet werden, um den Sitzungsstatus beizubehalten.

  - Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.

  - Erstellen Sie für die Firewall zwischen dem Reverseproxy und dem Hardwaregerät zum Lastenausgleich des nächsten Hoppools eine Regel zum Zulassen von https:-Datenverkehr an Port 4443 – vom Reverseproxy zum Hardwaregerät zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.

<div>


> [!IMPORTANT]  
> Weitere Informationen zur Konfiguration des Hardwaregerät zum Lastenausgleich finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich


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


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, da die Front-End-Server oder Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr auf dem Webdienste beenden. Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Front-End-Server Benutzer Pool – interne HLB-Schnittstelle

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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Pool &gt; -int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-End-</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;Pool &gt; -int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-End-</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Front-End-Server Benutzer Pool – externe HLB-Schnittstelle

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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Pool &gt; web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-End-</p>
<p>5061</p></td>
<td><p>Keine</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;Pool &gt; web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-End-</p>
<p>5061</p></td>
<td><p>Keine</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

