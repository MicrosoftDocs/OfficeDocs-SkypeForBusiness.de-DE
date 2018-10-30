---
title: Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013
TOCTitle: Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425791(v=OCS.15)
ms:contentKeyID: 49293541
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieser Abschnitt enthält eine Beschreibung der globalen Einstellungen und Objekte und der universellen Dienst- und Verwaltungsgruppen, die bei der Gesamtstrukturvorbereitung erstellt werden.

## Globale Einstellungen und Objekte in Active Directory

Wenn Sie die globalen Einstellungen im Konfigurationscontainer speichern (dies ist bei allen neuen Lync Server 2013-Bereitstellungen der Fall), wird bei der Gesamtstrukturvorbereitung der vorhandene Dienstcontainer verwendet, und unterhalb des Objekts "Configuration\\Services" wird ein Objekt **RTC Service** hinzugefügt. Unterhalb des Objekts "RTC Service" wird bei der Gesamtstrukturvorbereitung ein Objekt **Global Settings** vom Typ "msRTCSIP-GlobalContainer" hinzugefügt. Das Objekt für globale Einstellungen enthält alle Einstellungen, die in der Lync Server-Bereitstellung angewendet werden. Wenn Sie die globalen Einstellungen im Systemcontainer speichern, wird bei der Gesamtstrukturvorbereitung ein Microsoft-Container unterhalb des Systemcontainers der Stammdomäne verwendet und unterhalb des Objekts "System\\Microsoft" ein Objekt "RTC Service" hinzugefügt.

Außerdem wird während der Gesamtstrukturvorbereitung ein neues Objekt **msRTCSIP-Domain** für die Stammdomäne hinzugefügt, in der das Verfahren ausgeführt wird.

## Universelle Dienst- und Verwaltungsgruppen in Active Directory

Die Gesamtstrukturvorbereitung erstellt universelle Gruppen anhand der von Ihnen angegebenen Domäne und fügt Zugriffssteuerungseinträge (Access Control Entries, ACEs) für diese Gruppen hinzu. In diesem Schritt werden die universellen Gruppen in den Benutzercontainern der Domäne erstellt, die Sie angegeben haben.

Anhand von universellen Gruppen können Administratoren globale Einstellungen und Dienste verwenden und verwalten. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:

  - **Administrative Gruppen**   Mit diesen Gruppen werden Administratorrollen für ein Lync Server-Netzwerk definiert.

  - **Infrastrukturgruppen**   Mit diesen Gruppen werden Berechtigungen zum Zugriff auf spezielle Bereiche der Lync Server-Infrastruktur erteilt. Sie fungieren als Komponenten von administrativen Gruppen. Sie sollten diese Gruppen weder ändern noch direkt Benutzer zu ihnen hinzufügen.

  - **Dienstgruppen**   Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Lync Server-Dienste benötigt werden.

In der folgenden Tabelle werden die administrativen Gruppen beschrieben.

### Administrative Gruppen, die während der Gesamtstrukturvorbereitung erstellt werden

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Administrative Gruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Erlaubt den Mitgliedern, Server- und Pooleinstellungen zu verwalten, darunter alle Serverrollen, globalen Einstellungen und Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Ermöglicht Mitgliedern das Verwalten von Benutzereinstellungen und das Verschieben von Benutzern von einem Server oder Pool zu einem anderen.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Ermöglicht Mitgliedern das Lesen von Server-, Pool- und Benutzereinstellungen.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.

### Infrastrukturgruppen, die während der Gesamtstrukturvorbereitung erstellt werden

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Infrastrukturgruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Gewährt Schreibzugriff auf die globalen Einstellungsobjekte für Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Gewährt Lesezugriff auf die globalen Einstellungsobjekte für Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Gewährt Lesezugriff auf die Lync Server-Benutzereinstellungen.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Gewährt Lesezugriff auf die Lync Server-Einstellungen. Diese Gruppe hat keinen Zugriff auf die Einstellungen auf Poolebene, sondern lediglich auf Einstellungen für einzelne Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf die Lync Server-Konfiguration und wird bei der Installation in die lokale Administratorgruppe der Survivable Branch Appliances eingefügt.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Dienstgruppen beschrieben.

### Dienstgruppen, die während der Gesamtstrukturvorbereitung erstellt werden

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dienstgruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die zum Ausführen des Front-End-Servers und des Standard Edition-Servers verwendet werden. Diese Gruppe ermöglicht Servern Lese-/Schreibzugriff auf die globalen Einstellungen von Lync Server und die Active Directory-Benutzerobjekte.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Umfasst Dienstkonten zur Ausführung von A/V-Konferenzservern, Webdiensten, Vermittlungsservern, Archivierungsservern und Monitoring-Servern.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die zum Ausführen von Lync Server-Edgeservern verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Enthält Server, die an der Lync Serverzentralen Verwaltungsspeicher-Replikation teilnehmen können.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf die Lync Server-Einstellungen, ermöglicht aber auch die Konfiguration der Installation einer Survivable Branch Server- und Survivable Branch Appliance-Bereitstellung.</p></td>
</tr>
</tbody>
</table>


Die Gesamtstrukturvorbereitung fügt den entsprechenden Infrastrukturgruppen dann wie folgt Dienst- und Verwaltungsgruppen hinzu:

  - "RTCUniversalServerAdmins" wird zu "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalGlobalWriteGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

  - "RTCUniversalUserAdmins" wird als Mitglied von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

  - "RTCHSUniversalServices", "RTCComponentUniversalServices" und "RTCUniversalReadOnlyAdmins" werden als Mitglieder von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

Bei der Gesamtstrukturvorbereitung werden außerdem die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Ausführliche Informationen zu rollenbasierten Zugriffssteuerungsrollen und den Aufgaben, die mit jeder dieser Rollen ausgeführt werden können, finden Sie unter [Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt. Private ACEs werden im Container mit den globalen Einstellungen erstellt, der von Lync Server verwendet wird. Dieser Container wird ausschließlich von Lync Server verwendet und befindet sich entweder im Konfigurationscontainer oder im Systemcontainer der Stammdomäne (abhängig davon, wo Sie die globalen Einstellungen speichern). Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgeführt.

### Von der Gesamtstruktur erstellte öffentliche ACEs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Systemcontainer in der Stammdomäne lesen (nicht vererbt)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>DisplaySpecifiers-Container der Konfiguration lesen (nicht vererbt)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <STRONG>*</STRONG>ACEs, die nicht vererbt werden, gewähren keinen Zugriff auf untergeordnete Objekte im betreffenden Container. ACEs, die vererbt werden, gewähren Zugriff auf untergeordnete Objekte im betreffenden Container.



Die Gesamtstrukturvorbereitung führt die folgenden Aufgaben im Konfigurationscontainer unter dem Namenskontext für die Konfiguration durch:

  - Hinzufügen eines Eintrags **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die Seite **RTC property** unter den Attributen "adminContextMenu" und "adminPropertyPages" des Anzeigebezeichners für Sprachen für Benutzer, Kontakte und InetOrgPersons (z. B.: CN=user-Display,CN=409,CN=DisplaySpecifiers)

  - Hinzufügen eines Objekts **RTCPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User- und Contact-Klassen angewendet wird

  - Hinzufügen eines Objekts **RTCUserSearchPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User-, Contact-, OU- und DomainDNS-Klassen angewendet wird

  - Hinzufügen von **msRTCSIP-PrimaryUserAddress** unter dem Attribut **extraColumns** der jeweiligen Anzeigebezeichner für die Sprachen der Organisationseinheit (z. B.: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) und Kopieren der Werte des Attributs **extraColumns** der Standardanzeige (z. B.: CN=default-Display, CN=409,CN=DisplaySpecifiers)

  - Hinzufügen der Filterattribute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** und **msRTCSIP-UserEnabled** unterhalb des Attributs **attributeDisplayNames** der jeweiligen Anzeigebezeichners für Sprachen für Benutzer-, Kontakt- und InetOrgPerson-Objekte (z. B. auf Englisch: CN=user-Display,CN=409,CN=DisplaySpecifiers)

