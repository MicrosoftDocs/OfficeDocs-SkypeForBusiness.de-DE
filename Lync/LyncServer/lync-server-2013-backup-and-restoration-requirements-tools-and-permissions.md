---
title: 'Lync Server 2013: Sicherungs-und Wiederherstellungsanforderungen: Tools und Berechtigungen'
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
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

In diesem Thema werden die Tools aufgeführt, die Sie zum Sichern und Wiederherstellen von lync Server 2013, den erforderlichen Berechtigungen und zum Remote-oder lokalen Ausführen von Befehlen verwenden können. Insbesondere konzentriert sich dieses Thema auf Tools, die mit lync Server für Sicherung und Wiederherstellung bereitgestellt werden.

<div>

## <a name="backups"></a>Sicherungen

Zum Sichern von lync Server verwenden Sie die in der folgenden Tabelle angegebenen Tools. Alle Befehle, die Sie zum Sichern von lync Server benötigen, können skriptiert werden und können Remote ausgeführt werden.

### <a name="tools-for-backing-up-lync-server"></a>Tools zum Sichern von lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>So sichern Sie Folgendes:</th>
<th>Verwenden Sie dieses Tool oder Cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Topologie-Konfigurationsdaten (XDS. mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Standortinformationsdienst (E9-1-1)-Daten (LIS. mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Konfigurationsdaten der Reaktionsgruppe (RgsConfig. mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Beständige Benutzerdaten (Rtcxds. mdf-Datenbank)</p>
<p>Konferenz-IDs</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Archivierungsdatenbank (LcsLog. mdf)</p></li>
<li><p>Überwachungsdatenbank für Anruf Detaildatensätze (LcsCDR. mdf)</p></li>
<li><p>Überwachen der QoE-Datenbank (Datenbank QoEMetrics werden. mdf)</p></li>
</ul></td>
<td><p>SQL Server-Datenbanktool wie SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Datenbank für beständigen Chat (MGC. mdf)</p></td>
<td><p>SQL Server-Sicherungsverfahren oder Export-CsPersistentChatData. Export-CsPersistentChatData exportiert persistente Chat-Daten als Datei.</p></td>
</tr>
<tr class="odd">
<td><p>Alle Dateispeicher: lync Server-Dateispeicher, Archivierungsdatei Speicher</p>
<div>

> [!NOTE]  
> Dateien mit dem Namen " <STRONG>Meeting. Active</STRONG> " sollten nicht gesichert werden. Diese Dateien werden während einer Besprechung verwendet und gesperrt.


</div></td>
<td><p>Standard mäßiges Dateisystem-Verwaltungstool, beispielsweise Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Wiederherstellung

Verwenden Sie zum Wiederherstellen von lync Server die Tools in der folgenden Tabelle. Für alle Befehle, die Sie zum Wiederherstellen von lync Server benötigen, kann ein Skript erstellt werden. Einige können Remote ausgeführt werden, andere müssen jedoch lokal ausgeführt werden, wie in der folgenden Tabelle angegeben.

### <a name="tools-for-restoring-lync-server"></a>Tools zum Wiederherstellen von lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gehen Sie dazu so vor:</th>
<th>Verwenden Sie dieses Tool oder Cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erstellen eines neuen oder sauberen Computers</p></td>
<td><ul>
<li><p>Installationssoftware für Windows-Betriebssysteme</p></li>
<li><p>SQL Server-Installationssoftware</p></li>
<li><p>Zertifikate Microsoft Management Console (MMC)-Snap-in, wenn Zertifikate mit einem exportierbaren privaten Schlüssel wiederhergestellt werden</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Wiederherstellen von dateispeicherdaten</p></td>
<td><p>Standard mäßiges Dateisystem-Verwaltungstool wie Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Erstellen Sie leere Datenbanken neu, und legen Sie Berechtigungen für Folgendes an:</p>
<ul>
<li><p>zentraler Verwaltungsspeicher</p></li>
<li><p>Back-End-Server</p></li>
<li><p>Überwachungsdatenbank</p></li>
<li><p>Archivierungsdatenbank</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Wiederherstellen des Zeigers der Active Directory-Domänendienste auf den zentralen Verwaltungsspeicher</p>
<div>

> [!NOTE]  
> Wenn Sie den Dienstverbindungspunkt zu einem beliebigen Zeitpunkt verloren haben, können Sie dieses Cmdlet erneut ausführen.


</div></td>
<td><p>Satz-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importieren der Topologie, Richtlinien und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher (XDS. mdf)</p></td>
<td><p>Importieren-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Veröffentlichen und Aktivieren der Topologie</p></td>
<td><p>Topologie-Generator</p>
<p>oder</p>
<p>Publish-CsTopology und enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren der letzten veröffentlichten Topologie</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Erneutes Installieren von lync Server-Komponenten</p></td>
<td><p>Lync Server-Setup</p>
<div>

> [!NOTE]  
> Befindet sich im lync Server-Installationsordner oder-Medien unter \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Wiederherstellen von Standortinformationen (E9-1-1)-Daten (LIS. mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Wiederherstellen beständiger Benutzerdaten (Rtcxds. mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Wiederherstellen der Konfigurationsdaten der Reaktionsgruppe (RgsConfig. mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Wenn die Konfiguration in einem neu bereitgestellten Pool wiederhergestellt wird, in dem keine Antwortgruppen Daten in der Datenbank enthalten sind, sollten Sie die Option – OverwriteOwner verwenden. Verwenden Sie diese Option, selbst wenn sich die wiederhergestellten Daten in einem Pool mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) befinden. Andernfalls ist der Import aufgrund der Kontaktobjekte zu den bereits in Active Directory vorhandenen Antwortgruppen nicht erfolgreich.


</div></td>
</tr>
<tr class="even">
<td><p>Stellen Sie die folgenden Datenbanken wieder her:</p>
<ul>
<li><p>Archivierungsdatenbank (LcsLog. mdf)</p></li>
<li><p>Überwachungsdatenbanken: Anruf Detaildatensatz Datenbank (LcsCDR. mdf) und QoE-Datenbank (Datenbank QoEMetrics werden. mdf)</p></li>
</ul></td>
<td><p>SQL Server-Datenbankverwaltungstools</p></td>
</tr>
<tr class="odd">
<td><p>Datenbank für beständigen Chat (MGS. mdf)</p></td>
<td><p>SQL Server-Wiederherstellungsverfahren oder Import-CsPersistentChatData. Sie können Import-CsPersistentChatData mit einer von Export-CsPersistentChatData erstellten Datei verwenden, und die Daten werden in die persistente Chat Datenbank importiert.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Benutzer müssen ein Mitglied der **RTCUniversalServerAdmins** -Gruppe sein, um alle in diesem Thema beschriebenen Befehle ausführen zu können. Die meisten Befehle für die Sicherung und Wiederherstellung unterstützen keine rollenbasierte Zugriffssteuerung. Zwei Ausnahmen sind die Cmdlets für beständigen Chat, Export-CsPersistentChatData und Import-CsPersistentChatData, die von einem Benutzer ausgeführt werden müssen, der ein Mitglied der CsPersistentChatAdministrator-Gruppe ist. Damit Sie den lync Server-Bereitstellungs-Assistenten ausführen können, muss ein Benutzer auch ein Mitglied der lokalen Administratoren-Gruppe sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

