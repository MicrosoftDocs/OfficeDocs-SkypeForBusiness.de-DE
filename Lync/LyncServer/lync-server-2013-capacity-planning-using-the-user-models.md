---
title: Lync Server 2013-Kapazitätsplanung mit den Benutzermodellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Kapazitätsplanung für lync Server 2013 mit den Benutzermodellen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-14_

Dieser Abschnitt enthält Anleitungen dazu, wie viele Server Sie auf einer Website benötigen, um die Anzahl der Benutzer auf dieser Website entsprechend der in den [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)beschriebenen Verwendung zu verwenden.

<div>

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Alle Leistungsergebnisse und Bereitstellungsempfehlungen in diesem Abschnitt basieren auf Leistungstests auf Servern, auf denen die in der folgenden Tabelle beschriebene Hardware ausgeführt wird. Wir empfehlen, ähnliche Hardware zu verwenden. Wenn Sie weniger leistungsfähige Hardware verwenden, treten möglicherweise Funktionsprobleme oder eine schlechte Leistung auf. Beachten Sie, dass diese Hardwareempfehlungen höher als in früheren Versionen von lync Server sind.

### <a name="hardware-used-in-performance-testing"></a>Bei Leistungstests eingesetzte Hardware

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Empfohlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz</p>
<p>Intel Itanium-Prozessoren werden für lync Server-Serverrollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 GB</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><ul>
<li><p>8 oder mehr Festplatten mit 10.000 U/Min mit mindestens 72 GB freiem Speicher.</p>
<p>Zwei Festplatten sollten RAID 1 verwenden und sechs Festplatten sollten RAID 10 verwenden.</p>
<p>-Oder</p></li>
<li><p>Festkörperlaufwerke (SSDs) mit einer ähnlichen Leistung wie 8 mechanische Festplattenlaufwerke mit 10.000 U/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür die Verknüpfung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

In der folgenden Tabelle werden diese Empfehlungen zusammengefasst.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Serverrolle</th>
<th>Maximale Anzahl von unterstützten Benutzern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Paar von Back-End-Servern.</p></td>
<td><p>80.000 eindeutige Benutzer, plus 50 % Anmeldungen auf mehreren Geräten (Multiple Point Of Presence, MPOP), die keine mobilen Instanzen sind, plus 40 % Benutzer, die für Mobilität aktiviert sind, für insgesamt 152.000 Endpunkte.</p></td>
</tr>
<tr class="even">
<td><p>A/V-Konferenzen</p></td>
<td><p>Der a/V-Konferenzdienst, der von einem Front-End-Pool bereitgestellt wird, unterstützt die Konferenzen des Pools, vorausgesetzt, es wird eine maximale Konferenzgröße von 250-Benutzern und nur eine solche große Konferenz gleichzeitig ausgeführt.</p>
<div>

> [!NOTE]  
> Darüber hinaus können Sie große Konferenzen zwischen 250-und 1000-Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, um die umfangreichen Konferenzen zu hosten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-supporting-large-meetings.md">unterstützen von umfangreichen Besprechungen mit lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Edgeserver</p></td>
<td><p>12.000 Concurrent Remote-Benutzer</p></td>
</tr>
<tr class="even">
<td><p>Ein Direktor</p></td>
<td><p>12.000 Concurrent Remote-Benutzer</p></td>
</tr>
<tr class="odd">
<td><p>Überwachen und Archivieren</p></td>
<td><p>In lync Server 2013 werden die Front-End-Dienste für die Überwachung und Archivierung nun auf jedem Front-End-Server und nicht auf separaten Server Rollen ausgeführt.</p>
<p>Für das Überwachen und Archivieren sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 ausführen, können Sie Ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL-Datenbank speichern.</p></td>
</tr>
<tr class="even">
<td><p>Ein Vermittlungs Server</p></td>
<td><p>Der mit dem Front-End-Server zusammenhängende Vermittlungsserver wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen. Informationen zum eigenständigen Vermittlungsserver finden Sie im Abschnitt "Mediation Server" weiter unten in diesem Thema.</p></td>
</tr>
<tr class="odd">
<td><p>Ein Standard Edition-Server</p></td>
<td><p>Wir empfehlen dringend, dass Sie bei der Verwendung von Standard Edition-Servern zum Hosten von Benutzern immer zwei Server verwenden, die mit den Empfehlungen <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">für die Planung von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013</a>kombiniert werden. Jeder Server der Kombination kann bis zu 2.500 Benutzer hosten und wenn ein Server ausfällt, kann der verbleibende Server in einem Failoverszenario 5.000 Benutzer unterstützen.</p>
<p>Wenn in Ihrer Bereitstellung Audio- oder Videodatenverkehr im großen Umfang anfällt, wird die Serverleistung u. U. auch bei mehr als 2.500 Benutzern pro Server beeinträchtigt. In diesem Fall sollten Sie das Hinzufügen weiterer Standard Edition-Server oder die Umstellung auf lync Server Enterprise Edition in Frage stellen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Front-End-Server

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

In einem Front-End-Pool sollten Sie über einen Front-End-Server für alle 6.660-Benutzer verfügen, die im Pool verwaltet werden, vorausgesetzt, dass Hyper-Threading auf allen Servern im Pool aktiviert ist und dass die Server Hardware die Empfehlungen in [Server Hardwareplattformen für lync erfüllt. Server 2013](lync-server-2013-server-hardware-platforms.md). Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000, vorausgesetzt, Hyper-Threading ist auf allen Servern im Pool aktiviert. Wenn Sie über mehr als 80.000 Benutzer an einer Website verfügen, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie die Benutzer, die sich auf überlebensfähigen Zweig-Appliances und überlebensfähigen Verzweigungs Servern befinden, in Zweigniederlassungen ein, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. Wenn Sie beispielsweise 30.000-Benutzer und fünf Front-End-Server haben, müssen die Verbindungen von 6000-Benutzern auf die anderen vier Server übertragen werden, wenn ein Server nicht verfügbar ist. Die restlichen vier Server verfügen jeweils über 7500-Benutzer, was eine größere Zahl als empfohlen ist.

Wenn Sie stattdessen mit sechs Front-End-Servern für ihre 30.000-Benutzer begonnen haben und diese dann nicht mehr zur Verfügung stehen, werden insgesamt 5000-Benutzer auf die restlichen fünf Server verschoben. Diese fünf Server sind für jeden Host 6000-Benutzer, der sich im empfohlenen Bereich befindet.

Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000. Die maximale Anzahl der Front-End-Server in einem Pool beträgt 12.

Bei einem Front-End-Pool mit 80.000-Benutzern genügen zwölf Front-End-Server für die Leistung in typischen Bereitstellungen, die den [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)entsprechen. Für Bereitstellungen zur Unterstützung von Disaster Recovery-Failover wird davon ausgegangen, dass maximal 40.000-Benutzer in jedem von zwei gekoppelten Front-End-Pools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools aufnehmen zu können, wenn ein Pool fehlerhaft sein muss. auf den anderen.

Die Anzahl der Benutzer, die mit einer guten Leistung von einem bestimmten Front-End-Pool unterstützt werden, kann aus folgenden Gründen von diesen Zahlen abweichen:

  - Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - Die Nutzung Ihrer Organisation weicht erheblich von den Benutzermodellen ab, wie etwa erheblich mehr Konferenzdatenverkehr.

<div>


> [!IMPORTANT]  
> In lync Server 2013 werden die Anwesenheits Datenbanken nun auf Front-End-Servern gehostet, anders als in lync Server 2010, auf dem Sie auf dem Back-End-Server gehostet wurden. Das bedeutet, dass die Datenträgerleistung und-Kapazität Ihrer Front-End-Server nicht von den weiter oben in diesem Abschnitt und auf <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>aufgeführten Empfehlungen beeinträchtigt werden sollten, unabhängig von der Anzahl der Benutzer, die von Ihre Front-End-Server.



</div>

In der folgenden Tabelle ist die durchschnittliche Bandbreite für Chat und Anwesenheitsinformationen anhand des Benutzermodells dargestellt, wie es in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)definiert ist.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Durchschnittliche Bandbreite pro Benutzer</th>
<th>Bandbreitenanforderungen pro Front-End-Server mit 6.660-Benutzern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 KBit/s</p></td>
<td><p>13 MBit/s</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Wenn Sie die Medien Leistung der co-located A/V-Konferenz-und Vermittlungs Server Funktionalität auf Ihren Front-End-Servern verbessern möchten, sollten Sie auf den Netzwerkadaptern auf Ihren Front-End-Servern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>in Windows Server 2008". Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Angesichts des Benutzermodells, dass sich 5% der Benutzer in einem Pool zu einem beliebigen Zeitpunkt in einer Konferenz befinden können, kann ein Pool von 80.000-Benutzern gleichzeitig über 4.000-Benutzer in Konferenzen verfügen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z. B. nur Chatnachrichten, Chatnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl der zulässigen Konferenzen, und die tatsächliche Nutzung bestimmt die tatsächliche Leistung. Wenn Ihre Organisation beispielsweise über viele weitere Konferenzen im gemischten Modus verfügt, als im Benutzermodell angenommen wird, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen als die Empfehlungen in diesem Dokument. Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in lync Server 2013](lync-server-2013-user-models.md).

Die maximale unterstützte Konferenzgröße, die von einem regulären lync Server 2013-Front-End-Pool gehostet wird, der auch Benutzer hostet, ist 250 Teilnehmer. Während eine 250-Benutzer Konferenz stattfindet, unterstützt der Pool weiterhin auch andere Konferenzen, sodass sich insgesamt 5% der Pool Benutzer in parallelen Konferenzen befinden. Beispielsweise unterstützt lync Server in einem Pool von zwölf Front-End-Servern und 80.000-Benutzern, während die 250-Benutzer Konferenz stattfindet, 3.750 anderen Benutzern, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die sich auf dem Front-End-Pool oder dem Standard Edition-Server befinden, unterstützt lync Server mindestens 125 anderen Benutzern, die an kleineren Konferenzen am gleichen Pool oder Server teilnehmen, der eine Konferenz mit 250-Benutzern hostet.

Zum Aktivieren von Konferenzen mit zwischen 250-und 1000-Benutzern können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen zu hosten. In diesem Front-End-Pool werden keine Benutzer gehostet. Ausführliche Informationen finden Sie unter [unterstützen von umfangreichen Besprechungen mit lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Wenn in Ihrer Organisation viele weitere Konferenzen im gemischten Modus stattfinden, die im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server als die Empfehlungen in diesem Dokument bereitstellen (bis zu einem Grenzwert von 12 Fes). Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Edgeserver

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Sie sollten einen Edgeserver für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen. Wir empfehlen mindestens zwei Edge-Server für eine höhere Verfügbarkeit. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.

Wenn Sie die Anzahl der Benutzer für die Edgeserver berücksichtigen, schließen Sie die Benutzer, die sich auf Survivable Branch Appliances und überlebensfähige Verzweigungs Server befinden, in Zweigniederlassungen ein, die einem Front-End-Pool an diesem Standort zugeordnet sind.

<div>


> [!NOTE]  
> Wenn Sie die Leistung des A/V-Konferenz-Edgedienst auf Ihren Edge-Servern verbessern möchten, sollten Sie auf den Netzwerkadaptern auf Ihren Edge-Servern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>in Windows Server 2008". Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Wenn Sie die Director-Serverrolle bereitstellen, empfehlen wir, dass Sie einen Director für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen. Wir empfehlen mindestens zwei Directors für höchste Verfügbarkeit. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.

Wenn Sie die Anzahl der Benutzer für die Directors berücksichtigen, fügen Sie die Benutzer, die sich auf Survival Branch-Appliances und überlebensfähige Branch-Server befinden, in Zweigniederlassungen ein, die einem Front-End-Pool an diesem Standort zugeordnet sind.

</div>

<div>

## <a name="mediation-server"></a>Vermittlungsserver

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Wenn Sie den Vermittlungsserver mit dem Front-End-Server collocate, wird der Mediation Server auf jedem Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen vermittlungsserverpool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der VoIP-Benutzer, der Anzahl der Gateway-Peers, die für jeden vermittlungsserverpool verwendet werden. Steuerelemente, der auslastungsstunden Verkehr über diese Gateways und der Prozentsatz von Anrufen mit Medien, die den Vermittlungs Server umgehen.

Die folgenden Tabellen enthalten eine Richtlinie für die Anzahl von gleichzeitigen anrufen, die von einem Vermittlungsserver verarbeitet werden können, vorausgesetzt, die Hardware für die Vermittlungsserver erfüllt die Anforderungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) und Hyper-Threading ist aktiviert. Details zur Vermittlungsserver-Skalierbarkeit finden Sie unter [schätzen der Sprachverwendung und des Datenverkehrs für lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) und [Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Alle folgenden Tabellen gehen davon aus, dass die Verwendung in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)zusammengefasst ist.

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Eigenständige Vermittlungs Server Kapazität: 70% interne Benutzer, 30% externe Benutzer mit nicht-Bypass-Anrufkapazität (vom Vermittlungsserver durchgeführte Medienumwandlung)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Serverhardware</th>
<th>Maximale Anzahl von Anrufen</th>
<th>Maximale Anzahl von T1-Leitungen</th>
<th>Maximale Anzahl von E1-Leitungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dualprozessor, Vierkern, Hyperthreading-CPU mit 2,26 GHz  <strong>und deaktiviertem Hyperthreading </strong>, 32 GB Arbeitsspeicher und einem Dualport-Netzwerkadapter.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz, 32 GB Arbeitsspeicher und ein Dualport-Netzwerkadapter.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Obwohl Server mit 32 GB Arbeitsspeicher für Leistungstests verwendet wurden, werden Server mit 16 GB Arbeitsspeicher für eigenständigen Vermittlungs Server unterstützt und genügen, um die in dieser Tabelle gezeigte Leistung bereitzustellen.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Vermittlungsserver Kapazität (Mediationsserver mit Front-End-Server) 70% interne Benutzer, 30% externe Benutzer, nicht-Bypass-Anrufkapazität (Medienverarbeitung vom Vermittlungsserver ausgeführt)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Serverhardware</th>
<th>Maximale Anzahl von Anrufen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz und deaktiviertem Hyperthreading, 32 GB Arbeitsspeicher und zwei Netzwerkadapter mit 1 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Diese Zahl ist viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver, da der Front-End-Server andere Features und Funktionen für die 6600-Benutzer, die sich auf diesem Server befinden, sowie die für Sprachanrufe benötigte Transcodierung verarbeiten muss.



</div>

<div>


> [!NOTE]  
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie auf den Netzwerkadaptern auf Ihren Vermittlungsservern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>in Windows Server 2008". Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="back-end-server"></a>Back-End-Server

In lync Server 2013 befinden sich die Anwesenheits Datenbanken auf den Front-End-Servern statt auf dem Back-End-Server. Dies hat zu einer wesentlich einfacheren Anforderung für jeden Back-End-Server in lync Server 2013 geführt, der der Hardwareanforderung für den Front-End-Server entspricht. Vergleichen Sie dies mit lync Server 2010, bei dem der Back-End-Server ein viel höherwertiger Server mit 25 Datenträgern sein muss. Die Arbeitsauslastung von Back-End-Servern ist jedoch weiterhin so, dass Sie die Hardwareempfehlungen, die weiter oben in diesem Abschnitt und auf [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)aufgeführt sind, nicht versäumen sollten.

Zur Bereitstellung einer großen Verfügbarkeit Ihres Back-End-Servers empfehlen wir die Bereitstellung der Server Spiegelung. Weitere Informationen finden Sie unter [Back-End-Server-Höchstverfügbarkeit in lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie in lync Server 2013 die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern statt auf separaten Server Rollen ausgeführt. Für die Überwachung und Archivierung wird jeweils weiterhin ein eigener Datenbankspeicher separat vom Back-End-Speicher verwendet. Wenn Sie jedoch Exchange 2013 bereitgestellt haben, können Sie Sofortnachrichten-Archivierungsdaten in Exchange anstatt in einem dedizierten SQL Store speichern.

Die folgende Tabelle zeigt, wie viele Datenbankspeicher pro Benutzer und Tag für die Daten aus der Überwachung und Archivierung in etwa benötigt wird.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>KDS (Überwachung)</strong></p></td>
<td><p><strong>QoE (Überwachung)</strong></p></td>
<td><p><strong>Archiving</strong></p></td>
</tr>
<tr class="even">
<td><p>Pro Benutzer und Tag benötigter Festplattenspeicher</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft hat bei den Leistungstests für den Datenbankserver die in der folgenden Tabelle aufgeführte Hardware für die Überwachung und Archivierung eingesetzt. Die Tests sammelten die Daten von zwei Front-End-Pools, die jeweils 80.000-Benutzer enthielten.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Beim Leistungstest der Überwachung und Archivierung eingesetzte Hardware

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Empfohlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>48 GB</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><p>25 Festplatten mit 10.000 U/Min mit jeweils 300 GB und der folgenden Konfiguration</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Laufwerk</strong></p></td>
<td><p><strong>RAID-Konfiguration</strong></p></td>
<td><p><strong>Anzahl Festplatten</strong></p></td>
</tr>
<tr class="even">
<td><p>KDS-, QoE- und Archivdatenbankdateien auf einem einzigen Laufwerk</p></td>
<td><p>1+0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>KDS-Datenbankprotokolldatei</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>QoE-Datenbankprotokolldatei</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Archiv-Datenbankprotokolldatei</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür die Verknüpfung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

