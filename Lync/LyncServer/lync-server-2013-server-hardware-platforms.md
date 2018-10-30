---
title: Serverhardwareplattformen für Lync Server 2013
TOCTitle: Serverhardwareplattformen
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398835(v=OCS.15)
ms:contentKeyID: 49295391
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Serverhardwareplattformen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für Serverrollen von Lync Server 2013 und für Computer, auf denen die Verwaltungstools von Lync Server ausgeführt werden, ist 64-Bit-Hardware erforderlich.

Die für die Lync Server 2013-Bereitstellung benötigte Hardware richtet sich nach den Anforderungen an Größe und Verwendung der Bereitstellung. In diesem Abschnitt wird die empfohlene Hardware beschrieben. Wenngleich es sich hier nicht um Anforderungen, sondern um Empfehlungen handelt, kann der Einsatz von Hardware, die diesen Empfehlungen nicht entspricht, zu erheblichen Leistungsproblemen und sonstigen Problemen führen.

## Empfohlene Hardwareplattform

Für eine optimale Leistung wird empfohlen, Lync Server auf Servern mit Hardware auszuführen, die die in der folgenden Tabelle aufgeführten Anforderungen erfüllt. Falls Sie nicht so leistungsfähige Hardware verwenden, können Funktionalitätsprobleme oder Leistungseinbußen auftreten. Beachten Sie, dass diese Hardwareanforderungen höher als bei früheren Versionen von Lync Server sind. Dies liegt in erster Linie daran, dass bei Lync Server 2013 auf allen Front-End-Servern SQL Server ausgeführt wird.


> [!NOTE]
> Der NIC-Teamvorgang wird unterstützt und sollte für Lync Server transparent sein. Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming (Kommunikationsserver oder Lync Server und Teamvorgang für Netzwerkadapter)</A>.



### Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server, Server für beständigen Chat, Speicher für beständigen Chat und Compliance-Speicher für beständigen Chat (Back-End-Serverrollen für Server für beständigen Chat)

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
<p>Intel Itanium-Prozessoren werden für Serverrollen von Lync Server nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 GB</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz</p>
<p>Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.</p>
<p>– ODER –</p></li>
<li><p>Festkörperlaufwerke (SSDs) mit einer ähnlichen Leistung wie 8 mechanische Laufwerke mit 10.000 U/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist).</p>
<div>

> [!NOTE]
> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt.<BR>Verbindungen über ILO, DRAC usw., die für das Betriebssystem nicht verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, stellen keinen mehrfach vernetzten Server dar und werden daher unterstützt.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors

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
<td><ul>
<li><p>64-Bit-Dualprozessor, Vierkern, mindestens 2,0 GHz</p>
<p>– ODER –</p></li>
<li><p>64-Bit-4-Wege-Prozessor, Doppelkern, mindestens 2,0 GHz</p></li>
</ul>
<p>Intel Itanium-Prozessoren werden für Serverrollen von Lync Server nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>16 GB</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz</p>
<p>Die Festplatten sollten in einer 2x-RAID-1-Konfiguration angeordnet sein.</p>
<p>– ODER –</p></li>
<li><p>Festkörperlaufwerke (SSDs) mit einer ähnlichen Leistung wie 4 mechanische Laufwerke mit 10.000 U/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist). Für Edgeserver sind 2 Netzwerkschnittstellen erforderlich, und für eigenständige Vermittlungsserver werden sie unterstützt.</p></li>
</ul>
<div>

> [!NOTE]
> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Directors nicht unterstützt.<BR>Verbindungen über ILO, DRAC usw., die für das Betriebssystem nicht verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, stellen keinen mehrfach vernetzten Server dar und werden daher unterstützt.


</div>
<p>Edgeserver benötigen zwei Netzwerkschnittstellen mit folgenden Merkmalen: Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (oder zwei Netzwerkadapterpaare (insgesamt vier Netzwerkadapter), die als Team mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse konfiguriert sind (insgesamt zwei Paare)).</p>
<p>Die Installation von zusätzlichen Netzwerkadaptern, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen, wird für eigenständige Vermittlungsserver unterstützt.</p></td>
</tr>
</tbody>
</table>

