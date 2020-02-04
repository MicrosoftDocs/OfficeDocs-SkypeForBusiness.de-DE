---
title: Konfigurieren von KDS- (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Konfigurieren der Einstellungen für die Anrufdetailaufzeichnung und die Qualität der Benutzerfreundlichkeit in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Nachdem Sie einen Überwachungsspeicher mit einem Front-End-Pool verknüpft haben, Einrichten des überwachungsspeichers und anschließendes Installieren und Konfigurieren von SQL Server Reporting Services-und Überwachungsberichten können Sie die Anruf Detail Aufzeichnung (CDR) und die Quality of Experience (QoE) verwalten. Überwachen mithilfe der lync Server-Verwaltungsshell. Cmdlets der lync Server-Verwaltungsshell ermöglichen es Ihnen, die CDR-und/oder QoE-Überwachung für eine bestimmte Website oder für die gesamte lync Server-Bereitstellung zu aktivieren und zu deaktivieren. Dies kann mit einem einfachen Befehl erfolgen:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Wenn Sie Microsoft lync Server 2013 installieren, können Sie auch eine vordefinierte Sammlung globaler Konfigurationseinstellungen für CDR und QoE installieren. In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eigenschaft</th>
<th>Beschreibung</th>
<th>Standardwert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Gibt an, ob KDS aktiviert ist. Bei „True“ werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</p></td>
<td><p>Wahr</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf „True“ werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften „KeepCallDetailForDays“ (KDS-Datensätze) und „KeepErrorReportForDays“ (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf „False“ werden KDS-Einträge nie gelöscht.</p></td>
<td><p>Wahr</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</p>
<p>„KeepCallDetailForDays“ kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.</p></td>
<td><p>60 Tage</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Gibt an, wie viele Tage CdR-Fehlerberichte aufbewahrt werden. Alle Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen wie Microsoft lync 2013 hochgeladen wurden.</p>
<p>Sie können diese Eigenschaft auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (etwa 7 Jahre) festlegen.</p></td>
<td><p>60 Tage</p></td>
</tr>
</tbody>
</table>


Entsprechend werden in dieser Tabelle Standardwerte für ausgewählte QoE-Einstellungen aufgeführt:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eigenschaft</th>
<th>Beschreibung</th>
<th>Standardwert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf „True“ werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</p></td>
<td><p>Wahr</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf „True“ festgelegt ist, werden die Einträge nach der über die Eigenschaft „KeepQoEDataForDays“ angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf „False“ werden QoE-Datensätze nie gelöscht.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</p>
<p>„KeepCallDetailForDays“ kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.</p></td>
<td><p>60 Tage</p></td>
</tr>
</tbody>
</table>


Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets „Set-CsCdrConfiguration“ und „Set-CsQoEConfiguration“ verwenden. Mit diesem Befehl (der in der lync Server-Verwaltungsshell ausgeführt wird) wird beispielsweise die CDR-Überwachung im globalen Bereich deaktiviert. Dies erfolgt durch Festlegen der EnableCDR-Eigenschaft auf "false" ($false):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert. Wenn Sie die lync Server-Verwaltungsshell zum Deaktivieren der CDR-oder QoE-Überwachung verwenden, müssen Sie lync Server vorübergehend nicht mehr für das Sammeln und Archivieren von Überwachungsdaten verwenden. Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft „EnableCDR“ wieder auf „True“ ($True) festlegen:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Neben den globalen Einstellungen können KDS- und QoE-Konfigurationseinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.

Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Wenn Sie weitere Informationen wünschen, geben Sie in der lync Server-Verwaltungsshell die folgenden Befehle ein:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

