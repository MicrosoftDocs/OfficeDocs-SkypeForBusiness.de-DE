---
title: 'Lync Server 2013: ProgressReport-Ansicht'
description: 'Lync Server 2013: ProgressReport-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579791"
---
# <a name="progressreport-view-in-lync-server-2013"></a>ProgressReport-Ansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen. Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.

<div>


> [!NOTE]  
> Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fehler</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zum Bestimmen des Fortschrittsberichts. Wird zum Unterscheiden von Fortschrittsberichten desselben Fehlerberichts verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID für den Fehlerbericht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="even">
<td><p><strong>Anwendung</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Zusätzliche Fehlerinformationen.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

