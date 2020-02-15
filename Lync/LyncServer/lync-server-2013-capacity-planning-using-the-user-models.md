---
title: Lync Server 2013 Kapazitätsplanung mithilfe der Benutzermodelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Kapazitätsplanung für lync Server 2013 mithilfe der Benutzermodelle

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-14_

Dieser Abschnitt enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)beschriebenen Verwendung.

<div>

## <a name="tested-hardware-platform"></a>Getestete Hardware Plattform

Alle Leistungsergebnisse und Bereitstellungsempfehlungen in diesem Abschnitt basieren auf Leistungstests auf Servern, die die in der folgenden Tabelle beschriebene Hardware ausführen. Es wird empfohlen, dass Sie ähnliche Hardware verwenden. Wenn Sie weniger leistungsfähige Hardware verwenden, können Funktionsprobleme oder eine schlechte Leistung auftreten. Beachten Sie, dass diese Hardwareempfehlungen höher als die der früheren Versionen von lync Server sind.

### <a name="hardware-used-in-performance-testing"></a>In Leistungstests verwendete Hardware

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
<td><p>64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher</p>
<p>Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 Gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>8 oder mehr 10.000-RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</p>
<p>Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.</p>
<p>-Oder</p></li>
<li><p>Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000-rpm bieten.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

Eine Übersicht über diese Empfehlungen finden Sie in der folgenden Tabelle.


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
<td><p>80.000 eindeutige Benutzer, die gleichzeitig angemeldet sind, plus 50% mehrere Points of Presence (mpop), die nicht-Mobile Instanzen darstellen, plus 40% der für die Mobilität aktivierten Benutzer für insgesamt 152.000 Endpunkte.</p></td>
</tr>
<tr class="even">
<td><p>A/V-Konferenzen</p></td>
<td><p>Die A/V-Konferenzdienst, die von einem Front-End-Pool bereitgestellt werden, unterstützen die Konferenzen des Pools, vorausgesetzt eine maximale Konferenzgröße von 250 Benutzern und nur eine solche große Konferenz, die gleichzeitig gestartet wird.</p>
<div>

> [!NOTE]  
> Darüber hinaus können Sie große Konferenzen zwischen 250 und 1000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, um die großen Konferenzen zu hosten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-supporting-large-meetings.md">unterstützen großer Besprechungen mit lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Edgeserver</p></td>
<td><p>12.000 gleichzeitige Remotebenutzer</p></td>
</tr>
<tr class="even">
<td><p>Ein Director</p></td>
<td><p>12.000 gleichzeitige Remotebenutzer</p></td>
</tr>
<tr class="odd">
<td><p>Überwachen und Archivieren</p></td>
<td><p>In lync Server 2013 werden die Front-End-Dienste für die Überwachung und Archivierung nun auf jeder Front-End-Server statt auf separaten Server Rollen ausgeführt.</p>
<p>Für die Überwachung und Archivierung sind jeweils weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 ausführen, können Sie Ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL-Datenbank speichern.</p></td>
</tr>
<tr class="even">
<td><p>Ein Vermittlungsserver</p></td>
<td><p>Vermittlungsserver zusammen mit Front-End-Server wird auf allen Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen. Informationen zur eigenständigen Vermittlungsserver finden Sie im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.</p></td>
</tr>
<tr class="odd">
<td><p>Ein Standard Edition-Server</p></td>
<td><p>Wenn Sie Standard Edition-Server zum Hosten von Benutzern verwenden, wird dringend empfohlen, dass Sie immer zwei Server verwenden, gepaart mit den Empfehlungen <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">für die Planung der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</a>. Jeder Server im Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000-Benutzer in einem Failover-Szenario unterstützen.</p>
<p>Wenn Ihre Bereitstellung eine erhebliche Menge an Audio-oder Videodatenverkehr umfasst, leidet die Serverleistung möglicherweise bei mehr als 2.500 Benutzern pro Server. In diesem Fall sollten Sie in Betracht ziehen, weitere Standard Edition-Server hinzuzufügen oder zu lync Server Enterprise Edition zu wechseln.</p></td>
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

In einem Front-End-Pool sollten Sie eine Front-End-Server für alle 6.660-Benutzer haben, die im Pool verwaltet werden, vorausgesetzt, dass das Hyper-Threading auf allen Servern im Pool aktiviert ist und dass die Server Hardware die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000, vorausgesetzt, dass Hyper-Threading auf allen Servern im Pool aktiviert ist. Wenn Sie mehr als 80.000 Benutzer an einem Standort haben, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl von Benutzern in einem Front-End-Pool berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. Wenn beispielsweise 30.000-Benutzer und fünf Front-End-Server vorhanden sind, müssen die Verbindungen von 6000-Benutzern auf die anderen vier Server übertragen werden, wenn ein Server nicht verfügbar ist. Die verbleibenden vier Server verfügen jeweils über 7500 Benutzer, was eine höhere Anzahl als empfohlen.

Wenn Sie stattdessen mit sechs Front-End-Servern für ihre 30.000-Benutzer begonnen und anschließend eine nicht verfügbar waren, werden insgesamt 5000-Benutzer auf die restlichen fünf Server verschoben. Diese fünf Server werden alle Host 6000-Benutzer, die im empfohlenen Bereich ist.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Die maximale Anzahl der Front-End-Server in einem Pool beträgt 12.

Für eine Front-End-Pool mit 80.000-Benutzern genügen zwölf Front-End-Server für die Leistung in typischen Bereitstellungen, die den [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)entsprechen. Für Bereitstellungen zur Unterstützung des Notfall Wiederherstellungs Failovers wird davon ausgegangen, dass maximal 40.000 Benutzer in zwei gekoppelten Front-End-Pools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools unterzubringen, wenn ein Pool fehlerhaft sein muss. auf den anderen.

Die Anzahl der Benutzer, die von einer bestimmten Front-End-Pool mit guter Leistung unterstützt werden, kann aus den folgenden Gründen von diesen Zahlen abweichen:

  - Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - Die Nutzung in Ihrer Organisation unterscheidet sich erheblich von den Benutzermodellen (z. B. deutlich mehr Konferenzdatenverkehr).

<div>


> [!IMPORTANT]  
> In lync Server 2013 werden die Anwesenheits Datenbanken jetzt auf Front-End-Servern gehostet, im Gegensatz zu lync Server 2010, in denen Sie auf dem Back-End-Server gehostet wurden. Dies bedeutet, dass die Datenträgerleistung und-Kapazität Ihrer Front-End-Server nicht von den Empfehlungen, die weiter oben in diesem Abschnitt und in <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>aufgeführt sind, beeinträchtigt werden sollte, unabhängig von der Anzahl der Benutzer, die von ihren Front-End-Servern gehostet werden.



</div>

In der folgenden Tabelle ist die durchschnittliche Bandbreite für Sofortnachrichten und Anwesenheitsinformationen anhand des Benutzermodells dargestellt, wie in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)definiert.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Durchschnittliche Bandbreite pro Benutzer</th>
<th>Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern</th>
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
> Um die Medien Leistung der co-located A/V-Konferenz-und Vermittlungsserver Funktionalität auf Ihren Front-End-Servern zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf Ihren Front-End-Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Bei einem Benutzermodell, bei dem 5 % der Benutzer in einem Pool gleichzeitig an einer Konferenz teilnehmen können, können in einem Pool mit 80.000 Benutzern gleichzeitig ca. 4.000 Benutzer an einer Konferenz teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt. Wenn in Ihrer Organisation beispielsweise wesentlich mehr Konferenzen im gemischten Modus verwendet werden, als im Benutzermodell angenommen werden, müssen Sie u. U. mehr Front-End-Server oder A/V-Konferenzserver bereitstellen, als in diesem Dokument empfohlen. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in lync Server 2013](lync-server-2013-user-models.md).

Die maximale unterstützte Konferenzgröße, die von einer regulären lync Server 2013 gehostet wird Front-End-Pool die auch Benutzer hostet, ist 250 Teilnehmer. Während eine 250-User-Konferenz stattfindet, unterstützt der Pool weiterhin auch andere Konferenzen, sodass sich insgesamt 5% der Pool Benutzer in gleichzeitigen Konferenzen befinden. In einem Pool mit zwölf Front-End-Servern und 80.000-Benutzern unterstützt lync Server beispielsweise 3.750 andere Benutzer, die an kleineren Konferenzen teilnehmen, während die 250-Benutzer Konferenz stattfindet.

Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder Standard Edition-Server verwaltet werden, unterstützt lync Server mindestens 125 andere Benutzer, die an kleineren Konferenzen in demselben Pool oder Server teilnehmen, der eine Konferenz mit 250 Benutzern hostet.

Um Konferenzen mit Benutzern mit 250 und 1000 zu ermöglichen, können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen zu hosten. In diesem Front-End-Pool werden keine Benutzer gehostet. Ausführliche Informationen finden Sie unter [unterstützen großer Besprechungen mit lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Wenn in Ihrer Organisation viel mehr Konferenzen im gemischten Modus stattfinden, die im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server bereitstellen als die Empfehlungen in diesem Dokument (bis zu einem Grenzwert von 12 Fes). Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Edgeserver

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Sie sollten eine Edgeserver für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

<div>


> [!NOTE]  
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, dass Sie einen Director für jeden 12.000-Remotebenutzer bereitstellen, der gleichzeitig auf eine Website zugreift. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.

Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

</div>

<div>

## <a name="mediation-server"></a>Vermittlungsserver

<div>


> [!NOTE]  
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.



</div>

Wenn Sie Vermittlungsserver mit Front-End-Server collocate, wird Vermittlungsserver auf jeder Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserver Pool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für Vermittlungsserver verwendeten Hardware, der Anzahl der VoIP-Benutzer, der Anzahl der Gateway-Peers, die die einzelnen Vermittlungsserver Pools steuert den Datenverkehr über diese Gateways und den Prozentsatz der Anrufe mit Medien, die die Vermittlungsserver umgehen.

Die folgenden Tabellen bieten eine Richtlinie für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, vorausgesetzt, dass die Hardware für die Vermittlungsserver die Anforderungen unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) erfüllt und Hyper-Threading aktiviert ist. Ausführliche Informationen zur Vermittlungsserver Skalierbarkeit finden Sie unter [Estimating Voice usage and Traffic for lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment Guidelines for Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Alle folgenden Tabellen gehen davon aus, dass die Verwendung in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)zusammengefasst wird.

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Eigenständige Vermittlungsserver Kapazität: 70% interne Benutzer, 30% externe Benutzer mit nicht-Bypass-Anrufkapazität (Medien Transkodierung durchgeführt von Vermittlungsserver)

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
<td><p>Dualprozessor, Hex-Kern, 2,26 GHz-Hyper-Threaded-CPU <strong>mit deaktiviertem Hyper-Threading</strong>, mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Dualprozessor, Hex-Kern, 2,26 GHz Hyper-Threaded CPU, mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Für die Leistungstests wurden Server mit 32 GB Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16 GB Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Vermittlungsserver Kapazität (Vermittlungsserver zusammen mit Front-End-Server) 70% interne Benutzer, 30% externe Benutzer, nicht-Bypass-Anrufkapazität (Medienverarbeitung durch Vermittlungsserver durchgeführt)

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
<td><p>Dual Prozessor, Hex-Kern, 2,26 GHz Hyper-Threaded CPU, mit 32 GB Arbeitsspeicher und 2 1GB Netzwerkadapterkarten.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Diese Zahl ist viel kleiner als die Zahlen für die eigenständige Vermittlungsserver, da die Front-End-Server andere Features und Funktionen für die 6600-Benutzer, die auf Ihr verwaltet werden, sowie die für Sprachanrufe erforderliche Transcodierung verarbeiten muss.



</div>

<div>


> [!NOTE]  
> Um die Leistung des Vermittlungsserver zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf Ihren Vermittlungsservern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

<div>

## <a name="back-end-server"></a>Back-End-Server

In lync Server 2013 befinden sich die Anwesenheits Datenbanken auf den Front-End-Servern statt auf dem Back-End-Server. Dies hat zu einer wesentlich einfacheren Anforderung für jeden Back-End-Server in lync Server 2013 geführt, der der Hardwareanforderung für die Front-End-Server entspricht. Kontrastiert dies mit lync Server 2010, bei dem der Back-End-Server ein weitaus höherwertiger Server mit 25 Datenträgern sein muss. Die Arbeitsauslastung von Back-End-Servern ist jedoch immer noch so, dass Sie die Hardwareempfehlungen, die weiter oben in diesem Abschnitt und in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)aufgeführt sind, nicht versäumen sollten.

Um eine hohe Verfügbarkeit des Back-End-Servers bereitzustellen, empfehlen wir die Bereitstellung der Server Spiegelung. Weitere Informationen finden Sie unter [Back End Server High Availability in lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie in lync Server 2013 die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern statt auf separaten Server Rollen ausgeführt. Für die Überwachung und Archivierung wird jeweils weiterhin ein eigener Datenbankspeicher verwendet, getrennt vom Back-End-Speicher. Alternativ können Sie, wenn Sie Exchange 2013 bereitgestellt haben, Sofortnachrichten-Archivierungsdaten in Exchange anstatt in einem dedizierten SQL-Speicher speichern.

Die folgende Tabelle gibt an, wie viel Datenbankspeicher pro Benutzer pro Tag für die Überwachung und Archivierung von Daten erforderlich ist.


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
<td><p><strong>CDR (Überwachung)</strong></p></td>
<td><p><strong>QoE (Überwachung)</strong></p></td>
<td><p><strong>Archivierung</strong></p></td>
</tr>
<tr class="even">
<td><p>Erforderlicher Festplattenspeicher pro Benutzer und Tag</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft hat die Hardware in der folgenden Tabelle für den Datenbankserver für die Überwachung und Archivierung während der Leistungstests verwendet. Bei den Tests wurden die Daten zweier Front-End-Pools gesammelt, von denen jedes 80.000-Benutzer umfasste.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware, die zum Überwachen und Archivieren von Leistungstests verwendet wird

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
<td><p>64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>48 Gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><p>25 10.000-RPM-Festplatten mit 300 GB auf jedem Datenträger mit der folgenden Konfiguration</p>
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
<td><p><strong>Drive</strong></p></td>
<td><p><strong>RAID-Konfiguration</strong></p></td>
<td><p><strong>Anzahl der Datenträger</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR-, QoE-und Archivierungsdatenbank-Datendateien auf einem einzelnen Laufwerk</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>KDS-Datenbankprotokolldatei</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>QoE-Datenbankprotokolldatei</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="odd">
<td><p>Archivierungsdatenbank Protokolldatei</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

