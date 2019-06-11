---
title: 'Lync Server 2013: ProgressReport-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>ProgressReport-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Statusberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung an die Datenbank hochgeladen wurden. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können.

Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben.


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
<td><p><strong>Fehlerzeit</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Datum und Uhrzeit des Status Fehlerberichts, der diesen Statusbericht enthält. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>ID-Nummer, die in Verbindung mit Fehlerzeit verwendet wird, ProgressReportSeq, um einen Statusbericht eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Die ID-Nummer, die den Fehlerbericht identifiziert. ErrorReporSeq wird in Verbindung mit Fehlerzeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-errorreport-table.md">in der errorreport-Tabelle in lync Server 2013</a> .</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Die ID-Nummer zur Identifizierung des Statusberichts. Wird in Verbindung mit Fehlerzeit und ErrorReportSeq verwendet, um einen Statusbericht eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Diagnose-ID des Statusberichts</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde). Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> . Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Der lync-Server Prozess, zu dem der Bericht gehört. Weitere Informationen finden Sie in der Anwendungstabelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>Bild</p></td>
<td></td>
<td><p>Details des Statusberichts, die im Binärformat gespeichert werden, um Platz zu sparen. Diese Daten können mit dieser Syntax in das Text Format konvertiert werden:</p>
<p>Umwandlung (Umwandlung (Detail als varbinary (max)) als varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Eindeutiger Bezeichner, der die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Zeit (in Millisekunden) für eine bestimmte Komponente, um an einer Konferenz teilzunehmen.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

