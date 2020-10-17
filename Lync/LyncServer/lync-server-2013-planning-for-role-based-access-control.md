---
title: 'Lync Server 2013: Planen der rollenbasierten Zugriffssteuerung'
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
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528032"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planen der rollenbasierten Zugriffssteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-01-27_

Damit Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können, bietet lync Server 2013 rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC). Bei der rollenbasierten Zugriffssteuerung werden administrative Berechtigungen erteilt, indem Benutzer Administratorrollen zugewiesen werden. Lync Server 2013 enthält eine umfangreiche Reihe integrierter Administratorrollen und ermöglicht Ihnen außerdem das Erstellen neuer Rollen und das Angeben einer benutzerdefinierten Liste von Cmdlets für jede neue Rolle. Sie können außerdem den erlaubten Aufgaben der vordefinierten und der benutzerdefinierten rollenbasierten Zugriffssteuerung Skripte von Cmdlets hinzufügen.

<div>

## <a name="better-server-security-and-centralization"></a>Verbesserte Serversicherheit und Zentralisierung

Bei RBAC basiert der Zugriff und die Autorisierung genau auf der lync Server Rolle eines Benutzers. So können Sie dem Sicherheitsprinzip "so wenige Rechte wie möglich" folgen, bei dem Administratoren und Benutzer nur die Rechte erhalten, die sie für ihre Arbeit benötigen.

<div>


> [!IMPORTANT]  
> RBAC-Einschränkungen funktionieren nur für Administratoren, die Remote arbeiten, indem Sie entweder die lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwenden. Ein Benutzer, der auf einem Server mit lync Server sitzt, wird nicht durch RBAC eingeschränkt. Daher ist die physische Sicherheit Ihrer lync Server wichtig, um RBAC-Einschränkungen beizubehalten.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Rollen und Bereiche

Bei der rollenbasierten Zugriffssteuerung kann eine *Rolle* eine Liste von Cmdlets verwenden, die für einen bestimmten Administratortyp oder Techniker von Interesse sind. Ein *Bereich* ist der Satz an Objekten, auf den die in einer Rolle definierten Cmdlets angewendet werden können. Bei den Objekten für diesen Bereich kann es sich entweder um Benutzerkonten (gruppiert nach Organisationseinheit) oder um Server (gruppiert nach Standort) handeln.

In der folgenden Tabelle sind die vordefinierten Rollen in lync Server aufgeführt, und es wird eine allgemeine Übersicht über die Aufgabentypen gegeben, die jeweils ausgeführt werden können. In der vierten Spalte wird die ähnliche Exchange Server Rolle für jede lync Server Rolle angezeigt (sofern vorhanden).

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
<td><p>Kann sämtliche Verwaltungsaufgaben ausführen und alle Einstellungen ändern, einschließlich der Erstellung von Rollen und der Zuweisung von Benutzern zu Rollen. Kann eine Bereitstellung erweitern, indem neue Standorte, Pools und Dienste hinzugefügt werden.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organisationsverwaltung</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Kann Benutzer für lync Server aktivieren und deaktivieren, Benutzer verlagern und vorhandene Richtlinien Benutzern zuweisen. Kann keine Richtlinien bearbeiten.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mailempfänger</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Nicht zutreffend.</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Kann Server und Dienste verwalten, überwachen und eine Problembehandlung durchführen. Kann neue Verbindungen mit Servern verhindern, Dienste beenden und starten und Softwareupdates anwenden. Kann keine Änderungen mit Auswirkung auf die globale Konfiguration durchführen.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Serververwaltung</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Kann die Bereitstellung anzeigen, einschließlich Benutzer- und Serverinformationen, um die Bereitstellungsintegrität zu überwachen.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Organisationsverwaltung (Nur Lesen)</p></td>
</tr>
<tr class="even">
<td><p>"Cshelpdesk"</p></td>
<td><p>Kann die Bereitstellung anzeigen, Benutzereigenschaften und -richtlinien eingeschlossen. Kann Aufgaben im Rahmen der Problembehandlung ausführen. Kann keine Benutzereigenschaften oder -richtlinien, Serverkonfigurationen oder Dienste ändern.</p></td>
<td><p>"Cshelpdesk"</p></td>
<td><p>Helpdesk</p></td>
</tr>
<tr class="odd">
<td><p>Csarchivingadministrator "</p></td>
<td><p>Kann Archivierungskonfiguration und -richtlinien ändern.</p></td>
<td><p>Csarchivingadministrator "</p></td>
<td><p>Verwaltung der Aufbewahrung, rechtliche Aufbewahrungspflicht</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Kann die Konfiguration der Reaktionsgruppenanwendung innerhalb eines Standorts verwalten.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niedrigste Berechtigungsstufe für E9-1-1-Verwaltung (9-1-1 [erweitert]), einschließlich Erstellung von E9-1-1-Standorten und Netzwerk-IDs, sowie deren Zuordnung zueinander. Diese Rolle wird immer mit globalem Gültigkeitsbereich zugewiesen.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Rolle csresponsegroupmanager</p></td>
<td><p>Kann spezifische Reaktionsgruppen verwalten.</p></td>
<td><p>Rolle csresponsegroupmanager</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>"Cspersistentchatadministrator"</p></td>
<td><p>Kann die Funktion "Beständiger Chat" und spezifische Räume dafür verwalten.</p></td>
<td><p>"Cspersistentchatadministrator"</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


Alle vordefinierten Rollen, die in lync Server ausgeliefert werden, haben einen globalen Bereich. Um dem Prinzip "so wenige Rechte wie möglich" zu folgen, sollten Sie Benutzern keine Rollen mit globalem Bereich zuweisen, wenn sie nur einen beschränkten Satz an Servern oder Benutzern verwalten sollen. Stattdessen können Sie Rollen erstellen, die auf einer bestehenden Rolle basieren, deren Bereich jedoch eingeschränkter ist.

<div>

## <a name="creating-a-scoped-role"></a>Erstellen einer bereichsbezogenen Rolle

Wenn Sie eine Rolle mit begrenztem Bereich erstellen (eine bereichsbezogene Rolle), geben Sie den Bereich zusammen mit der vorhandenen Rolle und der Active Directory Gruppe an, der die Rolle zugewiesen werden soll. Die von Ihnen angegebene Active Directory Gruppe muss bereits erstellt sein. Das folgende Cmdlet ist ein Beispiel für das Erstellen einer Rolle mit den Berechtigungen einer der vordefinierten Administratorrollen, jedoch mit begrenztem Bereich. Es wird eine neue Rolle mit dem Namen erstellt `Site01 Server Administrators` . Die Rolle besitzt die Fähigkeiten der vordefinierten CsServerAdministrator-Rolle, jedoch nur für die Server, die sich am Site01-Standort befinden. Damit dieses Cmdlet funktioniert, muss der Site01-Standort bereits definiert sein, und es muss bereits eine universelle Sicherheitsgruppe mit dem Namen `Site01 Server Administrators` vorhanden sein.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Nachdem dieses Cmdlet ausgeführt wurde, verfügen alle Benutzer, die Mitglied der Gruppe sind, `Site01 Server Administrators` über Serveradministratorrechte für die Server in Site01. Darüber hinaus erhalten alle Benutzer, die dieser universellen Sicherheitsgruppe später hinzugefügt werden, auch die Rechte dieser Rolle. Beachten Sie, dass sowohl die Rolle selbst als auch die universelle Sicherheitsgruppe, der Sie zugewiesen ist, aufgerufen werden `Site01 Server Administrators` .

Im folgenden Beispiel wird der Serverbereich auf den Benutzerbereich eingeschränkt. Es wird eine `Sales Users Administrator` Rolle zum Verwalten der Benutzerkonten in der Organisationseinheit "Sales" erstellt. Die universelle Sicherheitsgruppe SalesUsersAdministrator muss bereits erstellt sein, damit dieses Cmdlet funktioniert.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Erstellen einer neuen Rolle

Um eine Rolle zu erstellen, die Zugriff auf einen Satz von Cmdlets außerhalb der vordefinierten Rollen oder auf einen Satz von Skripts oder Modulen hat, müssen Sie ebenfalls zunächst eine der vordefinierten Rollen als Vorlage verwenden. Beachten Sie, dass Skripts und Module, die Rollen ausführen können sollen, an folgenden Orten gespeichert werden müssen:

  - Der lync-Modul Pfad, der standardmäßig C: \\ Programmdateien \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ Module \\ lync

  - Der Benutzer Skriptpfad, der standardmäßig C: \\ Programmdateien \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ AdminScripts

Um eine neue Rolle zu erstellen, verwenden Sie das Cmdlet **New-CsAdminRole**. Vor dem Ausführen von **New-CsAdminRole**müssen Sie zuerst die zugrunde liegende universelle Sicherheitsgruppe erstellen, die dieser Rolle zugeordnet wird.

Die folgenden Cmdlet-Beispiele zeigen die Erstellung einer neuen Rolle. Sie erstellen einen neuen Rollentypen mit dem Namen `MyHelpDeskScriptRole` . Die neue Rolle besitzt die Fähigkeiten der vordefinierten Rolle "CsHelpDesk" und kann außerdem die Funktionen in einem Skript namens "testscript" ausführen.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Damit dieses Cmdlet funktioniert, müssen Sie zuerst die universelle Sicherheitsgruppe MyHelpDeskScriptRole erstellt haben.

Nach der Ausführung dieses Cmdlets können Sie Benutzer direkt dieser Rolle zuweisen (in diesem Fall haben sie globalen Gültigkeitsbereich) oder eine auf dieser Rolle basierende bereichsbezogene Rolle erstellen. Dies wird weiter oben in diesem Dokument unter "Erstellen einer bereichsbezogenen Rolle" beschrieben.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Zuweisen von Rollen zu Benutzern

Jede lync Server Rolle ist einer zugrunde liegenden Active Directory universellen Sicherheitsgruppe zugeordnet. Alle Benutzer, die Sie der zugrunde liegenden Gruppe hinzufügen, erhalten die Fähigkeiten dieser Rolle.

In den Beispielen in den vorherigen Abschnitten wurde eine neue Rolle erstellt und der neuen Rolle eine vorhandene universelle Sicherheitsgruppe zugewiesen. Wenn Sie einer vorhandenen Rolle einen oder mehrere Benutzer zuweisen möchten, fügen Sie diese Benutzer der Gruppe zu, die der Rolle zugeordnet ist. Sie können diesen Gruppen sowohl einzelne Benutzer als auch universelle Sicherheitsgruppen hinzufügen.

Beispielsweise wird die **CsAdministrator** -Rolle automatisch der universellen Sicherheitsgruppe **CS-Administratoren** in Active Directory erteilt. Diese universelle Sicherheitsgruppe wird in Active Directory erstellt, wenn Sie lync Server bereitstellen. Wenn Sie einem Benutzer oder einer Gruppe diese Berechtigungen gewähren möchten, können Sie sie einfach der Gruppe **CS-Administratoren** hinzufügen.

Einem Benutzer können mehrere rollenbasierte Zugriffssteuerungsrollen hinzugefügt werden, indem er den zugrunde liegenden Active Directory-Gruppen hinzugefügt wird, die dieser Rolle entsprechen.

Beachten Sie, dass beim Erstellen einer Rolle alle Benutzer, die der zugrunde liegenden Active Directory-Gruppe später hinzugefügt werden, die Fähigkeiten dieser Rolle erhalten.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Ändern der Fähigkeiten einer Rolle

Sie können die Liste der Cmdlets und Skripts ändern, die von einer Rolle ausgeführt werden können. Sie können sowohl die Cmdlets als auch die Skripts bearbeiten, die von benutzerdefinierten Rollen ausgeführt werden können, bei vordefinierten Rollen können Sie jedoch nur die Skripts bearbeiten. Jedes Cmdlet, das Sie eingeben, kann Cmdlets oder Skripts hinzufügen, entfernen oder ersetzen.

Um eine Rolle zu bearbeiten, verwenden Sie das Cmdlet **Set-CsAdminRole**. Mit dem folgenden Cmdlet wird ein Skript aus der Rolle entfernt.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planen der rollenbasierten Zugriffssteuerung

Berücksichtigen Sie für jede Person, die eine beliebige Anzahl von Administratorrechten für Ihre lync Server-Bereitstellung erhalten soll, genau, welche Aufgaben Sie durchführen müssen, und weisen Sie Sie Rollen mit den geringsten Rechten und dem für Ihren Auftrag erforderlichen Bereich zu. Falls erforderlich, können Sie das Cmdlet " **CsAdminRole** " verwenden, um eine neue Rolle mit nur den für die Aufgaben dieser Person erforderlichen Cmdlets zu erstellen.

Benutzer mit der Rolle "CsAdministrator" können Rollen jeglichen Typs erstellen – auf "CsAdministrator" basierende Rollen eingeschlossen – und diesen Rollen Benutzer zuweisen. Als bewährte Methode sollte die Rolle "CsAdministrator" nur einem sehr kleinen Kreis vertrauenswürdiger Benutzer zugewiesen werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

