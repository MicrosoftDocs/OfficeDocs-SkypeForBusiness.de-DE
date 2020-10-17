---
title: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Tools und Berechtigungen'
description: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Tools und Berechtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553467"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-17_

In diesem Thema werden die Tools beschrieben, die Sie zum Sichern und Wiederherstellen von lync Server 2013, den benötigten Berechtigungen und zum Remote-oder lokalen Ausführen von Befehlen verwenden können. Dieses Thema konzentriert sich insbesondere auf Tools, die mit lync Server für Sicherung und Wiederherstellung bereitgestellt werden.

<div>

## <a name="backups"></a>Sicherungen

Verwenden Sie die in der folgenden Tabelle aufgeführten Tools, um lync Server zu sichern. Alle Befehle, die Sie zum Sichern von lync Server benötigen, können mit einem Skript erstellt werden und können Remote ausgeführt werden.

### <a name="tools-for-backing-up-lync-server"></a>Tools zum Sichern von lync Server

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
<td><p>Persistente Benutzerdaten ("rtcxds". mdf-Datenbank)</p>
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
<td><p>Datenbank für beständigen Chat (MGC. mdf)</p></td>
<td><p>SQL Server Sicherungsverfahren oder Export-CsPersistentChatData. Export-CsPersistentChatData exportiert persistent Chat-Daten als Datei.</p></td>
</tr>
<tr class="odd">
<td><p>Alle Dateispeicher: lync Server Dateispeicher, archivieren des Dateispeichers</p>
<div>

> [!NOTE]  
> Dateien mit dem Namen <STRONG>Meeting.Active</STRONG> sollten nicht gesichert werden. Diese Dateien sind während Besprechungen in Gebrauch und daher gesperrt.


</div></td>
<td><p>Standard mäßiges Dateisystem-Verwaltungstool wie Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Wiederherstellung

Verwenden Sie die in der folgenden Tabelle aufgeführten Tools, um lync Server wiederherzustellen. Alle Befehle, die Sie zum Wiederherstellen von lync Server benötigen, können als Skript erstellt werden. Einige können Remote ausgeführt werden, andere müssen jedoch wie in der folgenden Tabelle angegeben lokal ausgeführt werden.

### <a name="tools-for-restoring-lync-server"></a>Tools zum Wiederherstellen lync Server

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
<li><p>Snap-In "Certificates Microsoft Management Console“ (MMC), wenn Zertifikate mit einem exportierbaren privaten Schlüssel wiederhergestellt werden.</p></li>
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
<td><p>Wiederherstellen des Active Directory-Domänendienste Zeigers auf den zentralen Verwaltungsspeicher</p>
<div>

> [!NOTE]  
> Wenn der Dienstverbindungspunkt vorübergehend nicht verfügbar ist, können Sie dieses Cmdlet erneut ausführen.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importieren der Topologie-, Richtlinien-und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher (XDS. mdf)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Veröffentlichen und Aktivieren der Topologie</p></td>
<td><p>Topologie-Generator</p>
<p>oder</p>
<p>Publish-CsTopology und Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Zuletzt veröffentlichte Topologie aktivieren</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Neuinstallieren lync Server Komponenten</p></td>
<td><p>Lync Server-Setup</p>
<div>

> [!NOTE]  
> Befindet sich im lync Server Installationsordner oder auf dem Datenträger unter \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Standort-Informationsdaten wiederherstellen (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Wiederherstellen persistenter Benutzerdaten ("rtcxds". mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppen-Konfigurationsdaten wiederherstellen (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Wenn die Konfiguration in einem neu bereitgestellten Pool ohne Reaktionsgruppen Daten in der Datenbank wiederhergestellt wird, sollten Sie die Option – OverwriteOwner verwenden. Verwenden Sie diese Option, selbst wenn sich die wiederherzustellenden Daten in einem Pool mit dem gleichen vollqualifizierten Domänennamen (FQDN) befinden. Andernfalls wird der Import aufgrund der Kontaktobjekte zu den bereits in Active Directory vorhandenen Reaktionsgruppen nicht erfolgreich ausgeführt.


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
<td><p>Datenbank für beständigen Chat (MGS. mdf)</p></td>
<td><p>SQL Server Wiederherstellungsverfahren oder Import-CsPersistentChatData. Sie können Import-CsPersistentChatData mit einer Datei verwenden, die von Export-CsPersistentChatData erstellt wurde, und die Daten werden in die Datenbank für beständigen Chat importiert.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Benutzer müssen ein Mitglied der **RTCUniversalServerAdmins** -Gruppe sein, um alle in diesem Thema beschriebenen Befehle ausführen zu können. Die meisten Sicherungs-und Wiederherstellungsbefehle unterstützen die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) nicht. Zwei Ausnahmen sind die Cmdlets für beständigen Chat Export-CsPersistentChatData und Import-CsPersistentChatData, die von einem Benutzer ausgeführt werden müssen, der Mitglied der "cspersistentchatadministrator"-Gruppe ist. Zum Ausführen des lync Server-Bereitstellungs-Assistenten muss ein Benutzer auch Mitglied der lokalen Administratoren-Gruppe sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

