---
title: 'Lync Server 2013: Platzierung von SQL Server-Daten und Protokolldatei'
TOCTitle: Platzierung von SQL Server-Daten und Protokolldatei
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398479(v=OCS.15)
ms:contentKeyID: 49294257
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihren Lync Server 2013- Front-End-Pool ist die Platzierung der Daten und Protokolldateien auf physischen Festplatten für die Leistung entscheidend. Die empfohlene Festplattenkonfiguration sieht die Implementierung eines 1+0-RAID-Satzes mit sechs Spindeln vor. Die Platzierung aller vom Front-End-Pool verwendeten Datenbank- und Protokolldateien sowie zugehöriger Serverrollen und -dienste (d. h. Archivierungs- und Monitoring Server, Lync Server-Reaktionsgruppendienst, Lync Server-Dienst zum Parken von Anrufen) auf dem RAID-Festplattensatz mithilfe des Lync Server-Bereitstellungs-Assistents sorgt für eine Konfiguration, deren gute Leistung in Tests nachgewiesen wurde. Die Datenbankdateien und deren Zwecke sind in der folgenden Tabelle erläutert.


> [!NOTE]
> Wenn Ihre Richtlinien und SQL&nbsp;Server-Konfigurationen eine speziellere Installation erfordern, können die Datenbank- und Protokolldateien mithilfe der Lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden. Weitere Einzelheiten finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013</A>.



### Daten- und Protokolldateien für den zentralen Verwaltungsspeicher

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenbankdateien für zentralen Verwaltungsspeicher</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds.ldf</p></td>
<td><p>Transaktionsprotokolldatei für zentralen Verwaltungsspeicher</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>Zur Verwaltung der Konfiguration der aktuellen Lync Server 2013-Topologie gemäß Definition und Veröffentlichung per Topologie-Generator</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>Datendatei des Standortinformationsdiensts</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>Transaktionsprotokoll für die Datendatei des Standortinformationsdiensts</p></td>
</tr>
</tbody>
</table>


### Daten- und Protokolldateien für Benutzer, Konferenzen und Adressbuch

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Die wichtigsten Lync Server 2013-Datenbankdateien</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc.mdf</p></td>
<td><p>Dauerhafte Benutzerdaten (beispielsweise Zugriffssteuerungslisten, Kontakte, geplante Konferenzen)</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Transaktionsprotokoll für Rtc-Daten</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>Zur Verwaltung temporärer Benutzerdaten (Anwesenheitslaufzeitdaten)</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Transaktionsprotokoll für Rtcdyn-Daten.</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>Die RTC-Adressbuchdatenbank (Real-Time Communications) ist das SQL Server-Repository, in dem Informationen des Adressbuchdiensts gespeichert werden</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>Transaktionsprotokoll für den Adressbuchdienst</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>Hostet das Konferenzverzeichnis</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>Wartet die Sicherung für Benutzerdaten</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Transaktionsprotokoll für Rtcxds-Daten.</p></td>
</tr>
</tbody>
</table>


### Daten- und Protokolldateien für das Parken von Anrufen und Reaktionsgruppen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Anwendungsdatenbank</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn.mdf</p></td>
<td><p>Datenbank mit dynamischen Informationen für die Anwendung zum Parken von Anrufen</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>Transaktionsprotokoll für die Datendatei der Anwendung zum Parken von Anrufen</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>Datendatei für den Lync Server-Reaktionsgruppendienst zur Konfiguration der Dienste</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>Transaktionsprotokolldatei für die Konfiguration der Reaktionsgruppenanwendung</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>Datendatei des Reaktionsgruppendiensts für Laufzeitoperationen</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>Transaktionsprotokoll für die Laufzeitdatendatei des Reaktionsgruppendiensts</p></td>
</tr>
</tbody>
</table>


### Daten- und Protokolldateien für den Archivierungs- und Monitoring Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenbankdateien für Archivierung und Überwachung</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr.mdf</p></td>
<td><p>Datenspeicher für den Prozess zur Aufzeichnung von Kommunikationsdatensätzen (KDS) des Monitoring-Servers</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>Transaktionsprotokoll für KDS-Daten</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>Gespeicherte Quality of Experience-Datendatei vom Monitoring-Server</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>Transaktionsprotokoll für Überwachungsdaten</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>Datendatei für die Aufbewahrung von Sofortnachrichten- und Konferenzdaten auf einem Archivierungsserver</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>Transaktionsprotokoll für Archivierungsdaten</p></td>
</tr>
</tbody>
</table>


In diesem Thema wird auf Datenträger und RAID-Sätze verwiesen. Bei der Konfiguration von SQL Server-Ressourcen bezieht sich der Begriff "Datenträger" auf ein einzelnes Hardwaregerät. Ein Festplattenlaufwerk mit zwei Partitionen (je eine Partition für Protokoll- und Datendateien) ist nicht dasselbe wie zwei Datenträger, die als zwei dedizierte Komponenten für Protokoll- bzw. Datendateien eingesetzt werden.

Bei RAID-Sätzen sind unterschiedliche RAID-Technologien von verschiedenen Anbietern verfügbar. Und mit dem verstärkten Einsatz von SANs (Storage Area Networks) werden dedizierte RAID-Sätze für ein einzelnes System seltener. Kontaktieren Sie Ihren RAID- oder SAN-Anbieter, um die beste Konfiguration für Ihr Datenträgerlayout zu ermitteln, wenn Sie Ihre Umgebung für eine hohe Leistung von SQL Server mit Lync Server 2013 konfigurieren.

Beachten Sie, dass nicht alle Festplattenlaufwerke identisch gefertigt werden, sodass einige Laufwerke eine bessere Leistung bieten als andere. Selbst bei Laufwerken eines Herstellers kann die Leistung aufgrund von Drehgeschwindigkeit, Größe des Hardwarezwischenspeichers und anderen Faktoren variieren.

