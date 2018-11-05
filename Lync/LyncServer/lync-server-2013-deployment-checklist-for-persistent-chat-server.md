---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Server für beständigen Chat'
TOCTitle: Prüfliste zur Bereitstellung für den Server für beständigen Chat
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412851(v=OCS.15)
ms:contentKeyID: 49295115
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der Bereitstellung von Lync Server 2013 erfordert der Server für beständigen Chat, dass alle erforderlichen Bereitstellungsschritte in der richtigen Reihenfolge ausgeführt werden.

## Bereitstellungsreihenfolge

Sie können den Server für beständigen Chat bereitstellen, nachdem Sie die anfängliche Topologie mit mindestens einem Lync Server 2013- Front-End-Pool oder einem Lync Server 2013- Standard Edition-Server bereitgestellt haben. In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat durch Hinzufügen zu einer vorhandenen Bereitstellung bereitstellen.

## Bereitstellungsprozess

Die folgende Tabelle führt die grundlegenden Schritte zur Bereitstellung von einem Server für beständigen Chat auf und enthält Links für weitere Details.

### Bereitstellungsprozess für den Server für beständigen Chat

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufgabe</th>
<th>Schritte</th>
<th>Erforderliche Rollen und Gruppenmitgliedschaften</th>
<th>Verwandte Themen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Erforderliche Hardware und Software installieren</strong></p></td>
<td><p>Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</p>
<ul>
<li><p>Auf dem Front-End-Server für den Server für beständigen Chat:</p></li>
</ul>
<ul>
<li><p>Ein Betriebssystem, das die Systemanforderungen erfüllt</p></li>
<li><p>Erforderliche Software für Computer, auf denen Lync Server 2013 ausgeführt wird</p></li>
<li><p>SQL Server auf dem Server, auf dem Server für beständigen Chat-Datenbanken gehostet werden</p></li>
</ul>
<p>Wenn die Kompatibilität für Server für beständigen Chat erforderlich ist:</p>
<ul>
<li><p>SQL Server auf dem Server, auf dem die Kompatibilitätsdatenbank für den Server für beständigen Chat gehostet wird</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Geeignete interne Topologie zur Unterstützung der Server für beständigen Chat (und optional der Kompatibilität für Beständiger Chat) erstellen</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um Ihrer Topologie den Serverpool für beständigen Chat hinzuzufügen:</p>
<ul>
<li><p>Fügen Sie der Topologie Komponenten für den Server für beständigen Chat hinzu</p></li>
<li><p>Erstellen Sie eine SQL Server-Datenbank für den Speicher für den Server für beständigen Chat (und einen Sicherungs- SQL Server für die Notfallwiederherstellung)</p></li>
<li><p>Definieren Sie einen neuen Lync-Dateispeicher, oder verwenden Sie einen vorhandenen Lync-Dateispeicher für Dateien für den Server für beständigen Chat</p></li>
<li><p>Ordnen Sie diesem Serverpool für beständigen Chat den Lync Server 2013-Pool zu, der Anforderungen weiterleiten kann</p></li>
</ul>
<p>Wenn die Kompatibilität für Beständiger Chat erforderlich ist:</p>
<ul>
<li><p>Fügen Sie den Kompatibilitätsspeicher für Beständiger Chat hinzu</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen für die Definition vom Serverpool für beständigen Chat zum Ermöglichen der Kompatibilität</p></li>
<li><p>Veröffentlichen Sie die Topologie</p></li>
</ul>
<p>Wenn Sie den Server für beständigen Chat in der Standard Edition installieren, muss der vollqualifizierte Domänenname der Serverpool für beständigen Chat mit dem Standard Edition-Server übereinstimmen, und die SQL Server-Datenbanken werden mit der SQL Server Express-Instanz auf dem Standard Edition-Server verbunden</p></td>
<td><p>Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe &quot;Benutzer&quot; ist.</p>
<p>Zum Veröffentlichen einer Topologie. Ein Konto, das Mitglied der Gruppe &quot;Domänen-Admins&quot; und der Gruppe &quot;RTCUniversalServerAdmins&quot; ist, und der Benutzer sollte zudem über Vollzugriffsberechtigungen im Lync-Dateispeicher für Dateien für den Server für beständigen Chat verfügen (Lesen/Schreiben/Ändern) (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server für beständigen Chat bereitstellen</strong></p></td>
<td><p>Führen Sie das Setup für Lync Server auf allen Computern mit dem Server für beständigen Chat aus. Das Setup für den Server für beständigen Chat ist im Bereitstellungs-Assistenten von Lync Server 2013 integriert, der die folgenden Anweisungen bereitstellt:</p>
<ul>
<li><p>Den lokalen Verwaltungsspeicher bereitstellen</p></li>
<li><p>Den Server für beständigen Chat installieren</p></li>
<li><p>Zertifikate anfordern und zuweisen</p></li>
<li><p>Dienste ausführen und starten</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des Servers für beständigen Chat in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Einen Administrator für Beständiger Chat erstellen</strong></p></td>
<td><p>Fügen Sie der Sicherheitsgruppe &quot;CsPersistentChatAdministrator&quot; Benutzer hinzu.</p></td>
<td><p>Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server für beständigen Chat konfigurieren</strong></p></td>
<td><p>Konfigurieren von Benutzern:</p>
<ul>
<li><p>Der Benutzer muss gemäß Richtlinie aktiviert sein, um auf den Server für beständigen Chat zuzugreifen. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</p></li>
<li><p>Einstellungen konfigurieren</p></li>
</ul></td>
<td><p>Der Benutzer muss Mitglied von &quot;CsPersistentChatAdministrator&quot; sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in &quot;CsUserAdministrator&quot; befinden.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des Servers für beständigen Chat in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> Sie können einen oder mehrere Serverpools für beständigen Chat bereitstellen. Wir unterstützen mehrere Serverpools für beständigen Chat zur Einhaltung von Bestimmungen, wodurch in einer bestimmten Region erstellte Daten in dieser Region verbleiben. Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago bereitstellen und einen anderen in Zürich, um die gesetzlichen Bestimmungen für Daten in der Schweiz einzuhalten, können Benutzer in beiden Serverpools für beständigen Chat eine Verbindung zu Räumen herstellen, sofern sie über Zugriff verfügen.


