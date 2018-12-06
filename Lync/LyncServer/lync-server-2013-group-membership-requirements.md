---
title: 'Lync Server 2013: Erforderliche Gruppenmitgliedschaft'
TOCTitle: Erforderliche Gruppenmitgliedschaft
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204623(v=OCS.15)
ms:contentKeyID: 49292983
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erforderliche Gruppenmitgliedschaft für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der folgenden Tabelle sind die Gruppen aufgeführt, deren Mitglied ein Benutzer sein muss, um Lync Server 2013 erfolgreich installieren, verwalten und eine Problembehandlung für diese Software durchführen zu können.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ausführbare Lync Server 2013-Datei</th>
<th>Gruppenmitgliedschaft erforderlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong>: Ausführbare Datei, mit der die Installation der Lync Server 2013-Verwaltungstools gestartet wird.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe &quot;Domänen-Benutzer&quot; zum Lesen von Informationen in Active Directory-Domänendienste. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter &quot;Programme&quot; oder geschützte Registrierungseinträge wie der Schlüssel &quot;Local Machine&quot; – benötigt werden.</p>
<div>

> [!TIP]
> Es ist möglich, Installationsberechtigungen an Benutzer oder Gruppen zu delegieren, die Sie nicht in die Gruppe "Domänen-Admins" aufnehmen möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setupberechtigungen in Lync Server 2013</A> in der Bereitstellungsdokumentation.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong>: Wird von &quot;setup.exe&quot; aufgerufen und zur Bereitstellung der Softwarekomponenten für die Serverrollen ausgeführt.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe &quot;Domänen-Benutzer&quot; zum Lesen von Informationen in AD DS. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers - z. B. Verzeichnisse unter &quot;Programme&quot; oder geschützte Registrierungseinträge wie der Schlüssel &quot;Local Machine&quot; - benötigt werden. Mitgliedschaft in der Gruppe &quot;RtcUniversalReadOnlyAdmins&quot; zum Lesen des zentralen Verwaltungsspeichers erforderlich.</p>
<div>

> [!NOTE]
> Wenn Sie Windows&nbsp;Vista-Betriebssystem oder Windows&nbsp;7-Betriebssystem ausführen, werden Sie von der Benutzerkontensteuerung (User Account Control, UAC) aufgefordert, mit der Installation fortzufahren. Wenn Sie über ein Standardbenutzerkonto angemeldet sind, muss ein Mitglied der lokalen Administratorgruppe die erforderlichen Anmeldeinformationen eingeben, wenn Sie zur Angabe eines Kontos mit Berechtigungen zum Installieren der Software aufgefordert werden.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong>: Wird von &quot;setup.exe&quot; aufgerufen und zur Bereitstellung und Konfiguration von Serverrollen ausgeführt.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe &quot;RTCUniversalServerAdmins&quot; zum Ausführen der Datei &quot;Bootstrapper.exe&quot;. Mitglied der Gruppe &quot;Domänen-Benutzer&quot; zum Lesen von Informationen in AD DS. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter &quot;Programme&quot; oder geschützte Registrierungseinträge wie der Schlüssel &quot;Local Machine&quot; – benötigt werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong>: Eine Benutzeroberfläche in Form eines Assistenten, um Lync Server 2013-Topologien zu erstellen, anzuzeigen, anzupassen und zu überprüfen.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei zum Anzeigen der Topologie ausgeführt wird. Mitglied der Gruppe &quot;RTCUniversalServerAdmins&quot; mit Berechtigung zum Ändern der Konfigurationseinstellungen. Mitglied der Gruppen &quot;RTCUniversalServerAdmins&quot; und &quot;Domänen-Admins&quot; oder Mitglied der Gruppe &quot;RTCUniversalServerAdmins&quot; (nur falls der Gruppe die Berechtigung zum Delegieren der Installationsberechtigungen erteilt wurde), um die Topologie zu veröffentlichen. Weitere Informationen zum Delegieren von Installationsberechtigungen an Mitglieder der Gruppe &quot;RTCUniversalServerAdmins&quot;, um die Topologie zu veröffentlichen, ohne Mitglied der Gruppe &quot;Domänen-Admins&quot; zu sein, finden Sie unter <a href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setupberechtigungen in Lync Server 2013</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong>: Eine webbasierte, grafische Benutzeroberfläche zur Verwaltung von Lync Server 2013.</p></td>
<td><p>Mitglied der Gruppe &quot;CsAdministrator&quot; oder einer anderen rollenbasierten Zugriffssteuerungsrolle (Role-Based Access Control, RBAC), der eine bestimmte Verwaltungsaufgabe zugewiesen wurde. Systemsteuerung für Lync Server 2013 implementiert Änderungen an der Konfiguration mithilfe von Verwaltungsshell für Lync Server 2013-Cmdlets. Eine Liste vordefinierter Rollen und Cmdlets, die Benutzer ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>&quot;PowerShell.exe&quot; mit geladenem Lync Server 2013-Modul</strong>: Befehlszeilentool mit Cmdlets speziell für die Verwaltung von Lync Server 2013.</p></td>
<td><p>Mitglied der Gruppe &quot;CsAdministrator&quot; oder einer anderen rollenbasierten Zugriffssteuerungsrolle, der ein bestimmtes Cmdlet zugewiesen wurde. Eine Liste vordefinierter Rollen und Cmdlets, die Benutzer ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</a> in der Planungsdokumentation.</p>
<p>Oder, abhängig vom Cmdlet, Mitglied einer oder mehrerer der folgenden Gruppen:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>

