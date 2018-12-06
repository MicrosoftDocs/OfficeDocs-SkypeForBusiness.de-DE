---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für Einwahlkonferenzen'
TOCTitle: Prüfliste zur Bereitstellung für Einwahlkonferenzen
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412726(v=OCS.15)
ms:contentKeyID: 49294892
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die für Einwahlkonferenzen erforderlichen Komponenten werden bei der Bereitstellung der Konferenzarbeitsauslastung bereitgestellt. Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder einen Vermittlungsserver sowie ein PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) bereitstellen.

Alle Schritte in der folgenden Tabelle müssen durchgeführt werden, damit Benutzer sich über ein Telefonfestnetz einwählen und an einer Audio/Video-Konferenz teilnehmen können.


> [!NOTE]
> Wenn Sie eine Migration von Office Communications Server 2007 R2 durchführen, müssen Sie vor der Bereitstellung von Einwahlkonferenzen die neusten Updates auf Ihre Office Communications Server 2007 R2-Umgebung anwenden.



### Verfahren zur Bereitstellung von Einwahlkonferenzen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Berechtigungen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Erstellen Sie eine Topologie, die die Konferenzarbeitslast einschließlich eines Vermittlungsservers und PSTN-Gateways umfasst und stellen Sie den Front-End-Pool oder den Standard Edition-Server bereit</strong></p></td>
<td><ol>
<li><p>Führen Sie das Topologie-Generator zum Konfigurieren Ihrer Topologie aus. Wählen Sie beim Konfigurieren der Topologie die Einwahlkonferenzoption aus.</p></li>
<li><p>Veröffentlichen Sie die Topologie und stellen Sie den Front-End-Pool oder den Standard Edition-Server bereit.</p></li>
<li><p>Erstellen Sie bei Bedarf einen eigenständigen Vermittlungsserver und ordnen Sie ihm ein PSTN-Gateway zu.</p>
<div>

> [!NOTE]
> Dieser Schritt ist nur dann erforderlich, wenn Sie Enterprise-VoIP nicht bereitstellen und den Vermittlungsserver nicht mit dem Enterprise Edition- Front-End-Server oder - Standard Edition-Server gemeinsam ausführen. Wenn Sie Enterprise-VoIP bereitstellen, installieren und konfigurieren Sie Vermittlungsserver und PSTN-Gateways im Rahmen der Enterprise-VoIP-Bereitstellung. Wenn Sie den Vermittlungsserver gemeinsam mit einer anderen Rolle ausführen, installieren und konfigurieren Sie den Vermittlungsserver als Teil der Bereitstellung des Front-End-Pools oder des Standard Edition-Servers.


</div></li>
</ol></td>
<td><p>Domänen-Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></li>
<li><p>So erstellen Sie einen eigenständigen Vermittlungsserverpool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013</a>Server pool</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Wähleinstellungen</strong></p></td>
<td><p>Wähleinstellungen sind ein Satz von Rufnummernnormalisierungsregeln, die von einem bestimmten Standort aus gewählte Rufnummern in ein einziges Standardformat (E.164) übersetzen, um die Telefonautorisierung und das Anrufrouting zu ermöglichen. Eine von verschiedenen Standorten aus gewählte Rufnummer kann je nach Wähleinstellungen dem Standort entsprechend in unterschiedliche E.164-Nummern aufgelöst werden. Wenn Sie Enterprise-VoIP bereitstellen, richten Sie Wähleinstellungen im Rahmen dieser Bereitstellung ein und müssen sicherstellen, dass die Wähleinstellungen auch Einwahlkonferenzen umfassen. Falls Sie Enterprise-VoIP nicht bereitstellen, müssen Sie Wähleinstellungen für Einwahlkonferenzen einrichten.</p>
<p>Verwenden Sie zum Einrichten von Wähleinstellungen die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell folgendermaßen:</p>
<ol>
<li><p>Erstellen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl.</p></li>
<li><p>Weisen Sie jedem Pool einen Standardsatz mit Wähleinstellungen zu. Legen Sie die <strong>Region für Einwahlkonferenzen</strong> auf den geografischen Standort fest, für den die Wähleinstellungen gelten. Die Region ordnet die Wähleinstellungen den Zugriffsnummern für die Einwahl zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicherstellen, dass den Wähleinstellungen Regionen zugeordnet werden</strong></p></td>
<td><p>Führen Sie die Cmdlets <strong>Get-CsDialPlan</strong> und <strong>Set-CsDialPlan</strong> aus, um sicherzustellen, dass allen Wähleinstellungen eine Region zugeordnet wird.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Sicherstellen, dass Wählplänen in Lync Server 2013 Regionen zugewiesen wurden</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen oder ändern Sie die Anforderungen an die persönliche Identifikationsnummer (PIN) der Benutzer.</strong></p></td>
<td><p>Verwenden Sie die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell zum Anzeigen oder Ändern der <strong>PIN-Richtlinie</strong> für Konferenzen. Sie können eine PIN-Mindestlänge, eine maximale Anzahl von Anmeldeversuchen, ein PIN-Ablaufdatum und die Zulässigkeit gängiger Muster festlegen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Überprüfen der PIN-Richtlinieneinstellungen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren Sie die Konferenzrichtlinie so, dass Einwahlkonferenzen unterstützt werden.</strong></p></td>
<td><p>Verwenden Sie die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell zum Konfigurieren von Einstellungen der <strong>Konferenzrichtlinie</strong> . Legen Sie folgende Einstellungen fest:</p>
<ul>
<li><p>Die PSTN-Konferenzeinwahl ist aktiviert.</p></li>
<li><p>Benutzer können anonyme Teilnehmer einladen.</p></li>
<li><p>Nicht authentifizierte Benutzer können über ausgehende Telefonverbindungen an einer Konferenz teilnehmen. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Zugriffsnummern für die Einwahl</strong></p></td>
<td><p>Verwenden Sie die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell zum Einrichten von Zugriffsnummern, mit denen Benutzer sich in einer Konferenz einwählen können, und geben Sie die Regionen an, welche die Zugriffsnummer den entsprechenden Wähleinstellungen zuordnen. Die ersten drei Zugriffsnummern für die Region, die durch die Wähleinstellungen des Organisators festgelegt wird, sind in der Konferenzeinladung enthalten. Alle Zugriffsnummern stehen auf der Seite &quot;Einstellungen für Einwahlkonferenz&quot; zur Verfügung.</p>
<div>

> [!NOTE]
> Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte mithilfe des Cmdlets <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Überprüfen der Einwahlkonferenzeinstellungen</strong></p></td>
<td><p>Suchen Sie mithilfe des Cmdlets <strong>Get-CsDialinConferencingAccessNumber</strong> nach Wähleinstellungen, deren Einwahlkonferenzregion von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern, denen keine Region zugeordnet ist.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Überprüfen der Einwahlkonferenzeinstellungen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Ändern der Tastenzuordnung von DTMF-Befehlen</strong></p></td>
<td><p>Ändern Sie mithilfe des Cmdlets <strong>Set-CsDialinConferencingDtmfConfiguration</strong> die Tasten für DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren), mit denen Teilnehmer Konferenzeinstellungen steuern können (z. B. die Stummschaltung bzw. Aufhebung der Stummschaltung oder die Sperre bzw. Aufheben der Sperre).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Ändern Sie das Ankündigungsverhalten beim Beitreten oder Verlassen einer Konferenz</strong></p></td>
<td><p>Ändern Sie mit dem Cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> die Funktionsweise von Ankündigungen, wenn Teilnehmer einer Konferenz beitreten bzw. diese verlassen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen von Einwahlkonferenzen</strong></p></td>
<td><p>Testen Sie mithilfe des Cmdlets <strong>Test-CsDialInConferencing</strong>, ob die Zugriffsnummern für den angegebenen Pool ordnungsgemäß funktionieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Überprüfen von Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Bereitstellen des Onlinebesprechungs-Add-In für Lync 2013</strong></p></td>
<td><p>Stellen Sie das Onlinebesprechungs-Add-In für Lync 2013 bereit, damit Benutzer Konferenzen planen können, die Einwahlkonferenzfunktionen unterstützen. Das Onlinebesprechungs-Add-In für Lync 2013 wird bei der Installation von Lync 2013 automatisch installiert.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren der Benutzerkontoeinstellungen</strong></p></td>
<td><p>Konfigurieren Sie mithilfe der Systemsteuerung für Lync Server 2013 oder der Lync Server-Verwaltungsshell den <strong>Anschluss-URI</strong> für die Telefonie als eindeutige, normalisierte Rufnummer (z. B. tel:+14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Konfigurieren der Benutzerkontoeinstellungen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Empfohlen) Konfigurieren von Konferenzverzeichnissen</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CsConferenceDirectory</strong>, um ein Konferenzverzeichnis pro 999 Benutzer im Pool zu erstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">Erstellen von Konferenzverzeichnissen (empfohlen)</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Einladen von Benutzern zu Einwahlkonferenzen und Festlegen der anfänglichen PIN</strong></p></td>
<td><p>Verwenden Sie das Skript <strong>Set-CsPinSendCAWelcomeMail</strong>, um die anfänglichen PINs der Benutzer festzulegen und eine Begrüßungs-E-Mail zu senden, in der die anfängliche PIN und ein Link zur Seite &quot;Einstellungen für Einwahlkonferenz&quot; enthalten sind.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

