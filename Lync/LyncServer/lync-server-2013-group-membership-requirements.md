---
title: 'Lync Server 2013: Anforderungen an die Gruppenmitgliedschaft'
description: 'Lync Server 2013: Gruppen Mitgliedschaftsanforderungen.'
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
ms.openlocfilehash: 3f18fb6fbc782ecd41b7a782965f2cd6a82f6fd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554461"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a>Anforderungen an die Gruppenmitgliedschaft für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

In der folgenden Tabelle sind die Gruppen oder Gruppen zusammengefasst, denen eine Person angehören sollte, um lync Server 2013 erfolgreich zu installieren, zu verwalten und zu beheben.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 ausführbare Datei</th>
<th>Gruppenmitgliedschaft erforderlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong> – ausführbare Datei, mit der die Installation der lync Server 2013-Verwaltungstools gestartet wird.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "Domänenbenutzer" zum Lesen von Informationen in Active Directory-Domänendienste. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden.</p>
<div>

> [!TIP]  
> Es ist möglich, Installationsberechtigungen an Benutzer oder Gruppen zu delegieren, die Sie nicht in die Gruppe "Domänen-Admins" aufnehmen möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</A> in der Bereitstellungsdokumentation.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – Wird von "setup.exe" aufgerufen und zur Bereitstellung der Softwarekomponenten für die Serverrollen ausgeführt.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "Domänen-Benutzer" zum Lesen von Informationen in AD DS. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden. Zum Lesen des zentralen Verwaltungsspeichers ist die Mitgliedschaft in der RtcUniversalReadOnlyAdmins-Gruppe erforderlich.</p>
<div>

> [!NOTE]  
> Wenn Sie das Betriebssystem Windows Vista oder Windows 7 Betriebssystem ausführen, werden Sie von der Benutzerkontensteuerung (User Account Control, UAC) aufgefordert, die Installation fortzusetzen. Wenn Sie über ein Standardbenutzerkonto angemeldet sind, muss ein Mitglied der lokalen Administratorgruppe die erforderlichen Anmeldeinformationen eingeben, wenn Sie zur Angabe eines Kontos mit Berechtigungen zum Installieren der Software aufgefordert werden.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – Wird von "setup.exe" aufgerufen und zur Bereitstellung und Konfiguration von Serverrollen ausgeführt.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "RTCUniversalServerAdmins" zum Ausführen der Datei "Bootstrapper.exe". Mitglied der Gruppe "Domänen-Benutzer" zum Lesen von Informationen in AD DS. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – Assistenten gesteuerte Benutzeroberfläche zum Erstellen, anzeigen, anpassen und Validieren von lync Server 2013 Topologien.</p></td>
<td><p>Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei zum Anzeigen der Topologie ausgeführt wird. Mitglied der Gruppe "RTCUniversalServerAdmins" mit Berechtigung zum Ändern der Konfigurationseinstellungen. Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" oder Mitglied der Gruppe "RTCUniversalServerAdmins" (nur falls der Gruppe die Berechtigung zum Delegieren der Installationsberechtigungen erteilt wurde), um die Topologie zu veröffentlichen. Ausführliche Informationen zum Delegieren von Setup Berechtigungen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Veröffentlichen der Topologie zu ermöglichen, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein, finden Sie unter <a href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – webbasierte grafische Benutzeroberfläche für die Verwaltung von lync Server 2013.</p></td>
<td><p>Mitglied der Gruppe "CsAdministrator" oder einer anderen rollenbasierten Zugriffssteuerungsrolle (Role-Based Access Control, RBAC), der eine bestimmte Verwaltungsaufgabe zugewiesen wurde. In lync Server 2013 Systemsteuerung werden Konfigurationsänderungen durch Ausführen der Cmdlets der lync Server 2013 Verwaltungsshell implementiert. Eine Liste mit vordefinierten Rollen und die Cmdlets, die von Mitgliedern ausgeführt werden dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell.exe mit dem lync Server 2013 Modul Loaded</strong> – Befehlszeilen-Verwaltungstool mit speziell für die Verwaltung von lync Server 2013 spezifischen Cmdlets.</p></td>
<td><p>Mitglied der Gruppe "CsAdministrator" oder einer anderen rollenbasierten Zugriffssteuerungsrolle, der ein bestimmtes Cmdlet zugewiesen wurde. Eine Liste mit vordefinierten Rollen und die Cmdlets, die von Mitgliedern ausgeführt werden dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</a> in der Planungsdokumentation.</p>
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

