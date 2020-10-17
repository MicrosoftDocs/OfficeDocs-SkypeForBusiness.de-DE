---
title: 'Lync Server 2013: Arbeitsblätter zur Sicherung und Wiederherstellung'
description: 'Lync Server 2013: Arbeitsblätter zur Sicherung und Wiederherstellung.'
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
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552317"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Arbeitsblätter zur Sicherung und Wiederherstellung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern. Sie können die hier dargestellten Arbeitsblätter verwenden, um Sie bei der Dokumentation dieser Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu unterstützen.

Verwenden Sie die folgenden Arbeitsblätter, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Datenbankinformationen, Dateispeicher und Einstellungen für einen lync Server Pool oder Standard Edition-Server benötigen. Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.

<div>


> [!NOTE]  
> In den Arbeitsblättern in diesem Abschnitt werden nur die Informationen behandelt, die erforderlich sind, um die Daten und Einstellungen von lync Server Datenbanken und Servern wiederherzustellen. Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum Neuinstallieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Arbeitsblatt "Datenbanksicherung und-Wiederherstellung"

Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen lync Server Datenbanken benötigen.

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
<th>Database</th>
<th>Server Name (FQDN)</th>
<th>Sicherungszeitplan</th>
<th>Datenbanksicherungstool</th>
<th>Sicherungssätze</th>
<th>Sicherungsziel</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-csuserdata "-</strong> Cmdlet</p></td>
<td><p>Name</p>
<p>Ablauf</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>LcsLog-Datenbank (Standardname) auf Archivierungsdatenbank Server</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Name</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>LcsCdr-Datenbank auf Überwachungsdatenbank Server für Anruf Detaildatensätze (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Name</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics-Datenbank auf Überwachungsdatenbank Server für QoE-Daten (Quality of Experience)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server-Verwaltungstool</p></td>
<td><p>Name</p>
<p>Ablauf</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Datenbank für beständigen Chat</p></td>
<td></td>
<td></td>
<td><p>SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</p></td>
<td><p>Name</p>
<p>Ablauf</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:

  - RTCDyn. Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.

  - RTCAb. Die Adressbuchdatenbank wird in Active Directory-Domänendienste automatisch aus der globalen Adressliste (GAL) neu erstellt.

  - Rgsdyn. Die Daten der transienten Reaktionsgruppen Dienste in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.

  - Cpsdyn. Die dynamischen Informationen für den Anwendung zum Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.

  - MgcComp. Die Kompatibilitätsdatenbank für den beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Arbeitsblatt Dateispeicher Sicherung und Wiederherstellung

Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen. Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, die Erfüllung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppen-, Anruf Park-und Ankündigungs Anwendungen.

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
<th>Sicherungsziel</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server Dateispeicher</p></td>
<td></td>
<td></td>
<td><p>Standard Sicherungstool wie Robocopy</p></td>
<td><p>Auf dem Dateiserver für Enterprise Edition. Standard Edition für die Standard Edition-Bereitstellung. Normalerweise eine pro Website.</p></td>
<td></td>
<td><p>Dateien mit dem Namen <strong>Meeting.Active</strong> sollten nicht gesichert werden. Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Arbeitsblatt "Einstellungen sichern und Wiederherstellen"

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
<th>Database</th>
<th>Server Name (FQDN)</th>
<th>Sicherungszeitplan</th>
<th>Sicherungstool</th>
<th>Name der Konfigurationsdatei (XML)</th>
<th>Sicherungsspeicherort</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS-Datenbank im zentralen Verwaltungsspeicher für die Topologie-Konfiguration (Global)</p></td>
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
<td><p>RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration von Reaktionsgruppen (Pool)</p></td>
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

