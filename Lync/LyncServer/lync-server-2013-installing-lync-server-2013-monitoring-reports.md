---
title: 'Lync Server 2013: Installieren von lync Server 2013-Überwachungsberichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad28507f5b0da1758c2e29b9907bd017f922f692
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498542"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a>Installieren von Lync Server 2013-Überwachungsberichten

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-02-27_

Microsoft lync Server 2013 Überwachungsberichte bieten Ihnen eine Fülle von Informationen über die Qualität und Quantität der Kommunikationssitzungen, die in Ihrer Organisation stattfinden. Überwachungsberichte werden jedoch nicht automatisch installiert, wenn Sie lync Server 2013 installieren; Stattdessen müssen Sie Überwachungsberichte separat installieren und erst, nachdem lync Server auf dem Computer installiert wurde.

<div>


> [!NOTE]  
> Es empfiehlt sich, die Überwachungsberichte auf demselben Computer zu intstallieren, auf dem auch die Überwachungsdatenbank installiert ist. Somit wird die Zuweisung von Zugriffsberechtigungen für die Berichte vereinfacht: wenn die Überwachungsberichte auf dem Computer installiert sind, der auch als Host für den Überwachungsspeicher fungiert, müssen Sie keine Berechtigungen zuweisen, die einer Datenbank auf dem Computer gestatten, mit Reporting Services zu interagieren, wenn diese auf einem zweiten Computer ausgeführt werden.



</div>

Lync Server Überwachungsberichte umfassen mehr als 30 Berichte, die detaillierte Informationen zu Konferenzen, Peer-zu-Peer-Sofortnachrichtensitzungen, Benutzerregistrierungen, Reaktionsgruppenanwendung und vielem mehr bereitstellen sollen. Für die 2013-Version enthalten lync Server-Überwachungsberichte eine Reihe von Verbesserungen:

  - **Neue Berichte zur Sprachqualität**. Diese neuen Berichte enthalten den [Bericht über die Medienqualität in lync Server 2013](lync-server-2013-media-quality-comparison-report.md), der die Qualität zwischen verschiedenen Anruftypen vergleicht (beispielsweise zwischen verkabelten anrufen und drahtlosen anrufen); und den [Bericht über die Konferenzbeitritts Zeit in lync Server 2013](lync-server-2013-conference-join-time-report.md), der Informationen über die Zeitdauer bereitstellt, für die Benutzer an einer Konferenz teilnehmen müssen.

  - **Verbesserte Berichte zur Analyse und Problembehebung bei Video- und Anwendungsfreigabesitzungen.** Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) bietet eine Möglichkeit zum Analysieren von Video-und Anwendungsfreigabe aufrufen, während der Bericht über die [Serverleistung in lync Server 2013](lync-server-2013-server-performance-report.md) die Leistung von Servern detailliert erläutert, die diese Anrufe generieren. Die Metriken für die Video-und Anwendungsfreigabe werden jetzt auch vom [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) und dem [Konferenz Detailbericht in lync Server 2013](lync-server-2013-conference-detail-report.md)gemeldet.

  - **Verbesserte Berichtsleistung**. Dies umfasst kürzere Reaktions- und Datenabrufzeiten, also auch eine schnellere und einfachere Navigation in den Berichten.

Weitere Informationen erhalten Sie in der Dokumentation zu den Überwachungsberichten.

<div>


> [!NOTE]  
> Ein weiterer neuer Bericht – QoE-Anruf Detail-Unterbericht – ist in lync Server 2013 enthalten. Dieser Bericht dient jedoch in erster Linie der internen Verwendung und ist nicht für den direkten Zugriff vorgesehen.



</div>

Es gibt zwei Möglichkeiten zum Installieren von lync Server-Überwachungsberichten: Sie können den lync Server-Bereitstellungs-Assistenten verwenden oder ein Windows PowerShell-Skript verwenden, das in den lync Server 2013 Installationsdateien enthalten ist. Unabhängig davon, für welche Installationsmethode Sie sich entscheiden, müssen Sie zunächst Folgendes sicherstellen:

  - Sie sind dazu berechtigt, einem Benutzerkonto in der Überwachungsdatenbank eine Datenbankrolle hinzuzufügen.

  - Sie haben die Rolle "Content Manager" in SQL Server Reporting Services. Diese Rolle berechtigt Sie dazu, Berichte in SQL Server Reporting Services bereitzustellen.

Führen Sie folgende Schritte durch, um die Überwachungsberichte mithilfe des Bereitstellungs-Assistenten zu installieren:

1.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.

2.  Im Bereitstellungs-Assistenten klicken Sie auf **Überwachungsberichte bereitstellen**, um den Assistenten für die Bereitstellung der Überwachungsberichte zu starten.

3.  Stellen Sie im Assistenten für die Bereitstellung der Überwachungsberichte auf der Seite **Überwachungsdatenbank angeben** sicher, dass der vollqualifizierte Domänenname des als Host für Ihren Überwachungsspeicher fungierenden Computers in der Dropdownliste **Überwachungsdatenbank** angezeigt wird. (Sollten Sie über mehrere Überwachungsspeicher verfügen, müssen Sie den entsprechenden Server in der Dropdownliste auswählen.) Stellen Sie sicher, dass die richtige SQL-Serverinstanz im Feld **SQL Server Reporting Services-Instanz (SSRS)** angezeigt wird (z. B. **atl-sql-001.litwareinc.com/archinst**) und klicken Sie anschließend auf **Weiter**.

4.  Geben Sie auf der Seite **Anmeldeinformationen angeben** im Feld **Benutzername** den Domänennamen und den Benutzernamen des Kontos ein, das beim Zugriff auf die Überwachungsberichte verwendet werden soll (beispielsweise **litwareinc \\ kenmyer**). Wenn Sie dieses Format (Domänen \\ Benutzername) nicht verwenden, wird ein Fehler auftreten.
    
    Geben Sie das Kennwort in das Feld **Kennwort** ein, und klicken Sie auf **Weiter**. Beachten Sie, dass für dieses Konto keine besonderen Rechte erforderlich sind. Dem Konto werden automatisch die erforderlichen Anmelde-und Datenbankberechtigungen erteilt, wenn das Setup abgeschlossen ist.

5.  Geben Sie auf der Seite **Gruppe mit Lesezugriff angeben** den Namen einer Sicherheitsgruppe an, der der Lesezugriff auf die SQL Server Reporting Services im Benutzergruppenfeld gewährt wird. Wenn Sie beispielsweise einen Lesezugriff auf die Berichte für Administratoren erteilen möchten, geben Sie **RTCUniversalReadOnlyAdmins** ein. Klicken Sie auf **Weiter**.

6.  Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.

Überwachungsberichte können auch über die lync Server-Verwaltungsshell installiert werden, indem Sie das Skript DeployReports.ps1 ausführen; Dieses Windows PowerShell Skript finden Sie auf der lync Server Installationsmedien im \\ \\ Ordner Setup ReportingSetup. Um die Überwachungsdienste mithilfe von "DeployReports.ps1" zu installieren, geben Sie einen ähnlichen Befehl wie den folgenden an der Verwaltungsshell-Eingabeaufforderung ein:

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

Die im vorstehenden Befehl verwendeten Parameter werden in der folgenden Tabelle beschrieben:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametername</th>
<th>Erforderlich</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>Ja</p></td>
<td><p>Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird. Zum Beispiel</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>Dieses Konto muss über die zuvor angegebenen Berechtigungen für SQL Server und SQL Server Reporting Services verfügen, damit das Skript nicht fehlschlägt.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>Ja</p></td>
<td><p>Kennwort für das Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>Nein</p></td>
<td><p>Domäne oder lokale Sicherheitsgruppe, deren Mitglieder den Lesezugriff für die Überwachungsberichte erhalten. Beachten Sie, dass das Skript fehlschlägt, wenn die angegebene Gruppe nicht vorhanden ist. Falls Sie diese Berechtigungen später wieder entziehen möchten oder wenn Sie sich dafür entscheiden, anderen Benutzern oder Gruppen Zugriffsberechtigungen zu erteilen, können Sie dies mithilfe des Berichts-Managers der SQL Service Reporting Services tun.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>Nein</p></td>
<td><p>SQL Server-Instanz, die als Host für den Berichtsdienst fungiert. Die Berichtsinstanz muss unter Verwendung des vollqualifizierten Domänennamens des Berichtsservers angegeben werden. Beispiel:</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>Falls dieser Parameter nicht enthalten ist, nimmt das Skript an, dass die Berichtsdienste von derselben SQL Server-Instanz gehostet werden, die auch als Host für die Überwachungsdatenbank dient.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>Nein</p></td>
<td><p>Dienstidentität für die Überwachungsdatenbank. Sie können die Identitäten für Ihre Überwachungsdatenbanken durch Ausführung des folgenden Befehls zurückgeben:</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


Nachdem die Überwachungsberichte installiert wurden, müssen Sie das Set-CsReportingConfiguration-Cmdlet verwenden, um die URL zu konfigurieren, die für den Zugriff auf diese Berichte verwendet wird. Diese Aufgabe kann aus dem lync Server-Verwaltungsshell ausgeführt werden, indem Sie den folgenden Windows PowerShell-Befehl ausführen. Beachten Sie, dass es empfohlen wird, aber nicht erforderlich ist, dass Sie beim Konfigurieren der Berichts-URL das HTTPS-Protokoll verwenden:

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

Im vorangehenden Befehl sollte die ReportingUrl-Eigenschaft auf die von SQL Server 2008 R2 Reporting Services verwendete Berichts-Manager-URL festgelegt sein. Führen Sie zur Ermittlung der Berichts-Manager-URL folgende Schritte auf dem Computer durch, auf dem SQL Server Reporting Services installiert wurde:

1.  Klicken Sie auf "Start", "Alle Programme", "Microsoft SQL Server 2008 R2", "Konfigurationstools" und dann auf "Konfigurations-Manager für Reporting Services".

2.  Vergewissern Sie sich, dass im Dialogfeld "Konfigurationsverbindung für Reporting Services" der Name des Reporting Services-Computers im Feld "Servername" angezeigt wird. Wählen Sie die SQL Server-Instanz in der Dropdownliste "Berichtsserverinstanz" aus, und klicken Sie dann auf "Verbinden".

3.  Klicken Sie unter "Konfigurations-Manager für Reporting Services" auf  "Berichts-Manager-URL". Im  Bereich "Berichts-Manager-URL"sollten mehrere URLs angezeigt werden. Sie können jede dieser URLs als URL für die Berichtsfunktion verwenden. Es sei jedoch nochmals darauf hingewiesen, dass für die ReportingUrl das HTTPS-Protokoll empfohlen wird.

Wenn Sie eine Spiegeldatenbank für Ihre Überwachungsdatenbank eingerichtet haben, müssen Sie auch die Überwachungsberichte der Spiegeldatenbank zuordnen. Weitere Informationen finden Sie im Artikel [Zuordnen von Überwachungsberichten mit einer Spiegeldatenbank in lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .

</div>

<span> </span>

</div>

</div>

</div>

