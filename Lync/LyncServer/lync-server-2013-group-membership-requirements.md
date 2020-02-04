---
title: 'Lync Server 2013: Erforderliche Gruppenmitgliedschaft'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Erforderliche Gruppenmitgliedschaft für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

In der folgenden Tabelle sind die Gruppen oder Gruppen zusammengefasst, zu denen eine Person gehören soll, um lync Server 2013 erfolgreich zu installieren, zu verwalten und zu beheben.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013, ausführbare Datei</th>
<th>Gruppenmitgliedschaft erforderlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> – ausführbare Datei, mit der die Installation der lync Server 2013-Verwaltungstools gestartet wird.</p></td>
<td><p>Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "Domänenbenutzer", um Informationen in den Active Directory-Domänendiensten zu lesen. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers.</p>
<div>

> [!TIP]  
> Sie können auch Setup Berechtigungen an Benutzer oder Gruppen delegieren, denen Sie nicht die Mitgliedschaft in der Gruppe Domänenadministratoren gewähren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</A> in der Bereitstellungsdokumentation.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy</strong> . exe – von Setup. exe aufgerufen, ist "Deploy. exe" für die Bereitstellung der Softwarekomponenten für die Serverrollen verantwortlich.</p></td>
<td><p>Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "Domänenbenutzer", um Informationen in AD DS zu lesen. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers. Die Mitgliedschaft in der RtcUniversalReadOnlyAdmins-Gruppe ist erforderlich, um den zentralen Verwaltungsspeicher lesen zu können.</p>
<div>

> [!NOTE]  
> Wenn Sie das BetriebssystemWindows Vista oder Windows 7 ausführen, werden Sie von der Benutzerkontensteuerung (User Account Control, UAC) aufgefordert, die Installation fortzusetzen. Wenn Sie mit einem Standardbenutzerkonto angemeldet sind, benötigen Sie eine Person, die ein Mitglied der lokalen Gruppe Administratoren ist, um Anmeldeinformationen einzugeben, wenn Sie aufgefordert werden, ein Konto mit den Berechtigungen zum Installieren der Software einzugeben.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper. exe</strong> – von Setup. exe aufgerufen, ist Bootstrapper. exe verantwortlich für die Bereitstellung und Konfiguration von Serverrollen.</p></td>
<td><p>Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der RTCUniversalServerAdmins-Gruppe, um Bootstrapper. exe auszuführen. Mitglied der Gruppe "Domänenbenutzer", um Informationen in AD DS zu lesen. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – Assistenten gesteuerte Benutzeroberfläche zum Erstellen, anzeigen, anpassen und Validieren von lync Server 2013-Topologien.</p></td>
<td><p>Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird, um die Topologie anzuzeigen. Mitglied der RTCUniversalServerAdmins-Gruppe, um die Konfigurationseinstellungen zu ändern. Mitglied der Gruppe "RTCUniversalServerAdmins", Gruppe "Domänen-Admins" oder Mitglied der RTCUniversalServerAdmins-Gruppe (nur, wenn der Gruppe Berechtigungen für die Stellvertretung erteilt wurden), um die Topologie zu veröffentlichen. Details zum Delegieren von Setup Berechtigungen, damit Mitglieder der RTCUniversalServerAdmins-Gruppe die Topologie veröffentlichen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein, finden Sie unter <a href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – webbasierte grafische Benutzeroberfläche für die Verwaltung von lync Server 2013.</p></td>
<td><p>Mitglied der CsAdministrator-Gruppe oder Mitglied einer anderen rollenbasierten zugriffssteuerungsrolle (Role-Based Access Control, RBAC), der die bestimmte administrative Aufgabe zugewiesen ist. Die lync Server 2013-Systemsteuerung implementiert Konfigurationsänderungen, indem Sie die lync Server 2013-Verwaltungsshell-Cmdlets ausführen. Eine Liste der vordefinierten Rollen und die Cmdlets, die Mitglieder ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe mit dem lync Server 2013-Modul geladen</strong> – Befehlszeilen-Verwaltungstool mit Cmdlets, die für die Verwaltung von lync Server 2013 spezifisch sind.</p></td>
<td><p>Mitglied der CsAdministrator-Gruppe oder Mitglied einer anderen RBAC-Rolle, der das jeweilige Cmdlet zugewiesen wurde. Eine Liste der vordefinierten Rollen und die Cmdlets, die Mitglieder ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a> in der Planungsdokumentation.</p>
<p>Oder, abhängig vom Cmdlet, Mitglied einer oder mehrerer der folgenden Gruppen:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

