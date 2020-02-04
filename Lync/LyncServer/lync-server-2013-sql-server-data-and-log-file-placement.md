---
title: 'Lync Server 2013: Platzierung von SQL Server-Daten und Protokolldatei'
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
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bei der Planung und Bereitstellung von Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2 SP1 für Ihren lync Server 2013-Front-End-Pool ist es wichtig, dass Daten und Protokolldateien auf physischen Festplatten zur Leistung platziert werden. Die empfohlene Festplattenkonfiguration besteht in der Implementierung eines 1 +1-RAID-Satzes mit 6 Spindeln. Platzieren aller vom Front-End-Pool verwendeten Datenbank-und Protokolldateien und der zugehörigen Serverrollen und Dienste (also Archivierungs-und Überwachungsserver, lync Server-Reaktionsgruppendienst, lync Server-Anruf Park Dienst) auf dem RAID-Laufwerk, das mit dem lync-Server festgesetzt wird Der Bereitstellungs-Assistent führt zu einer Konfiguration, die auf eine gute Leistung getestet wurde. Die Datenbankdateien und deren Verantwortlichkeiten sind in der folgenden Tabelle aufgeführt.

<div>


> [!NOTE]  
> Wenn für Ihre Richtlinien und SQL Server-Konfigurationen eine spezialisiertere Installation erforderlich ist, können die Datenbank-und Protokolldateien mithilfe der lync Server-Verwaltungsshell an einem beliebigen vordefinierten Speicherort installiert werden. Weitere Informationen finden Sie unter <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Datenbankinstallation mithilfe der lync Server-Verwaltungsshell in lync Server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Daten-und Protokolldateien für den zentralen Verwaltungsspeicher

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zentrale Verwaltungsspeicher-Datenbankdateien</th>
<th>Datendatei oder Protokoll Zweck</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Transaktionsprotokolldatei für den zentralen Verwaltungsspeicher</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Verwaltet die Konfiguration der aktuellen lync Server 2013-Topologie, wie Sie vom Topologie-Generator definiert und veröffentlicht wurde</p></td>
</tr>
<tr class="odd">
<td><p>LIS. mdf</p></td>
<td><p>Datendatei des Standort Informationsdiensts</p></td>
</tr>
<tr class="even">
<td><p>LIS. ldf</p></td>
<td><p>Transaktionsprotokoll für die Datendatei des Standort Informationsdiensts</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Daten-und Protokolldateien für Benutzer, Konferenz und Adressbuch

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Core lync Server 2013-Datenbankdateien</th>
<th>Datendatei oder Protokoll Zweck</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. mdf</p></td>
<td><p>Beständige Benutzerdaten (beispielsweise Zugriffssteuerungslisten (ACLs), Kontakte, geplante Konferenzen)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Transaktionsprotokoll für RTC-Daten</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. mdf</p></td>
<td><p>Pflegt vorübergehende Benutzerdaten (Anwesenheits Laufzeitdaten)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Transaktionsprotokoll für RTCDyn-Daten</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. mdf</p></td>
<td><p>RTC-Adressbuchdatenbank (Echtzeitkommunikation) ist das SQL Server-Repository, in dem Adressbuchdienst Informationen gespeichert werden.</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Transaktionsprotokoll für Adressbuchdienst</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Gastgeber des Konferenz Verzeichnisses</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. mdf</p></td>
<td><p>Verwaltet die Sicherung für Benutzerdaten</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Transaktionsprotokoll für Rtcxds-Daten</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Daten-und Protokolldateien für den Anruf Park und die Reaktionsgruppe

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Anwendungsdatenbank</th>
<th>Datendatei oder Protokoll Zweck</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. mdf</p></td>
<td><p>Dynamische Informationsdatenbank für die Anwendung "Parken des Anrufs"</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Transaktionsprotokoll für die APP-Datendatei des Anruf Parks</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. mdf</p></td>
<td><p>Lync Server Response Group Service-Datendatei für die Konfiguration der Dienste</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Transaktionsprotokolldatei für die Anwendungskonfiguration der Reaktionsgruppe</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. mdf</p></td>
<td><p>Datendatei des Reaktionsgruppendiensts für Laufzeitvorgänge</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Transaktionsprotokoll für die Datendatei der Reaktionsgruppendienst-Laufzeit</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Daten-und Protokolldateien für Archivierungs-und Überwachungs Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivieren und Überwachen von Datenbankdateien</th>
<th>Datendatei oder Protokoll Zweck</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. mdf</p></td>
<td><p>Datenspeicher für den Prozess der Anrufdetailaufzeichnung (CDR) des Überwachungsservers</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Transaktionslog für Daten zur Anrufdetailaufzeichnung (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>Datenbank QoEMetrics werden. mdf</p></td>
<td><p>Auf dem Überwachungs Server gespeicherte Datendatei mit hoher Qualität</p></td>
</tr>
<tr class="even">
<td><p>Datenbank QoEMetrics werden. ldf</p></td>
<td><p>Transaktionslog zum Überwachen von Daten</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog. mdf</p></td>
<td><p>Datendatei zur Aufbewahrung von Sofortnachrichten und Konferenzdaten auf einem Archivierungs Server</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. ldf</p></td>
<td><p>Transaktionsprotokoll zum Archivieren von Daten</p></td>
</tr>
</tbody>
</table>


In diesem Thema werden Verweise auf die Festplatte und auf RAID festgesetzt. Beachten Sie, dass bei der Konfiguration von SQL Server-Ressourcen ein einzelnes Hardwaregerät auf einen Datenträger verweist. Ein Festplattenlaufwerk mit zwei Partitionen, einem Protokolldateien und der anderen Partition, in der Datendateien gespeichert sind, ist nicht mit zwei Festplatten identisch, die jeweils für Protokoll-oder Datendateien reserviert sind.

In Bezug auf RAID-Sets gibt es eine Reihe unterschiedlicher RAID-Technologien verschiedener Anbieter. Und mit der Verbreitung von San (Storage Area Networks) sind RAID-Sätze, die einem einzigen System gewidmet sind, seltener. Wenden Sie sich an Ihren RAID-oder SAN-Anbieter, um zu ermitteln, welche Konfiguration für das Festplattenlayout am besten geeignet ist, wenn Sie die Leistung von SQL Server mit lync Server 2013 konfigurieren.

Beachten Sie auch, dass nicht alle Festplatten gleichermaßen erstellt werden. einige funktionieren besser als andere. Auch Laufwerke desselben Herstellers können aufgrund von Drehzahl, Hardwarecache Größe und anderen Faktoren in der Leistung variieren.

</div>

<span> </span>

</div>

</div>

</div>

