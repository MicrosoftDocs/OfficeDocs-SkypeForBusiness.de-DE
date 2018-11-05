---
title: Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen
TOCTitle: Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204621(v=OCS.15)
ms:contentKeyID: 49292976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Nachdem Sie einen Überwachungsspeicher einem Front-End-Pool zugeordnet, den Überwachungsspeicher eingerichtet und anschließend SQL Server Reporting Services und Überwachungsberichte installiert und konfiguriert haben, können Sie die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE (Quality of Experience) mithilfe der Lync Server-Verwaltungsshell verwalten. Lync Server-Verwaltungsshell-Cmdlets ermöglichen Ihnen das Aktivieren und Deaktivieren der KDS- und/oder QoE-Überwachung für eine bestimmte Website oder Ihre gesamte Lync Server-Bereitstellung. Dazu ist lediglich ein einfacher Befehl wie der Folgende erforderlich:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Bei der Installation von Microsoft Lync Server 2013 installieren Sie auch eine vordefinierte Auflistung von global Konfigurationseinstellungen für KDS und QoE. In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:


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
<td><p>Gibt an, ob KDS aktiviert ist. Bei &quot;True&quot; werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf &quot;True&quot; werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften &quot;KeepCallDetailForDays&quot; (KDS-Datensätze) und &quot;KeepErrorReportForDays&quot; (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf &quot;False&quot; werden KDS-Einträge nie gelöscht.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</p>
<p>&quot;KeepCallDetailForDays&quot; kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.</p></td>
<td><p>60 Tage</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter sind als angegeben, werden automatisch gelöscht. Fehlerberichte zu Kommunikationsdatensätzen sind Diagnoseberichte, die von Clientanwendungen wie z. B. Microsoft Lync 2013 hochgeladen werden.</p>
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
<td><p>Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf &quot;True&quot; werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf &quot;True&quot; festgelegt ist, werden die Einträge nach der über die Eigenschaft &quot;KeepQoEDataForDays&quot; angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf &quot;False&quot; werden QoE-Datensätze nie gelöscht.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</p>
<p>&quot;KeepCallDetailForDays&quot; kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.</p></td>
<td><p>60 Tage</p></td>
</tr>
</tbody>
</table>


Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets "Set-CsCdrConfiguration" und "Set-CsQoEConfiguration" verwenden. Beispielsweise deaktiviert dieser Befehl (ausgeführt in der Lync Server-Verwaltungsshell) die KDS-Überwachung auf globaler Ebene; dazu wird die Eigenschaft "EnableCDR" auf "False" ($False) festgelegt:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert. Wenn Sie die KDS- oder QoE-Überwachung mithilfe der Lync Server-Verwaltungsshell deaktivieren, müssen Sie lediglich das Sammeln und Archivieren von Überwachungsdaten durch Lync Server anhalten. Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft "EnableCDR" wieder auf "True" ($True) festlegen:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Neben den globalen Einstellungen können KDS- und QoE-Konfigurationeneinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.

Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Geben Sie die folgenden Befehle in der Lync Server-Verwaltungsshell ein, um weitere Informationen zu erhalten:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

