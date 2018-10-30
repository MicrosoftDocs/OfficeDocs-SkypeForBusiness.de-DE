---
title: 'Anforderungen für die Sicherung und Wiederherstellung: Tools und Berechtigungen'
TOCTitle: 'Anforderungen für die Sicherung und Wiederherstellung: Tools und Berechtigungen'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202171(v=OCS.15)
ms:contentKeyID: 52056321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für die Sicherung und Wiederherstellung: Tools und Berechtigungen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieses Thema enthält Informationen zu den Tools, die Sie zum Sichern und Wiederherstellen von Lync Server 2013 verwenden können, zu den erforderlichen Berechtigungen sowie dazu, ob die Befehle remote oder lokal ausgeführt werden. Insbesondere werden die mit Lync Server bereitgestellten Tools zum Sichern und Wiederherstellen beschrieben.

## Sicherungen

Verwenden Sie die in der folgenden Tabelle aufgeführten Tools, um Lync Server zu sichern. Alle Befehle, die zum Sichern von Lync Server benötigt werden, können in Skripte integriert und remote ausgeführt werden.

### Tools zum Sichern von Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zu sichern:</th>
<th>Zu verwendendes Tool oder Cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Topologiekonfigurationsdaten (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Daten zum Standortinformationsdienst (E9-1-1) (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppen-Konfigurationsdaten (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dauerhafte Benutzerdaten (Rtcxds.mdf-Datenbank)</p>
<p>Konferenz-IDs</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Archivierungsdatenbank (LcsLog.mdf)</p></li>
<li><p>Überwachungsdatenbank zu Kommunikationsdatensätzen (LcsCDR.mdf)</p></li>
<li><p>QoE-Überwachungsdatenbank (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server-Datenbanktool, z. B. SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Datenbank für beständigen Chat (Mgc.mdf)</p></td>
<td><p>SQL Server-Sicherungsverfahren oder &quot;Export-CsPersistentChatData&quot;. Mit &quot;Export-CsPersistentChatData&quot; werden Daten des beständigen Chat als Datei exportiert.</p></td>
</tr>
<tr class="odd">
<td><p>Alle Dateispeicher: Lync Server-Dateispeicher, Archivdateispeicher</p>
<div>

> [!NOTE]
> Dateien mit dem Namen <STRONG>Meeting.Active</STRONG> sollten nicht gesichert werden. Diese Dateien sind während Besprechungen in Gebrauch und daher gesperrt.


</div></td>
<td><p>Standardtool zur Dateisystemverwaltung, z. B. Robocopy</p></td>
</tr>
</tbody>
</table>


## Wiederherstellung

Verwenden Sie die Tools in der folgenden Tabelle, um Lync Server wiederherzustellen. Alle Befehle, die zum Wiederherstellen von Lync Server benötigt werden, können in Skripte integriert werden. Einige können remote ausgeführt werden, andere jedoch müssen wie in folgender Tabelle angegeben lokal ausgeführt werden.

### Tools zum Wiederherstellen von Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gewünschte Aktion</th>
<th>Zu verwendendes Tool oder Cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Neuen oder bereinigten Computer erstellen</p></td>
<td><ul>
<li><p>Installationssoftware für das Windows-Betriebssystem</p></li>
<li><p>Installationssoftware für den SQL Server</p></li>
<li><p>Snap-In &quot;Certificates Microsoft Management Console“ (MMC), wenn Zertifikate mit einem exportierbaren privaten Schlüssel wiederhergestellt werden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Dateispeicherdaten wiederherstellen</p></td>
<td><p>Standardtool zur Dateisystemverwaltung, z. B. Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Leere Datenbanken wiederherstellen und Berechtigungen für Folgendes festlegen:</p>
<ul>
<li><p>zentralen Verwaltungsspeicher</p></li>
<li><p>Back-End-Server</p></li>
<li><p>Überwachungsdatenbank</p></li>
<li><p>Archivierungsdatenbank</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Wiederherstellen des Active Directory-Domänendienste-Verweises auf zentralen Verwaltungsspeicher</p>
<div>

> [!NOTE]
> Wenn der Dienstverbindungspunkt vorübergehend nicht verfügbar ist, können Sie dieses Cmdlet erneut ausführen.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Topologie- Richtlinien- und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher (Xds.mdf) importieren</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Topologie veröffentlichen und aktivieren</p></td>
<td><p>Topologie-Generator</p>
<p>-oder-</p>
<p>Publish-CsTopology und Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Zuletzt veröffentlichte Topologie aktivieren</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Lync Server-Komponenten erneut installieren</p></td>
<td><p>Lync Server-Setup</p>
<div>

> [!NOTE]
> Befindet sich im Lync Server-Installationsordner oder auf dem Installationsdatenträger unter "\setup\amd64\Setup.exe".


</div></td>
</tr>
<tr class="odd">
<td><p>Standort-Informationsdaten wiederherstellen (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dauerhafte Benutzerdaten wiederherstellen (Rtcxds.mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppen-Konfigurationsdaten wiederherstellen (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]
> Wenn die Konfiguration in einem neu bereitgestellten Pool wiederhergestellt wird, in dessen Datenbank sich keine Reaktionsgruppendaten befinden, sollte Sie die Option "–OverwriteOwner" verwenden. Verwenden Sie die Option auch dann, wenn die Wiederherstellungsdaten sich in einem Pool mit demselben vollqualifizierten Domänennamen (FQDN) befindet. Andernfalls schlägt der Import fehl, da die Kontaktobjekte der Reaktionsgruppen bereits in Active&nbsp;Directory vorhanden sind.


</div></td>
</tr>
<tr class="even">
<td><p>Folgende Datenbanken wiederherstellen:</p>
<ul>
<li><p>Archivierungsdatenbank (LcsLog.mdf)</p></li>
<li><p>Überwachungsdatenbanken: Kommunikationsdatensatz-Datenbank (LcsCDR.mdf) und QoE-Datenbank (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL-Serverdatenbank-Verwaltungstools</p></td>
</tr>
<tr class="odd">
<td><p>Datenbank für beständigen Chat (Mgs.mdf)</p></td>
<td><p>SQL Server-Wiederherstellungsverfahren oder &quot;Import-CsPersistentChatData&quot;. Sie können &quot;Import-CsPersistentChatData&quot; mit einer von &quot;Export-CsPersistentChatData&quot; erstellten Datei verwenden, und die Daten werden in die Datenbank für beständigen Chat importiert.</p></td>
</tr>
</tbody>
</table>


## Erforderliche Berechtigungen

Benutzer müssen Mitglied der Gruppe **RTCUniversalServerAdmins** sein, um alle in diesem Thema beschriebenen Befehle ausführen zu können. Die meisten Sicherungs- und Wiederherstellungsbefehle unterstützen keine rollenbasierte Zugriffssteuerung (RBAC). Die Cmdlets des beständigen Chats "Export-CsPersistentChatData" und "Import-CsPersistentChatData" stellen zwei Ausnahmen dar, die von einem Benutzer ausgeführt werden müssen, der Mitglied der Gruppe "CsPersistentChatAdministrator" ist. Zum Ausführen des Lync Server-Bereitstellungs-Assistenten muss der Benutzer auch Mitglied der lokalen Administratorgruppe sein.

