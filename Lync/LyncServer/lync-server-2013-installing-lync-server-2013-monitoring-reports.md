---
title: Installieren von Lync Server 2013-Überwachungsberichten
TOCTitle: Installieren von Lync Server 2013-Überwachungsberichten
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204989(v=OCS.15)
ms:contentKeyID: 49294346
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Lync Server 2013-Überwachungsberichten

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Microsoft Lync Server 2013-Überwachungsberichte bieten Ihnen umfassende Informationen zur Qualität und Quantität der Kommunikationssitzungen, die in Ihrer Organisation stattfinden. Die Überwachungsberichte werden jedoch nicht automatisch installiert, wenn Sie Lync Server 2013 installieren. Sie müssen die Überwachungsberichte separat installieren, nachdem Lync Server auf dem Computer installiert wurde.


> [!NOTE]
> Es empfiehlt sich, die Überwachungsberichte auf demselben Computer zu intstallieren, auf dem auch die Überwachungsdatenbank installiert ist. Somit wird die Zuweisung von Zugriffsberechtigungen für die Berichte vereinfacht: wenn die Überwachungsberichte auf dem Computer installiert sind, der auch als Host für den Überwachungsspeicher fungiert, müssen Sie keine Berechtigungen zuweisen, die einer Datenbank auf dem Computer gestatten, mit Reporting Services zu interagieren, wenn diese auf einem zweiten Computer ausgeführt werden.



Lync Server Die Überwachungsberichte umfassen 30 Berichte, die detaillierte Informationen zu Konferenzen, Peer-zu-Peer-Sofortnachrichtensitzungen, Benutzerregistrierungen, zur Reaktionsgruppenanwendung und vieles mehr bieten. Mit der Version 2013 werden für die Lync Server -Überwachungsberichte eine Reihe von Verbesserungen eingeführt:

  - **Neue Berichte zur Sprachqualität**. Zu diesen neuen Berichten zählen der [Vergleichsbericht über Medienqualität](lync-server-2013-media-quality-comparison-report.md), in dem die Qualität bei verschiedenen Anruftypen verglichen wird (z. B. der Qualitätsunterschied zwischen Anrufen über drahtgebundene Verbindungen und Anrufen über drahtlose Verbindungen), sowie der [Bericht über Konferenzbeitrittszeit](lync-server-2013-conference-join-time-report.md), der Informationen darüber enthält, wie lange es dauert, bis ein Benutzer einer Konferenz beitreten kann.

  - **Verbesserte Berichte zur Analyse und Problembehebung bei Video- und Anwendungsfreigabesitzungen.** Der [Zusammenfassender Bericht über Medienqualität in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) bietet eine Möglichkeit zur Analyse von Video- und Anwendungsfreigabeanrufen, während der [Bericht über Serverleistung in Lync Server 2013](lync-server-2013-server-performance-report.md) die Leistung der Server aufschlüsselt, die diese Anrufe generieren. Video- und Anwendungsfreigabemetriken werden jetzt auch im [Detailbericht über Peer-zu-Peer-Sitzungen in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) und im [Konferenzdetailbericht](lync-server-2013-conference-detail-report.md) erfasst.

  - **Verbesserte Berichtsleistung**. Dies umfasst kürzere Reaktions- und Datenabrufzeiten, also auch eine schnellere und einfachere Navigation in den Berichten.

Weitere Informationen erhalten Sie in der Dokumentation zu den Überwachungsberichten.


> [!NOTE]
> In Lync Server 2013 gibt es einen weiteren neuen Bericht, den QoE Call Detail Subreport- Dieser Bericht dient jedoch in erster Linie internen Zwecken und soll nicht direkt aufgerufen werden.



Für die Installation der Lync Server-Überwachungsberichte gibt es zwei Möglichkeiten: Sie können den Lync Server-Bereitstellungs-Assistenten verwenden oder ein Windows PowerShell-Skript, das in den Lync Server 2013-Installationsdateien enthalten ist. Unabhängig davon, für welche Installationsmethode Sie sich entscheiden, müssen Sie zunächst Folgendes sicherstellen:

  - Sie sind dazu berechtigt, einem Benutzerkonto in der Überwachungsdatenbank eine Datenbankrolle hinzuzufügen.

  - Sie haben die Rolle "Content Manager" in SQL Server Reporting Services. Diese Rolle berechtigt Sie dazu, Berichte in SQL Server Reporting Services bereitzustellen.

Führen Sie folgende Schritte durch, um die Überwachungsberichte mithilfe des Bereitstellungs-Assistenten zu installieren:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Lync Server 2013** und anschließend auf **Lync Server-Bereitstellungs-Assistent**.

2.  Im Bereitstellungs-Assistenten klicken Sie auf **Überwachungsberichte bereitstellen**, um den Assistenten für die Bereitstellung der Überwachungsberichte zu starten.

3.  Stellen Sie im Assistenten für die Bereitstellung der Überwachungsberichte auf der Seite **Überwachungsdatenbank angeben** sicher, dass der vollqualifizierte Domänenname des als Host für Ihren Überwachungsspeicher fungierenden Computers in der Dropdownliste **Überwachungsdatenbank** angezeigt wird. (Sollten Sie über mehrere Überwachungsspeicher verfügen, müssen Sie den entsprechenden Server in der Dropdownliste auswählen.) Stellen Sie sicher, dass die richtige SQL-Serverinstanz im Feld **SQL Server Reporting Services-Instanz (SSRS)** angezeigt wird (z. B. **atl-sql-001.litwareinc.com/archinst**) und klicken Sie anschließend auf **Weiter**.

4.  Geben Sie auf der Seite **Angeben von Anmeldeinformationen** in das Feld **Benutzername** den Domänennamen und Benutzernamen des Kontos ein, das für den Zugriff auf die Überwachungsberichte verwendet werden soll (z. B. **litwareinc\\kenmyer**). Wenn Sie nicht dieses Format (Domäne\\Benutzername) verwenden, tritt ein Fehler auf.
    
    Geben Sie das Kennwort in das Feld **Kennwort** ein, und klicken Sie auf **Weiter**. Für dieses Konto sind keine speziellen Rechte erforderlich. Dem Konto werden die erforderlichen Anmelde- und Datenbankberechtigungen automatisch erteilt, wenn die Einrichtung abgeschlossen wird.

5.  Geben Sie auf der Seite **Gruppe mit Lesezugriff angeben** den Namen einer Sicherheitsgruppe an, der der Lesezugriff auf die SQL Server Reporting Services im Benutzergruppenfeld gewährt wird. Wenn Sie beispielsweise einen Lesezugriff auf die Berichte für Administratoren erteilen möchten, geben Sie **RTCUniversalReadOnlyAdmins** ein. Klicken Sie auf **Weiter**.

6.  Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.

Die Überwachungsberichte können auch über die Lync Server-Verwaltungsshell installiert werden, indem Sie das Skript "DeployReports.ps1" ausführen; dieses Windows PowerShell-Skript befindet sich auf dem Lync Server-Installationsmedium im Ordner "\\Setup\\ReportingSetup". Um die Überwachungsdienste mithilfe von "DeployReports.ps1" zu installieren, geben Sie einen ähnlichen Befehl wie den folgenden an der Verwaltungsshell-Eingabeaufforderung ein:

    D:\Setup\AMD64\Setp\ReportingSetup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

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


Nachdem die Überwachungsberichte installiert wurden, müssen Sie das Set-CsReportingConfiguration-Cmdlet verwenden, um die URL für den Zugriff auf die Berichte zu konfigurieren. Diese Aufgabe kann über die Lync Server-Verwaltungsshell ausgeführt werden. Sie führen dazu den folgenden Windows PowerShell-Befehl aus. Beachten Sie, dass es zwar ratsam, aber nicht erforderlich ist, das HTTPS-Protokoll für die Konfiguration der Berichts-URL zu verwenden:

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

Im vorangehenden Befehl sollte die ReportingUrl-Eigenschaft auf die von SQL Server 2008 R2 Reporting Services verwendete Berichts-Manager-URL festgelegt sein. Führen Sie zur Ermittlung der Berichts-Manager-URL folgende Schritte auf dem Computer durch, auf dem SQL Server Reporting Services installiert wurde:

1.  Klicken Sie auf "Start", "Alle Programme", "Microsoft SQL Server 2008 R2", "Konfigurationstools" und dann auf "Konfigurations-Manager für Reporting Services".

2.  Vergewissern Sie sich, dass im Dialogfeld "Konfigurationsverbindung für Reporting Services" der Name des Reporting Services-Computers im Feld "Servername" angezeigt wird. Wählen Sie die SQL Server-Instanz in der Dropdownliste "Berichtsserverinstanz" aus, und klicken Sie dann auf "Verbinden".

3.  Klicken Sie unter "Konfigurations-Manager für Reporting Services" auf "Berichts-Manager-URL". Im Bereich "Berichts-Manager-URL"sollten mehrere URLs angezeigt werden. Sie können jede dieser URLs als URL für die Berichtsfunktion verwenden. Es sei jedoch nochmals darauf hingewiesen, dass für die ReportingUrl das HTTPS-Protokoll empfohlen wird.

Wenn Sie eine Spiegeldatenbank für Ihre Überwachungsdatenbank eingerichtet haben, müssen Sie auch die Überwachungsberichte mit der Spiegeldatenbank verknüpfen. Weitere Informationen hierzu finden Sie im Artikel [Verknüpfen von Überwachungsberichten mit einer Spiegeldatenbank](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md).

