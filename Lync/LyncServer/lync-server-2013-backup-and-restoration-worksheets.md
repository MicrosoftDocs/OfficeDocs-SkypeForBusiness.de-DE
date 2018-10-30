---
title: Arbeitsblätter zur Sicherung und Wiederherstellung
TOCTitle: Arbeitsblätter zur Sicherung und Wiederherstellung
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202169(v=OCS.15)
ms:contentKeyID: 52056308
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Arbeitsblätter zur Sicherung und Wiederherstellung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Sicherungs- und Wiederherstellungsplan für Ihre Organisation sollte Informationen dazu enthalten, wie und wann Daten und Einstellungen gesichert werden. Sie können die hier vorgestellten Arbeitsblätter verwenden, um diese Informationen für Ihre Bereitstellung und die Sicherungs- und Wiederherstellungsanforderungen Ihrer Organisation zu dokumentieren.

Verwenden Sie die folgenden Arbeitsblätter zum Aufzeichnen der erforderlichen Informationen zum Sichern und Wiederherstellen der Datenbank, des Dateispeicher und der Einstellungsinformationen für einen Lync Server-Pool oder Standard Edition-Server. Bewahren Sie mindestens eine Kopie dieser Arbeitsblätter an einem sicheren Speicherort auf, damit leicht darauf zugegriffen werden kann, wenn Lync Server wiederhergestellt werden muss.


> [!NOTE]
> Die Arbeitsblätter in diesem Abschnitt enthalten nur die erforderlichen Informationen zum Wiederherstellen der Daten und Einstellungen von Lync Server-Datenbanken und Servern. Wenn Sie weitere Wiederherstellungsinformationen dokumentieren müssen, z.&nbsp;B. Informationen zur Wiederherstellung von Betriebssystemen und anderer Software, verwenden Sie für diese Anforderungen die Bereitstellungspläne und Sicherungs- und Wiederherstellungspläne Ihrer Organisation.



## Arbeitsblatt zur Sicherung und Wiederherstellung von Datenbanken

Verwenden Sie die folgende Tabelle zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen von Lync Server-Datenbanken benötigen.

### Datenbankinformationen zum Sichern und Wiederherstellen

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenbank</th>
<th>Servername (FQDN)</th>
<th>Sicherungsplan</th>
<th>Datenbanksicherungstool</th>
<th>Sicherungssatz</th>
<th>Datensicherungsziel</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong>-Cmdlet</p></td>
<td><p>Name:</p>
<p>Ablauf:</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Datenbank &quot;LcsLog&quot; (Standardname) auf Archivierungsdatenbank-Server</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL-Serververwaltungstool</p></td>
<td><p>Name:</p>
<p>Ablauf:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Datenbank &quot;LcsCdr&quot; auf Überwachungsdatenbank-Server für Kommunikationsdatensätze (KDS)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL-Serververwaltungstool</p></td>
<td><p>Name:</p>
<p>Ablauf:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Datenbank &quot;QoEMetrics&quot; auf Überwachungsdatenbank-Server für QoE-Daten (Quality of Experience)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL-Serververwaltungstool</p></td>
<td><p>Name:</p>
<p>Ablauf:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Datenbank für beständigen Chat</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>SQL-Serververwaltungstool oder das Cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Name:</p>
<p>Ablauf:</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


Folgende Datenbanken erfordern keine Sicherung oder Wiederherstellung:

  - Rtcdyn. Die temporären Benutzerdaten in dieser Datenbank sind nicht für die Wiederherstellung eines Diensts erforderlich.

  - Rtcab. Die Adressbuchdatenbank wird aus der globalen Adressliste (GAL) in Active Directory-Domänendienste automatisch neu erstellt.

  - Rgsdyn. Die temporären Daten des Reaktionsgruppendiensts in dieser Datenbank sind nicht für die Wiederherstellung eines Diensts erforderlich.

  - Cpsdyn. Die dynamischen Informationen für die Anwendung zum Parken von Anrufen sind nicht für die Wiederherstellung eines Diensts erforderlich.

  - MgcComp. Die Kompatibilitätsdatenbank für Beständiger Chat ist zum Wiederherstellen des Diensts nicht erforderlich.

## Arbeitsblatt zur Sicherung und Wiederherstellung von Dateispeichern

Verwenden Sie die folgende Tabelle zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen. Dateispeicher enthalten Daten wie Metadaten zu Besprechungsinhalten, Protokolle für Besprechungskompatibilität, Geräteaktualisierungsprotokolle und Audiodateien für die Reaktionsgruppe-, Parken von Anrufen- und Ansageanwendung.

### Dateispeicherinformationen zum Sichern und Wiederherstellen

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Inhalt</th>
<th>Servername (FQDN)</th>
<th>Sicherungsplan</th>
<th>Dateisystem-Sicherungstool</th>
<th>zu sichernde Dateifreigabe *</th>
<th>Datensicherungsziel</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server-Dateispeicher</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>Standardsicherungstool, z. B. Robocopy</p></td>
<td><p>Auf dem Dateiserver für die Enterprise Edition. Standardmäßig auf der Standard Edition für die Bereitstellung der Standard Edition. In der Regel eine pro Website.</p></td>
<td><p></p></td>
<td><p>Dateien mit dem Namen <strong>Meeting.Active</strong> sollten nicht gesichert werden. Diese Dateien sind während Besprechungen in Gebrauch und daher gesperrt.</p></td>
</tr>
</tbody>
</table>


## Arbeitsblatt zur Sicherung und Wiederherstellung von Einstellungen

Verwenden Sie die folgende Tabelle zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.

### Einstellungsinformationen zum Sichern und Wiederherstellen

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenbank</th>
<th>Servername (FQDN)</th>
<th>Sicherungsplan</th>
<th>Sicherungstool</th>
<th>Name der Konfigurationsdatei (.xml)</th>
<th>Sicherungsspeicherort</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datenbank &quot;Xds&quot; in zentralen Verwaltungsspeicher für Topologiekonfiguration (global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong>-Cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Datenbank &quot;Lis&quot; in zentralen Verwaltungsspeicher für E9-1-1-Speicherortinformationen (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong>-Cmdlet</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Datenbank &quot;RgsConfig&quot; auf Back-End-Server für Reaktionsgruppe-Konfiguration (Pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> -Cmdlet</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>

