---
title: 'Lync Server 2013: Planen für die rollenbasierte Zugriffssteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-01-27_

Damit Sie administrative Aufgaben delegieren und gleichzeitig hohe Standards für die Sicherheit aufrecht erhalten können, bietet lync Server 2013 rollenbasierte Zugriffssteuerung. Mit RBAC wird Administratorprivilegien gewährt, indem Benutzeradministratorrollen zugewiesen werden. Lync Server 2013 umfasst zahlreiche integrierte Administratorrollen und ermöglicht Ihnen außerdem, neue Rollen zu erstellen und eine benutzerdefinierte Liste mit Cmdlets für jede neue Rolle festzulegen. Sie können auch Skripten von Cmdlets zu den zulässigen Aufgaben von vordefinierten und benutzerdefinierten RBAC-Rollen hinzufügen.

<div>

## <a name="better-server-security-and-centralization"></a>Bessere Server Sicherheit und Zentralisierung

Mit RBAC basieren Zugriff und Autorisierung exakt auf der lync-Server Rolle eines Benutzers. Auf diese Weise wird die Verwendung der Sicherheitspraxis von "Least Privilege" ermöglicht, sodass Administratoren und Benutzern nur die Rechte gewährt werden, die für Ihren Auftrag erforderlich sind.

<div>


> [!IMPORTANT]  
> RBAC-Einschränkungen funktionieren nur für Administratoren, die Remote arbeiten, entweder über die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell. Ein Benutzer, der auf einem Server mit lync Server sitzt, ist nicht durch RBAC eingeschränkt. Daher ist die physische Sicherheit Ihres lync-Servers wichtig, um RBAC-Einschränkungen beizubehalten.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Rollen und Bereich

In RBAC ist eine *Rolle* aktiviert, um eine Liste von Cmdlets zu verwenden, die für einen bestimmten Typ von Administrator oder Techniker nützlich sein sollen. Ein *Bereich* ist die Gruppe von Objekten, auf die die in einer Rolle definierten Cmdlets angewendet werden können. Die Objekte, auf die sich der Bereich auswirkt, können entweder Benutzerkonten (gruppiert nach Organisationseinheit) oder Server (gruppiert nach Website) sein.

In der folgenden Tabelle sind die vordefinierten Rollen in lync Server aufgelistet, und es wird eine allgemeine Übersicht über die einzelnen Aufgabentypen angezeigt. Die vierte Spalte zeigt die ähnliche Microsoft Exchange-Serverrolle für jede lync-Serverrolle, sofern vorhanden.

### <a name="predefined-administrative-roles"></a>Vordefinierte Administratorrollen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rolle</th>
<th>Zulässige Aufgaben</th>
<th>Zugrunde liegende Active Directory-Gruppe</th>
<th>Exchange-Äquivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern, einschließlich des Erstellens von Rollen und Zuweisen von Benutzern zu Rollen. Kann eine Bereitstellung erweitern, indem neue Websites, Pools und Dienste hinzugefügt werden.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organisationsverwaltung</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Kann Benutzer für lync Server aktivieren und deaktivieren, Benutzer verschieben und Benutzern vorhandene Richtlinien zuweisen. Richtlinien können nicht geändert werden.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>E-Mail-Empfänger</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Kann sprachbezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen. Kann neue Verbindungen mit Servern verhindern, Dienste beenden und starten und Softwareupdates anwenden. Mit Auswirkungen auf die globale Konfiguration können keine Änderungen vorgenommen werden.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Verwaltung</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Kann die Bereitstellung, einschließlich Benutzer-und Server Informationen, anzeigen, um den Bereitstellungsstatus zu überwachen.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Organisationsverwaltung mit Ansicht</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Kann die Bereitstellung anzeigen, einschließlich der Eigenschaften und Richtlinien des Benutzers. Kann bestimmte Problembehandlungsaufgaben ausführen. Benutzereigenschaften oder-Richtlinien, Serverkonfiguration oder Dienste können nicht geändert werden.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Helpdesk</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Kann die Archivierungskonfiguration und-Richtlinien ändern.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Aufbewahrungsverwaltung, rechtliche Aufbewahrung</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Kann die Konfiguration der reaktionsgruppenanwendung innerhalb einer Website verwalten.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niedrigste Ebene der Rechte für eine erweiterte Verwaltung von 9-1-1 (E9-1-1), einschließlich der Erstellung von E9-1-1-Speicherorten und Netzwerk Bezeichnern sowie deren Zuordnung untereinander. Diese Rolle wird immer mit einem globalen Bereich zugewiesen.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Kann bestimmte Antwortgruppen verwalten.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Kann das Feature für beständigen Chat und bestimmte beständige Chatrooms verwalten.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


Alle vordefinierten Rollen, die in lync Server ausgeliefert werden, verfügen über einen globalen Bereich. Wenn Sie nur eine begrenzte Anzahl von Servern oder Benutzern verwalten möchten, sollten Sie Benutzern keine Rollen mit globalem Gültigkeitsbereich zuweisen, wenn Sie nur eine begrenzte Anzahl von Servern oder Benutzern verwalten möchten. Um dies zu erreichen, können Sie Rollen erstellen, die auf einer vorhandenen Rolle basieren, jedoch mit einem eingeschränkten Bereich.

<div>

## <a name="creating-a-scoped-role"></a>Erstellen einer Rolle im Bereich "Bereich"

Wenn Sie eine Rolle mit einem eingeschränkten Bereich (einer Rolle mit Gültigkeitsbereich) erstellen, geben Sie den Bereich zusammen mit der vorhandenen Rolle an, auf der er basiert, und der Active Directory-Gruppe, der die Rolle zugewiesen werden soll. Die von Ihnen angegebene Active Directory-Gruppe muss bereits erstellt sein. Das folgende Cmdlet ist ein Beispiel für das Erstellen einer Rolle, die über die Privilegien einer vordefinierten Administratorrolle verfügt, jedoch mit begrenztem Umfang. Sie erstellt eine neue Rolle mit `Site01 Server Administrators`dem Namen. Die Rolle verfügt über die Fähigkeiten der vordefinierten CsServerAdministrator-Rolle, aber nur für die Server, die sich auf der Site01-Website befinden. Damit dieses Cmdlet funktioniert, muss die Site01-Website bereits definiert sein, und es muss bereits eine Univers `Site01 Server Administrators` Elle Sicherheitsgruppe mit dem Namen vorhanden sein.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Nachdem dieses Cmdlet ausgeführt wurde, verfügen alle Benutzer, die Mitglieder `Site01 Server Administrators` der Gruppe sind, über Serveradministratorrechte für die Server in Site01. Darüber hinaus erhalten alle Benutzer, die dieser universellen Sicherheitsgruppe später hinzugefügt werden, auch die Privilegien dieser Rolle. Beachten Sie, dass die Rolle selbst und die universelle Sicherheitsgruppe, der Sie zugewiesen ist `Site01 Server Administrators`, aufgerufen werden.

Im folgenden Beispiel wird der Benutzerbereich anstelle des Serverbereichs eingeschränkt. Sie erstellt eine `Sales Users Administrator` Rolle, um die Benutzerkonten in der Organisationseinheit "Sales" zu verwalten. Die universelle Sicherheitsgruppe SalesUsersAdministrator muss bereits erstellt sein, damit dieses Cmdlet funktioniert.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Erstellen einer neuen Rolle

Zum Erstellen einer Rolle, die Zugriff auf eine Reihe von Cmdlets hat, die nicht in einer der vordefinierten Rollen enthalten sind, oder auf eine Reihe von Skripten oder Modulen, verwenden Sie erneut eine der vordefinierten Rollen als Vorlage. Beachten Sie, dass Skripts und Module, die Rollen ausführen können, an den folgenden Speicherorten gespeichert werden müssen:

  - Der lync-Modul Pfad, der standardmäßig C lautet\\: Program\\Files Common\\Files Microsoft lync Server\\2013\\modules lync

  - Der Benutzer Skriptpfad, der standardmäßig C lautet:\\Program Files\\Common Files\\Microsoft lync Server 2013\\AdminScripts

Zum Erstellen einer neuen Rolle verwenden Sie das Cmdlet **New-CsAdminRole** . Bevor Sie **New-CsAdminRole**ausführen, müssen Sie zuerst die zugrunde liegende universelle Sicherheitsgruppe erstellen, die dieser Rolle zugeordnet ist.

Die folgenden Cmdlets dienen als Beispiel für das Erstellen einer neuen Rolle. Sie erstellen einen neuen Rollentyp mit `MyHelpDeskScriptRole`dem Namen. Die neue Rolle verfügt über die Fähigkeiten der vordefinierten CsHelpDesk-Rolle und kann die Funktionen zusätzlich in einem Skript mit dem Namen "testscript" ausführen.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Damit dieses Cmdlet funktioniert, müssen Sie zuerst die universelle Sicherheitsgruppe MyHelpDeskScriptRole erstellt haben.

Nachdem dieses Cmdlet ausgeführt wurde, können Sie Benutzer dieser Rolle direkt zuweisen (in diesem Fall verfügen Sie über einen globalen Bereich), oder Sie können auf der Grundlage dieser Rolle eine Bereichs Rolle erstellen, wie unter Erstellen einer Rolle im Bereich zuvor in diesem Dokument erläutert.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Zuweisen von Rollen zu Benutzern

Jeder lync-Server Rolle ist eine zugrunde liegende universelle Active Directory-Sicherheitsgruppe zugeordnet. Alle Benutzer, die Sie der zugrunde liegenden Gruppe hinzufügen, erhalten die Fähigkeiten dieser Rolle.

In den Beispielen in den vorherigen Abschnitten wurde eine neue Rolle erstellt und der neuen Rolle eine vorhandene universelle Sicherheitsgruppe zugewiesen. Wenn Sie einer oder mehreren Benutzern eine vorhandene Rolle zuweisen möchten, fügen Sie diese Benutzer der Gruppe hinzu, die der Rolle zugeordnet ist. Sie können diesen Gruppen sowohl einzelne Benutzer als auch universelle Sicherheitsgruppen hinzufügen.

Beispielsweise wird der **CsAdministrator** -Rolle automatisch die universelle Sicherheitsgruppe **CS-Administratoren** in Active Directory gewährt. Diese universelle Sicherheitsgruppe wird in Active Directory erstellt, wenn Sie lync Server bereitstellen. Um einem Benutzer oder einer Gruppe diese Berechtigung zu erteilen, können Sie ihn einfach der Gruppe **CS-Administratoren** hinzufügen.

Einem Benutzer können mehrere RBAC-Rollen zugewiesen werden, indem er zu den zugrunde liegenden Active Directory-Gruppen hinzugefügt wird, die jeder Rolle entsprechen.

Beachten Sie, dass Benutzer, die später der zugrunde liegenden Active Directory-Gruppe hinzugefügt werden, die Fähigkeiten dieser Rolle erhalten, wenn Sie eine Rolle erstellen.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Ändern der Fähigkeiten einer Rolle

Sie können die Liste der Cmdlets und Skripts ändern, die von einer Rolle ausgeführt werden können. Sie können sowohl die Cmdlets und Skripts ändern, die benutzerdefinierte Rollen ausführen können, aber Sie können nur die Skripts für vordefinierte Rollen ändern. Jedes von Ihnen eingegebene Cmdlet kann Cmdlets oder Skripts hinzufügen, entfernen oder ersetzen.

Wenn Sie eine Rolle ändern möchten, verwenden Sie das Cmdlet " **Satz-CsAdminRole** ". Das folgende Cmdlet entfernt ein Skript aus der Rolle.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planen für RBAC

Berücksichtigen Sie für jede Person, die für Ihre lync Server-Bereitstellung jede Art von Administratorrechten erhalten soll, genau, welche Aufgaben Sie durchführen müssen, und weisen Sie Sie den Rollen mit den für Ihren Auftrag erforderlichen geringsten Rechten und Umfang zu. Falls erforderlich, können Sie das Cmdlet " **Satz-CsAdminRole** " verwenden, um eine neue Rolle mit nur den für die Aufgaben dieser Person erforderlichen Cmdlets zu erstellen.

Benutzer mit der CsAdministrator-Rolle können alle Typen von Rollen, einschließlich Rollen basierend auf CsAdministrator, erstellen und Ihnen Benutzer zuweisen. Die bewährte Methode besteht darin, die CsAdministrator-Rolle einem sehr kleinen Satz vertrauenswürdiger Benutzer zuzuweisen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

