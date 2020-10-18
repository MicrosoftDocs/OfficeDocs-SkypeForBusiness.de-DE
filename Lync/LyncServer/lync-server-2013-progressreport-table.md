---
title: 'Lync Server 2013: ProgressReport-Tabelle'
description: 'Lync Server 2013: ProgressReport-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579821"
---
# <a name="progressreport-table-in-lync-server-2013"></a>ProgressReport-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden. Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt.

Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fehler</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Datum und Uhrzeit des Fortschritts Fehlerberichts, der diesen Fortschrittsbericht enthält. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID-Nummer, die in Verbindung mit Error-ProgressReportSeq verwendet wird, um einen Statusbericht eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID-Nummer, die den Fehlerbericht identifiziert. ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Identifikation des Fortschrittsberichts. Wird zusammen mit ErrorTime und ErrorReportSeq zur eindeutigen Identifikation eines Fortschrittsberichts verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Die Diagnose-ID des Fortschrittberichts.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde). Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Der Lync Server-Vorgang, auf den sich der Bericht bezieht. Weitere Informationen finden Sie in der Anwendungstabelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>Abbildung</p></td>
<td></td>
<td><p>Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax in ein Textformat konvertiert werden.</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Eindeutige ID, die Informationen zum Zeitpunkt des Konferenzbeitritts für die verschiedenen an der Konferenz beteiligten Komponenten korreliert.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Zeit (in Millisekunden) für den Konferenzbeitritt einer bestimmten Komponente.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

