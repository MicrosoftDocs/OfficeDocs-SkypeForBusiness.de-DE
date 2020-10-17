---
title: 'Lync Server 2013: Platzierung von Daten und Protokolldateien SQL Server'
description: 'Lync Server 2013: SQL Server der Daten-und Protokolldatei Platzierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558281"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>SQL Server der Daten-und Protokolldatei Platzierung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihre lync Server 2013 Front-End-Pool, ist es wichtig, dass Daten und Protokolldateien für die Leistung auf physischen Festplatten platziert werden. Die empfohlene Datenträgerkonfiguration besteht in der Implementierung eines 1 +1-RAID-Satzes mit 6 Spindeln. Wenn Sie alle Datenbank-und Protokolldateien, die von der Front-End-Pool und den zugehörigen Serverrollen und-Diensten verwendet werden (also Archivierungs-und Monitoring Server, lync Server Reaktionsgruppendienst, lync Server Dienst zum Parken von Anrufen) auf dem RAID-Laufwerk mit dem lync Server-Bereitstellungs-Assistenten platzieren, wird eine Konfiguration mit einer guten Leistung getestet. Die Datenbankdateien und deren Verantwortlichkeiten sind in der folgenden Tabelle aufgeführt.

<div>


> [!NOTE]  
> Wenn für Ihre Richtlinien und SQL Server Konfigurationen eine speziellere Installation erforderlich ist, können die Datenbank-und Protokolldateien mithilfe der lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden. Weitere Informationen finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Daten- und Protokolldateien für den zentralen Verwaltungsspeicher

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenbankdateien des zentralen Verwaltungsspeichers</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Transaktionsprotokolldatei für den zentralen Verwaltungsspeicher</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Verwaltet die Konfiguration der aktuellen lync Server 2013 Topologie, wie Sie vom Topologie-Generator definiert und veröffentlicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>LIS. mdf</p></td>
<td><p>Standortinformationsdienst-Datendatei</p></td>
</tr>
<tr class="even">
<td><p>LIS. ldf</p></td>
<td><p>Transaktionsprotokoll für die Standortinformationsdienst-Datendatei</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Daten- und Protokolldateien für Benutzer, Konferenzen und Adressbuch

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kern lync Server 2013-Datenbankdateien</th>
<th>Zweck der Daten- oder Protokolldatei</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. mdf</p></td>
<td><p>Persistente Benutzerdaten (beispielsweise Zugriffssteuerungslisten (Access Control Lists, ACLs), Kontakte, geplante Konferenzen)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Transaktionsprotokoll für RTC-Daten</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. mdf</p></td>
<td><p>Verwaltet transiente Benutzerdaten (Anwesenheits Laufzeitdaten)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Transaktionsprotokoll für RTCDyn-Daten</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. mdf</p></td>
<td><p>Die RTC-Adressbuchdatenbank (Real-Time Communications) ist das SQL Server-Repository, in dem Informationen des Adressbuchdiensts gespeichert werden</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Transaktionsprotokoll für den Adressbuchdienst</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Hostet das Konferenzverzeichnis</p></td>
</tr>
<tr class="even">
<td><p>"Rtcxds". mdf</p></td>
<td><p>Verwaltet die Sicherung für Benutzerdaten.</p></td>
</tr>
<tr class="odd">
<td><p>"Rtcxds". ldf</p></td>
<td><p>Transaktionsprotokoll für "rtcxds"-Daten</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Daten- und Protokolldateien für das Parken von Anrufen und Reaktionsgruppen

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
<td><p>Cpsdyn. mdf</p></td>
<td><p>Dynamische Informationsdatenbank für den Anwendung zum Parken von Anrufen</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Transaktionsprotokoll für Anwendung zum Parken von Anrufen Datendatei</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. mdf</p></td>
<td><p>Datendatei für den Lync Server-Reaktionsgruppendienst zur Konfiguration der Dienste</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Transaktionsprotokolldatei für die Reaktionsgruppenanwendung Konfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. mdf</p></td>
<td><p>Datendatei des Reaktionsgruppendiensts für Laufzeitoperationen</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Transaktionsprotokoll für die Laufzeitdatendatei des Reaktionsgruppendiensts</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Daten- und Protokolldateien für den Archivierungs- und Monitoring Server

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
<td><p>LcsCdr. mdf</p></td>
<td><p>Datenspeicher für den CdR-Prozess (Call Detail Recording) des Monitoring Server</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Transaktionsprotokoll für KDS-Daten</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. mdf</p></td>
<td><p>Von der Monitoring Server gespeicherte Quality of Experience-Datendatei</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Transaktionsprotokoll für Überwachungsdaten</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog. mdf</p></td>
<td><p>Datendatei für die Aufbewahrung von Instant Messaging-und Konferenzdaten auf einem Archivierungsserver</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. ldf</p></td>
<td><p>Transaktionsprotokoll für Archivierungsdaten</p></td>
</tr>
</tbody>
</table>


In diesem Thema wird auf Datenträger und RAID-Sätze verwiesen. Bei der Konfiguration von SQL Server-Ressourcen bezieht sich der Begriff "Datenträger" auf ein einzelnes Hardwaregerät. Ein Festplattenlaufwerk mit zwei Partitionen (je eine Partition für Protokoll- und Datendateien) ist nicht dasselbe wie zwei Datenträger, die als zwei dedizierte Komponenten für Protokoll- bzw. Datendateien eingesetzt werden.

Bei RAID-Sätzen sind unterschiedliche RAID-Technologien von verschiedenen Anbietern verfügbar. Und mit dem verstärkten Einsatz von SANs (Storage Area Networks) werden dedizierte RAID-Sätze für ein einzelnes System seltener. Sie sollten sich mit Ihrem RAID-oder SAN-Anbieter beraten lassen, um festzustellen, welche Konfiguration für das Datenträgerlayout am besten geeignet ist, wenn Sie für SQL Server Leistung mit lync Server 2013 konfigurieren.

Beachten Sie, dass nicht alle Festplattenlaufwerke identisch gefertigt werden, sodass einige Laufwerke eine bessere Leistung bieten als andere. Selbst bei Laufwerken eines Herstellers kann die Leistung aufgrund von Drehgeschwindigkeit, Größe des Hardwarezwischenspeichers und anderen Faktoren variieren.

</div>

<span> </span>

</div>

</div>

</div>

