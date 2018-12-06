---
title: 'Lync Server 2013: Planen für die rollenbasierte Zugriffssteuerung'
TOCTitle: Planen für die rollenbasierte Zugriffssteuerung (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425917(v=OCS.15)
ms:contentKeyID: 49293801
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Lync Server 2013 bietet rollenbasierte Zugriffssteuerung, um Ihnen das Delegieren von Verwaltungsaufgaben zu ermöglichen, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt. Bei der rollenbasierten Zugriffssteuerung werden administrative Berechtigungen erteilt, indem Benutzer Administratorrollen zugewiesen werden. Lync Server 2013 umfasst zahlreiche integrierte Administratorrollen und ermöglicht Ihnen auch die Erstellung neuer Rollen und die Angabe einer benutzerdefinierten Liste von Cmdlets für jede neue Rolle. Sie können außerdem den erlaubten Aufgaben der vordefinierten und der benutzerdefinierten rollenbasierten Zugriffssteuerung Skripte von Cmdlets hinzufügen.

## Verbesserte Serversicherheit und Zentralisierung

Mit der rollenbasierten Zugriffssteuerung können Zugriff und Autorisierung basierend auf der Lync Server-Rolle eines Benutzers genau gesteuert werden. So können Sie dem Sicherheitsprinzip "so wenige Rechte wie möglich" folgen, bei dem Administratoren und Benutzer nur die Rechte erhalten, die sie für ihre Arbeit benötigen.


> [!IMPORTANT]
> Die Einschränkungen der rollenbasierten Zugriffssteuerung gelten nur für Administratoren, die remote arbeiten und entweder die Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell verwenden. Ein Benutzer, der lokal an einem Server sitzt, auf dem die Lync Server ausgeführt wird, wird nicht über die rollenbasierte Zugriffssteuerung eingeschränkt. Aus diesem Grund stellt die physische Sicherheit Ihres Lync Server-Systems einen wichtigen Faktor bei der rollenbasierten Zugriffssteuerung dar.



## Rollen und Bereiche

Bei der rollenbasierten Zugriffssteuerung kann eine *Rolle* eine Liste von Cmdlets verwenden, die für einen bestimmten Administratortyp oder Techniker von Interesse sind. Ein *Bereich* ist der Satz an Objekten, auf den die in einer Rolle definierten Cmdlets angewendet werden können. Bei den Objekten für diesen Bereich kann es sich entweder um Benutzerkonten (gruppiert nach Organisationseinheit) oder um Server (gruppiert nach Standort) handeln.

In der folgenden Liste werden die vordefinierten Rollen in Lync Server aufgeführt, und Sie erhalten einen allgemeinen Überblick über die Arten von Aufgaben, die mit jeder Rolle ausgeführt werden können. Die vierte Spalte zeigt die vergleichbare Microsoft Exchange Server-Rolle für jede Lync Server, sofern vorhanden.

### Vordefinierte Administratorrollen

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
<td><p>Kann Benutzer für Lync Server aktivieren und deaktivieren, Benutzer verschieben und Benutzern vorhandene Richtlinien zuweisen. Kann keine Richtlinien bearbeiten.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mailempfänger</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
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
<td><p>CsHelpDesk</p></td>
<td><p>Kann die Bereitstellung anzeigen, Benutzereigenschaften und -richtlinien eingeschlossen. Kann Aufgaben im Rahmen der Problembehandlung ausführen. Kann keine Benutzereigenschaften oder -richtlinien, Serverkonfigurationen oder Dienste ändern.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Helpdesk</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Kann Archivierungskonfiguration und -richtlinien ändern.</p></td>
<td><p>CSArchivingAdministrator</p></td>
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
<td><p>CsResponseGroupManager</p></td>
<td><p>Kann spezifische Reaktionsgruppen verwalten.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Kann die Funktion &quot;Beständiger Chat&quot; und spezifische Räume dafür verwalten.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>CsAdministrator</p></td>
<td><p>Kann sämtliche Verwaltungsaufgaben ausführen und alle Einstellungen ändern, einschließlich der Erstellung von Rollen und der Zuweisung von Benutzern zu Rollen. Kann eine Bereitstellung erweitern, indem neue Standorte, Pools und Dienste hinzugefügt werden.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organisationsverwaltung</p></td>
</tr>
<tr class="odd">
<td><p>CsUserAdministrator</p></td>
<td><p>Kann Benutzer für Lync Server aktivieren und deaktivieren, Benutzer verschieben und Benutzern vorhandene Richtlinien zuweisen. Kann keine Richtlinien bearbeiten.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mailempfänger</p></td>
</tr>
<tr class="even">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsServerAdministrator</p></td>
<td><p>Kann Server und Dienste verwalten, überwachen und eine Problembehandlung durchführen. Kann neue Verbindungen mit Servern verhindern, Dienste beenden und starten und Softwareupdates anwenden. Kann keine Änderungen mit Auswirkung auf die globale Konfiguration durchführen.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Serververwaltung</p></td>
</tr>
<tr class="even">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Kann die Bereitstellung anzeigen, einschließlich Benutzer- und Serverinformationen, um die Bereitstellungsintegrität zu überwachen.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Organisationsverwaltung (Nur Lesen)</p></td>
</tr>
<tr class="odd">
<td><p>CsHelpDesk</p></td>
<td><p>Kann die Bereitstellung anzeigen, Benutzereigenschaften und -richtlinien eingeschlossen. Kann Aufgaben im Rahmen der Problembehandlung ausführen. Kann keine Benutzereigenschaften oder -richtlinien, Serverkonfigurationen oder Dienste ändern.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Helpdesk</p></td>
</tr>
<tr class="even">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Kann Archivierungskonfiguration und -richtlinien ändern.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Verwaltung der Aufbewahrung, rechtliche Aufbewahrungspflicht</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Kann die Konfiguration der Reaktionsgruppenanwendung innerhalb eines Standorts verwalten.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>CsLocationAdministrator</p></td>
<td><p>Niedrigste Berechtigungsstufe für E9-1-1-Verwaltung (9-1-1 [erweitert]), einschließlich Erstellung von E9-1-1-Standorten und Netzwerk-IDs, sowie deren Zuordnung zueinander. Diese Rolle wird immer mit globalem Gültigkeitsbereich zugewiesen.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupManager</p></td>
<td><p>Kann spezifische Reaktionsgruppen verwalten.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Kann die Funktion &quot;Beständiger Chat&quot; und spezifische Räume dafür verwalten.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


Alle vordefinierten Rollen in Lync Server gelten auf globaler Ebene. Um dem Prinzip "so wenige Rechte wie möglich" zu folgen, sollten Sie Benutzern keine Rollen mit globalem Bereich zuweisen, wenn sie nur einen beschränkten Satz an Servern oder Benutzern verwalten sollen. Stattdessen können Sie Rollen erstellen, die auf einer bestehenden Rolle basieren, deren Bereich jedoch eingeschränkter ist.

## Erstellen einer bereichsbezogenen Rolle

Wenn Sie eine Rolle mit einem beschränkten Bereich (eine sogenannte bereichsbezogene Rolle) erstellen, geben Sie den Bereich an, zusammen mit der vorhandenen Rolle, auf der die neue Rolle basieren soll, sowie der Active Directory-Gruppe, der Sie die Rolle zuweisen möchten. Die angegebene Active Directory-Gruppe muss bereits erstellt worden sein. Das folgende Cmdlet-Beispiel zeigt die Erstellung einer Rolle mit den Berechtigungen einer der vordefinierten Administratorrollen, jedoch mit eingeschränktem Bereich. Die neu erstellte Rolle trägt den Namen `Site01 Server Administrators`. Die Rolle besitzt die Fähigkeiten der vordefinierten Rolle "CsServerAdministrator", aber nur für die Server am Standort "Site01". Damit dieses Cmdlet funktioniert, muss Standort "Site01" bereits definiert worden sein. Zudem muss eine universelle Sicherheitsgruppe mit dem Namen `Site01 Server Administrators` erstellt worden sein.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Nach der Ausführung dieses Cmdlets verfügen alle Benutzer, die Mitglied der Gruppe `Site01 Server Administrators` sind, über Serveradministratorrechte für die Server am Standort "Site01". Zusätzlich erhalten alle Benutzer, die später dieser universellen Sicherheitsgruppe hinzugefügt werden, die Berechtigungen dieser Rolle. Beachten Sie, dass die Rolle selbst und die universelle Sicherheitsgruppe, der sie zugewiesen ist, den Namen `Site01 Server Administrators` aufweisen.

Im folgenden Beispiel wird der Serverbereich auf den Benutzerbereich eingeschränkt. Es wird eine Rolle namens `Sales Users Administrator` erstellt, mit der die Benutzerkonten in der Organisationseinheit "Sales" verwaltet werden können. Die universelle Sicherheitsgruppe "SalesUsersAdministrator" muss bereits erstellt worden sein, damit dieses Cmdlet funktioniert.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

## Erstellen einer neuen Rolle

Um eine Rolle zu erstellen, die Zugriff auf einen Satz von Cmdlets außerhalb der vordefinierten Rollen oder auf einen Satz von Skripts oder Modulen hat, müssen Sie ebenfalls zunächst eine der vordefinierten Rollen als Vorlage verwenden. Beachten Sie, dass Skripts und Module, die Rollen ausführen können sollen, an folgenden Orten gespeichert werden müssen:

  - Im Lync-Modulverzeichnis unter dem Standardpfad "C:\\Programme\\Gemeinsame Dateien\\Microsoft Lync Server 2013\\Module\\Lync".

  - Im Benutzerskriptverzeichnis unter dem Standardpfad "C:\\Programme\\Gemeinsame Dateien\\Microsoft Lync Server 2013\\AdminScripts".

Um eine neue Rolle zu erstellen, verwenden Sie das Cmdlet **New-CsAdminRole**. Vor der Ausführung von **New-CsAdminRole** müssen Sie zunächst die zugrunde liegende universelle Sicherheitsgruppe erstellen, der diese Rolle zugewiesen werden soll.

Die folgenden Cmdlet-Beispiele zeigen die Erstellung einer neuen Rolle. Dabei wird ein neuer Rollentyp namens `MyHelpDeskScriptRole` erstellt. Die neue Rolle besitzt die Fähigkeiten der vordefinierten Rolle "CsHelpDesk" und kann außerdem die Funktionen in einem Skript namens "testscript" ausführen.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Damit dieses Cmdlet funktioniert, müssen Sie zuvor die universelle Sicherheitsgruppe "MyHelpDeskScriptRole" erstellt haben.

Nach der Ausführung dieses Cmdlets können Sie Benutzer direkt dieser Rolle zuweisen (in diesem Fall haben sie globalen Gültigkeitsbereich) oder eine auf dieser Rolle basierende bereichsbezogene Rolle erstellen. Dies wird weiter oben in diesem Dokument unter "Erstellen einer bereichsbezogenen Rolle" beschrieben.

## Zuweisen von Rollen zu Benutzern

Jede Lync Server-Rolle ist einer zugrunde liegenden universellen Active Directory-Sicherheitsgruppe zugeordnet. Alle Benutzer, die Sie der zugrunde liegenden Gruppe hinzufügen, erhalten die Fähigkeiten dieser Rolle.

In den Beispielen in den vorangehenden Abschnitten wurde eine neue Rolle erstellt und dieser neuen Rolle eine bestehende universelle Sicherheitsgruppe zugewiesen. Wenn Sie einer vorhandenen Rolle einen oder mehrere Benutzer zuweisen möchten, fügen Sie diese Benutzer der Gruppe zu, die der Rolle zugeordnet ist. Sie können sowohl einzelne Benutzer als auch universelle Sicherheitsgruppen zu diesen Gruppen hinzufügen.

Beispielsweise wird die Rolle **CsAdministrator** automatisch der universellen Sicherheitsgruppe **CS-Administratoren** in Active Directory gewährt. Diese Sicherheitsgruppe wird bei der Installation oder Bereitstellung von Lync Server in Active Directory erstellt. Wenn Sie einem Benutzer oder einer Gruppe diese Berechtigungen gewähren möchten, können Sie sie einfach der Gruppe **CS-Administratoren** hinzufügen.

Einem Benutzer können mehrere rollenbasierte Zugriffssteuerungsrollen hinzugefügt werden, indem er den zugrunde liegenden Active Directory-Gruppen hinzugefügt wird, die dieser Rolle entsprechen.

Beachten Sie, dass beim Erstellen einer Rolle alle Benutzer, die der zugrunde liegenden Active Directory-Gruppe später hinzugefügt werden, die Fähigkeiten dieser Rolle erhalten.

## Ändern der Fähigkeiten einer Rolle

Sie können die Liste der Cmdlets und Skripts ändern, die von einer Rolle ausgeführt werden können. Sie können sowohl die Cmdlets als auch die Skripts bearbeiten, die von benutzerdefinierten Rollen ausgeführt werden können, bei vordefinierten Rollen können Sie jedoch nur die Skripts bearbeiten. Jedes Cmdlet, das Sie eingeben, kann Cmdlets oder Skripts hinzufügen, entfernen oder ersetzen.

Um eine Rolle zu bearbeiten, verwenden Sie das Cmdlet **Set-CsAdminRole** . Das folgende Cmdlet entfernt ein Skript aus der Rolle.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

## Planen der rollenbasierten Zugriffssteuerung

Überprüfen Sie für jeden Benutzer, dem Sie administrative Rechte für Ihre Lync Server-Bereitstellung gewähren möchten, welche Aufgaben genau dieser Benutzer ausführen muss. Weisen Sie den Benutzer dann einer Rolle zu, welche die geringste Berechtigungsstufe und den kleinsten Bereich für die jeweiligen Aufgaben gewährt. Bei Bedarf können Sie das Cmdlet **Set-CsAdminRole** verwenden, um eine neue Rolle mit nur den für die Aufgaben dieser Person erforderlichen Cmdlets zu erstellen.

Benutzer mit der Rolle "CsAdministrator" können Rollen jeglichen Typs erstellen - auf "CsAdministrator" basierende Rollen eingeschlossen - und diesen Rollen Benutzer zuweisen. Als bewährte Methode sollte die Rolle "CsAdministrator" nur einem sehr kleinen Kreis vertrauenswürdiger Benutzer zugewiesen werden.

