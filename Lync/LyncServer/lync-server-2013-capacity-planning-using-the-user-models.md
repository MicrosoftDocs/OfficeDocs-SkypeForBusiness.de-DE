---
title: 'Lync Server 2013: Kapazitätsplanung mithilfe von Benutzermodellen'
TOCTitle: Kapazitätsplanung mithilfe von Benutzermodellen
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49890841
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kapazitätsplanung mithilfe von Benutzermodellen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt erfahren Sie, wie viele Server Sie an einem Standort für die Anzahl von Benutzern an diesem Standort benötigen, wenn die Nutzung der in [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md) beschriebenen Nutzung entspricht.

## Getestete Hardwareplattform

Alle in diesem Abschnitt enthaltenen Leistungsergebnisse und Bereitstellungsempfehlungen basieren auf Leistungstests mit Servern, auf denen die in der folgenden Tabelle aufgeführte Hardware zum Einsatz kam. Wir empfehlen die Verwendung vergleichbarer Hardware. Wenn Sie weniger leistungsstarke Hardware einsetzen, kann dies zu funktionalen Problemen oder einer schwachen Leistung führen. Beachten Sie, dass die Hardwareempfehlungen über denen für frühere Versionen von Lync Server liegen.

### Bei Leistungstests eingesetzte Hardware

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
<p>Intel Itanium-Prozessoren werden für Lync Server-Serverrollen nicht empfohlen.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 GB</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><ul>
<li><p>8 oder mehr Festplatten mit 10.000 U/Min mit mindestens 72 GB freiem Speicher.</p>
<p>Zwei Festplatten sollten RAID 1 verwenden, und sechs Festplatten sollten RAID 10 verwenden.</p>
<p>- oder -</p></li>
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


## Zusammenfassung der Ergebnisse

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
<td><p>Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder zwei gespiegelten Back-End-Servern.</p></td>
<td><p>80.000 eindeutige Benutzer, plus 50 % Anmeldungen auf mehreren Geräten (Multiple Point Of Presence, MPOP), die keine mobilen Instanzen sind, plus 40 % Benutzer, die für Mobilität aktiviert sind, für insgesamt 152.000 Endpunkte.</p></td>
</tr>
<tr class="even">
<td><p>A/V-Konferenzen</p></td>
<td><p>Der durch einen Front-End-Pool bereitgestellte A/V-Konferenzdienst unterstützt die Konferenzen des Pools unter der Annahme einer maximalen Konferenzgröße von 250 Benutzern und dass jeweils nur eine Konferenz dieser Größe ausgeführt wird.</p>
<div>

> [!NOTE]
> Zusätzlich können Sie große Konferenzen mit 250 bis 1000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, der große Konferenzen hostet. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-supporting-large-meetings.md">Unterstützen von großen Besprechungen mithilfe von Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Ein Edgeserver</p></td>
<td><p>15.000 gleichzeitige Remotebenutzer</p></td>
</tr>
<tr class="even">
<td><p>Ein Director</p></td>
<td><p>15.000 gleichzeitige Remotebenutzer</p></td>
</tr>
<tr class="odd">
<td><p>Überwachen und Archivieren</p></td>
<td><p>In Lync Server 2013 werden die Front-End-Dienste für die Überwachung und Archivierung jetzt auf den einzelnen Front-End-Servern und nicht in separaten Serverrollen ausgeführt.</p>
<p>Für das Überwachen und Archivieren sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie daher Exchange 2013 ausführen, können Sie Ihre Archivdaten in Exchange behalten und benötigen keine dedizierte SQL-Datenbank.</p></td>
</tr>
<tr class="even">
<td><p>Ein Vermittlungsserver</p></td>
<td><p>Der Vermittlungsserver, der mit dem Front-End-Server kombiniert ist, wird auf allen Front-End-Servern in einem Pool ausgeführt und sollte eine für die Benutzer im Pool ausreichende Kapazität bereitstellen. Informationen zu einem eigenständigen Vermittlungsserver finden Sie im weiteren Verlauf dieses Themas unter &quot; Vermittlungsserver&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>Ein Standard Edition-Server</p></td>
<td><p>Wenn Sie Standard Edition-Server zum Hosten von Benutzern verwenden, empfehlen wir Ihnen dringend, unter allen Umständen zwei gemäß den Empfehlungen in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</a> gepaarte Server zu verwenden. Jeder Server des Paars kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server in einem Failoverszenario 5.000 Benutzer unterstützen.</p>
<p>Wenn in Ihrer Bereitstellung große Mengen an Audio- oder Videodatenverkehr anfallen, wird die Serverleistung u. U. auch bei mehr als 2.500 Benutzern pro Server beeinträchtigt. In diesem Fall sollten Sie in Erwägung ziehen, mehrere Standard Edition-Server hinzuzufügen oder die Lync Server- Enterprise Edition zu verwenden.</p></td>
</tr>
</tbody>
</table>


## Front-End-Server


> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.



In einem Front-End-Pool sollten Sie über einen Front-End-Server pro 6.660 Benutzer verfügen, die in dem Pool verwaltet werden. Vorausgesetzt wird dabei, dass auf allen Servern im Pool Hyperthreading aktiviert ist und dass die Hardware die unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) aufgeführten Voraussetzungen erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000, sofern auf allen Servern im Pool Hyperthreading aktiviert ist. Wenn Sie über mehr als 80.000 Benutzer an einem Standort verfügen, können Sie mehrere Front-End-Pools bereitstellen.

Wenn Sie die Anzahl von Benutzern in einem Front-End-Pool berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. Beispiel: Wenn Sie über 30.000 Benutzer und fünf Front-End-Server verfügen und ein Server ausfällt, müssen die Verbindungen von 6.000 Benutzern an die anderen vier Server übertragen werden. Auf den übrigen vier Servern werden in diesem Fall je 7.500 Benutzer verwaltet, sodass der empfohlene Maximalwert überschritten wird.

Wenn Sie stattdessen für Ihre 30.000 Benutzer mit sechs Front-End-Servern anfangen, von denen einer anschließend nicht mehr verfügbar ist, werden insgesamt 5.000 Benutzer an die verbleibenden fünf Server übertragen. Diese fünf Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Die maximale Anzahl von Front-End-Servern in einem Pool beträgt 12.

Für einen Front-End-Pool mit 80.000 Benutzern bieten zwölf Front-End-Server in üblichen Bereitstellungen eine ausreichende Leistung, die den [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md) entsprechen. Bereitstellungen, die ein Failover für die Notfallwiederherstellung vorsehen, gehen davon aus, dass maximal 40.000 Benutzer in einem der beiden kombinierten Front-End-Pools gehostet werden können, von denen jeder Pool ausreichend Front-End-Server besitzt, um die Benutzer beider Pools aufzunehmen, falls ein Pool ausfällt.

Die Anzahl der durch einen bestimmten Front-End-Pool mit einer guten Leistung unterstützten Benutzer kann aus folgenden Gründen von dieser Zahl abweichen:

  - Die Hardware für Ihre Front-End-Server-Server entspricht nicht den Empfehlungen in [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - Die Nutzung in Ihrer Organisation unterscheidet sich erheblich von den Benutzermodellen (z. B. deutlich mehr Konferenzdatenverkehr).


> [!IMPORTANT]
> In Lync Server 2013 werden die Anwesenheitsdatenbanken jetzt auf den Front-End-Servern gehostet, während sie in Lync Server 2010 auf dem Back-End-Server gehostet wurden. Dies bedeutet, dass die Festplattenleistung und die Kapazität Ihrer Front-End-Server durch die vorab in diesem Abschnitt und unter <A href="lync-server-2013-server-hardware-platforms.md">Serverhardwareplattformen für Lync Server&nbsp;2013</A> aufgeführten Empfehlungen nicht beeinträchtigt werden und dies unabhängig von der Anzahl der durch Ihre Front-End-Server gehosteten Benutzer.



Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Sofortnachrichten- und Anwesenheitsdaten basierend auf dem Benutzermodell, das in [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md) beschrieben ist.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Durchschnittliche Bandbreite pro Benutzer</th>
<th>Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 KBit/s</p></td>
<td><p>13 MBit/s</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Zur Verbesserung der Medienleistung der zusammengestellten A/V-Konferenz- und der Vermittlungsserverfunktion auf Ihren Front-End-Servern müssen Sie auf den Netzwerkadaptern Ihrer Front-End-Server RSS (Receive-Side Scaling) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen dazu finden Sie in "Receive-Side Scaling Enhancements in Windows Server 2008" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



## Maximale Anzahl von Benutzern für Konferenzen

Bei einem Benutzermodell, bei dem 5 % der Benutzer in einem Pool gleichzeitig an einer Konferenz teilnehmen können, können in einem Pool mit 80.000 Benutzern gleichzeitig ca. 4.000 Benutzer an einer Konferenz teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z. B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt. Wenn in Ihrer Organisation beispielsweise wesentlich mehr Konferenzen im gemischten Modus verwendet werden, als im Benutzermodell angenommen werden, müssen Sie u. U. mehr Front-End-Server oder A/V-Konferenzserver bereitstellen, als in diesem Dokument empfohlen. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md).

Die maximal unterstützte Konferenzgröße in einem normalen Lync Server 2013- Front-End-Pool beträgt 250 Teilnehmer. Wenn eine Konferenz dieser Größe stattfindet, kann der Pool weiterhin andere Konferenzen unterstützen. Während einer Konferenz mit 250 Benutzern unterstützt der Pool weiterhin insgesamt 5 % der Poolbenutzer in gleichzeitigen Konferenzen. In einem Pool mit zwölf Front-End-Servern und 80.000 Benutzern unterstützt Lync Server während einer Konferenz mit 250 Teilnehmern z. B. die Teilnahme weiterer 3.750 Benutzer an kleineren Konferenzen.

Unabhängig von der Anzahl von Benutzern, die im Front-End-Pool oder auf dem Standard Edition-Server verwaltet werden, unterstützt Lync Server mindestens 125 weitere Benutzer, die während einer Konferenz mit 250 Benutzern in demselben Pool an kleineren Konferenzen teilnehmen.

Zum Aktivieren von Konferenzen mit 250 bis 1.000 Benutzern können Sie einen separaten Front-End-Pool einrichten, der nur diese Konferenzen hostet. Dieser Front-End-Pool hostet keine Benutzer. Ausführliche Informationen finden Sie unter [Unterstützen von großen Besprechungen mithilfe von Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Wenn Ihre Organisation weitaus mehr Konferenzen im gemischten Modus hat, als dies im Benutzermodell angenommen wird, müssen Sie gegebenenfalls mehr Front-End-Server bereitstellen, als dies hier empfohlen wird (bis zu einer Obergrenze von 12 FEs). Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md).

## Edgeserver


> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.



Sie sollten einen Edgeserver pro 12.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen werden. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. Diese Empfehlungen gehen davon aus, dass die Hardware für Ihre Edgeserver die Empfehlungen unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) erfüllt.

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.


> [!NOTE]
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



## Director


> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.



Wenn Sie die Serverrolle Director bereitstellen, empfiehlt es sich, einen Director für jeweils 12.000 Remotebenutzer bereitzustellen, die gleichzeitig auf einen Standort zugreifen. Wir empfehlen mindestens zwei Directors, um eine hohe Verfügbarkeit sicherzustellen. Diese Empfehlungen gehen davon aus, dass die Hardware für Ihre Edgeserver die Empfehlungen unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) erfüllt.

Wenn Sie die Anzahl von Benutzern für die Directors berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

## Vermittlungsserver


> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.



Wenn Sie den Vermittlungsserver mit dem Front-End-Server verbinden, wird der Vermittlungsserver für jeden Front-End-Server im Pool ausgeführt und sollte eine für die Benutzer im Pool ausreichende Kapazität bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserver-Pool bereitstellen, hängt die Anzahl der erforderlichen Vermittlungsserver von verschiedenen Faktoren ab. Dazu zählen u. a. die für den Vermittlungsserver verwendete Hardware, die Anzahl von VoIP-Benutzern, die Anzahl von Gatewaypeers, die über die einzelnen Vermittlungsserverpools gesteuert werden, der Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird, sowie der Prozentsatz von Anrufen mit Medien, die den Vermittlungsserver umgehen.

Die folgenden Tabellen enthalten Richtlinien für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, sofern die Hardware für die Vermittlungsserver den unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) definierten Anforderungen entsprechen und Hyperthreading aktiviert ist. Ausführliche Informationen zur Skalierbarkeit des Vermittlungsservers finden Sie unter [Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) und [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)..

Alle folgenden Tabellen gehen von einer Verwendung entsprechend der unter [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md) zusammengefassten Verwendung aus.

### Kapazität eigenständiger Vermittlungsserver: 70 % interne Benutzer, 30 % externe Benutzer, mit Anrufen ohne Umgehung (Medientranscodierung durch Vermittlungsserver)

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
<td><p>Dualprozessor, Vierkern, Hyperthreading-CPU mit 2,26 GHz <strong>und deaktiviertem Hyperthreading</strong>, 32 GB Arbeitsspeicher und einem Dualport-Netzwerkadapter.</p></td>
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



> [!NOTE]
> Für die Leistungstests wurden Server mit 32&nbsp;GB&nbsp;Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16&nbsp;GB&nbsp;Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.



### Vermittlungsserver Kapazität ( Vermittlungsserver verbunden mit Front-End-Server) 70 % interne Benutzer, 30 % externe Benutzer, keine Anruffunktion mit Medienumgehung (Medienverarbeitung durch Vermittlungsserver)

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



> [!NOTE]
> Diese Anzahl ist viel kleiner als die Anzahl für den eigenständigen Vermittlungsserver, da der Front-End-Server, zusätzlich zu der für die VoIP-Anrufe erforderlichen Transcodierung, andere Funktionen für die darin vorhandenen über 6.600 Benutzer übernimmt.




> [!NOTE]
> Zur Verbesserung der Leistung des Vermittlungsservers sollten Sie auf den Netzwerkadaptern Ihrer Vermittlungsserver RSS aktivieren. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Ausführliche Informationen finden Sie in "Receive-Side Scaling Enhancements in Windows Server 2008" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



## Back-End-Server

In Lync Server 2013 befindet sich die Anwesenheitsdatenbank auf den Front-End-Servern anstatt auf dem Back-End-Server. Dies hat die Anforderungen an die einzelnen Back-End-Server in Lync Server 2013 stark vereinfacht. Dasselbe gilt für die Hardwareanforderung für den Front-End-Server. Vergleichen Sie dies mit Lync Server 2010, wo der Back-End-Server einen weitaus leistungsstärkeren Server mit 25 Festplatten erfordert. Die Arbeitslast der Back-End-Server ist jedoch weiterhin so hoch, dass Sie die in diesem Abschnitt und in [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) aufgeführten Hardwareempfehlungen erfüllen sollten.

Zur Sicherstellung einer hohen Verfügbarkeit Ihres Back-End-Servers empfiehlt sich die Bereitstellung einer Serverspiegelung. Weitere Informationen finden Sie unter [Hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

## Überwachen und Archivieren

In Lync Server 2013 wird bei der Bereitstellung der Überwachung oder der Archivierung die Front-End-Funktion dieser Dienste auf den Front-End-Servern ausgeführt, anstatt in separaten Serverrollen. Die Überwachung und die Archivierung verwenden weiterhin ihren jeweils eigenen Datenbankspeicher, getrennt vom Back-End-Speicher. Alternativ können Sie, sofern Exchange 2013 bereitgestellt ist, die Archivdaten von Sofortnachrichten in Exchange speichern, anstatt in einem dedizierten SQL-Speicher.

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
<td><p></p></td>
<td><p><strong>KDS (Überwachung)</strong></p></td>
<td><p><strong>QoE (Überwachung)</strong></p></td>
<td><p><strong>Archivieren</strong></p></td>
</tr>
<tr class="even">
<td><p>Pro Benutzer und Tag benötigter Festplattenspeicher</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft hat bei den Leistungstests für den Datenbankserver die in der folgenden Tabelle aufgeführte Hardware für die Überwachung und Archivierung eingesetzt. Der Test hat die Daten von zwei Front-End-Pools erfasst, die jeweils 80.000 Benutzer enthielten.

### Beim Leistungstest der Überwachung und Archivierung eingesetzte Hardware

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
<td><p>1 + 0</p></td>
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


## In diesem Abschnitt

  - [Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

