---
title: 'Lync Server 2013: Arbeitsblätter zum Sichern und Wiederherstellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Arbeitsblätter zum Sichern und Wiederherstellen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern. Sie können die hier vorgestellten Arbeitsblätter dazu verwenden, diese Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu dokumentieren.

Verwenden Sie die folgenden Arbeitsblätter zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen von Datenbank-, Dateispeicher-und Einstellungsinformationen für einen lync Server-Pool oder Standard Edition-Server benötigen. Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.

<div>


> [!NOTE]  
> Die Arbeitsblätter in diesem Abschnitt beziehen sich nur auf die Informationen, die erforderlich sind, um die Daten und Einstellungen der lync Server-Datenbanken und-Server wiederherzustellen. Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum erneuten Installieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Arbeitsblatt für Datenbanksicherung und-Wiederherstellung

Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von lync Server-Datenbanken benötigen.

### <a name="database-information-for-backup-and-restoration"></a>Datenbankinformationen für Sicherung und Wiederherstellung

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
<th>Server Name (FQDN)</th>
<th>Sicherungszeitplan</th>
<th>Datenbanksicherungstool</th>
<th>Sicherungssatz</th>
<th>Backup-Ziel</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData-</strong> Cmdlet</p></td>
<td><p>Namen</p>
<p>Ablauf</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>LcsLog (Standardname)-Datenbank auf dem Archivierungsdaten Bankserver</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Namen</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>LcsCdr-Datenbank zum Überwachen des Datenbankservers für Anruf Detaildatensätze (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Namen</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Datenbank QoEMetrics werden-Datenbank zum Überwachen des Datenbankservers für QoE-Daten (Quality of Experience)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Namen</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Datenbank für beständigen Chat</p></td>
<td></td>
<td></td>
<td><p>SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</p></td>
<td><p>Namen</p>
<p>Ablauf</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:

  - RTCDyn. Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.

  - RTCAb. Die Adressbuchdatenbank wird automatisch aus der globalen Adressliste (Global Address List, GAL) in den Active Directory-Domänendiensten neu erstellt.

  - Rgsdyn. Die Daten in dieser Datenbank für transiente Reaktionsgruppen Dienste sind für die Wiederherstellung des Diensts nicht erforderlich.

  - Cpsdyn. Die dynamischen Informationen für die Anwendung für den Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.

  - MgcComp. Die Kompatibilitätsdatenbank für beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Arbeitsblatt zum Sichern und Wiederherstellen von Datei speichern

Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen. Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, Besprechung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppe, den Anruf Park und Ankündigungs Anwendungen.

### <a name="file-store-information-for-backup-and-restoration"></a>Dateispeicher Informationen für Sicherung und Wiederherstellung

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
<th>Server Name (FQDN)</th>
<th>Sicherungszeitplan</th>
<th>Dateisystem-Sicherungstool</th>
<th>Zu sichernde Dateifreigabe *</th>
<th>Backup-Ziel</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server-Dateispeicher</p></td>
<td></td>
<td></td>
<td><p>Standard Sicherungstool wie Robocopy</p></td>
<td><p>Auf Dateiserver für Enterprise Edition. Standardmäßig für die Standard Edition-Bereitstellung. In der Regel eine pro Website.</p></td>
<td></td>
<td><p>Dateien mit dem Namen " <strong>Meeting. Active</strong> " sollten nicht gesichert werden. Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Arbeitsblatt ' Sicherungs-und Wiederherstellungseinstellungen '

Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.

### <a name="settings-information-for-backup-and-restoration"></a>Einstellungsinformationen für Sicherung und Wiederherstellung

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
<th>Server Name (FQDN)</th>
<th>Sicherungszeitplan</th>
<th>Sicherungstool</th>
<th>Konfigurationsdatei-Name (XML)</th>
<th>Sicherungsspeicherort</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS-Datenbank im zentralen Verwaltungsspeicher für Topologie-Konfiguration (Global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration-</strong> Cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>LIS-Datenbank im zentralen Verwaltungsspeicher für E9-1-1-Standortinformationen (Global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration-</strong> Cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration der Reaktionsgruppe (Pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration-</strong> Cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

