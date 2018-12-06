---
title: 'Lync Server 2013: Bereitstellungsprozess für Reaktionsgruppen'
TOCTitle: Bereitstellungsprozess für Reaktionsgruppen
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205270(v=OCS.15)
ms:contentKeyID: 49295504
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieser Abschnitt enthält eine Übersicht über die Phasen und Schritte zum Bereitstellen der Reaktionsgruppenanwendung.

### Prozess zur Bereitstellung von Reaktionsgruppen

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
<td><p>Installieren der Reaktionsgruppenanwendung</p></td>
<td><p>Die Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installieren von Komponenten für die Reaktionsgruppe</p></td>
<td><p>Lync Server-Cmdlets, die Lync Server-Systemsteuerung, das Konfigurationstool für Reaktionsgruppen, die An- und Abmeldekonsole für Agents und der Reaktionsgruppen-Clientwebdienst werden im Rahmen der Webdienste installiert. Die Webdienste werden bei der Bereitstellung eines Enterprise Edition-Pools oder eines Standard Edition-Servers installiert.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzern für Lync 2013 und Enterprise-VoIP</p></td>
<td><p>Aktivieren Sie diejenigen Benutzer, die als Agents für Lync Server und Enterprise-VoIP fungieren sollen. Benutzer müssen aktiviert sein, damit sie Agentgruppen hinzugefügt werden können. Üblicherweise werden Benutzer während der Bereitstellung der Enterprise Edition bzw. des Standard Edition-Servers für Lync Server aktiviert. Für Enterprise-VoIP werden Benutzer während der Enterprise-VoIP-Bereitstellung aktiviert.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen</p></td>
<td><ol>
<li><p>Verwenden Sie die Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell, um folgende Aufgaben auszuführen:</p>
<ol>
<li><p>Erstellen und Konfigurieren von Agentgruppen</p></li>
<li><p>Erstellen und Konfigurieren von Warteschlangen</p></li>
</ol></li>
<li><p>Optional können Sie mit der Lync Server-Verwaltungsshell auch vordefinierte Geschäftszeiten und Feiertage für Reaktionsgruppen erstellen.</p></li>
<li><p>Verwenden Sie das Konfigurationstool für Reaktionsgruppen oder die Lync Server-Verwaltungsshell, um Workflows (Sammelanschlüsse oder interaktive Sprachantwort (Interactive Voice Response, IVR)) wie zum Beispiel benutzerdefinierte Geschäftszeiten und Feiertage für Reaktionsgruppen zu erstellen.</p>
<div>

> [!NOTE]
> Auf das Konfigurationstool für Reaktionsgruppen können Sie über die Lync Server-Systemsteuerung zugreifen.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Erstellen oder Ändern eines Workflows in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Optional) Anpassen der Einstellungen auf Anwendungsebene</p></td>
<td><p>Verwenden Sie die Lync Server-Verwaltungsshell zum Anpassen der Standardkonfiguration für die Musikeinspielung in der Warteschleife, der Standardaudiodatei für die Musikeinspielung in der Warteschleife, der Toleranzperiode für den Rückruf bei Halten des Agents sowie der Anrufkontextkonfiguration.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Optional) Delegieren der Verwaltung von Reaktionsgruppen</p></td>
<td><p>Weisen Sie Benutzer der Rolle CsResponseGroupManager zu, um die Konfiguration von Reaktionsgruppen zu delegieren. Reaktionsgruppemanager können dann die ihnen zugewiesenen Reaktionsgruppen konfigurieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Reaktionsgruppenbereitstellung</p></td>
<td><p>Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>

