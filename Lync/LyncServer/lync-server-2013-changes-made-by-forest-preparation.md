---
title: 'Lync Server 2013: von der Gesamtstrukturvorbereitung vorgenommene Änderungen'
description: 'Lync Server 2013: von der Gesamtstrukturvorbereitung vorgenommene Änderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543651"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommene Änderungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

Dieser Abschnitt enthält eine Beschreibung der globalen Einstellungen und Objekte und der universellen Dienst- und Verwaltungsgruppen, die bei der Gesamtstrukturvorbereitung erstellt werden.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Globale Einstellungen und Objekte in Active Directory

Wenn Sie globale Einstellungen im Container "Configuration" (wie bei allen neuen lync Server 2013-Bereitstellungen) speichern, verwendet die Gesamtstrukturvorbereitung den vorhandenen Dienste-Container und fügt unter dem Objekt "Configuration Services" ein **RTC-Dienst** Objekt hinzu \\ . Unterhalb des Objekts "RTC Service" wird bei der Gesamtstrukturvorbereitung ein Objekt **Global Settings** vom Typ "msRTCSIP-GlobalContainer" hinzugefügt. Das Global Settings-Objekt umfasst alle Einstellungen, die für die lync Server-Bereitstellung gelten. Wenn Sie globale Einstellungen im Systemcontainer speichern, verwendet die Gesamtstrukturvorbereitung einen Microsoft-Container unter dem Stammdomänen-Systemcontainer und ein RTC-Dienstobjekt unter dem Microsoft-System \\ Objekt.

Außerdem wird während der Gesamtstrukturvorbereitung ein neues Objekt **msRTCSIP-Domain** für die Stammdomäne hinzugefügt, in der das Verfahren ausgeführt wird.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Universelle Dienst- und Verwaltungsgruppen in Active Directory

Die Gesamtstrukturvorbereitung erstellt universelle Gruppen anhand der von Ihnen angegebenen Domäne und fügt Zugriffssteuerungseinträge (Access Control Entries, ACEs) für diese Gruppen hinzu. In diesem Schritt werden die universellen Gruppen in den Benutzercontainern der Domäne erstellt, die Sie angegeben haben.

Anhand von universellen Gruppen können Administratoren globale Einstellungen und Dienste verwenden und verwalten. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:

  - **Administrative Gruppen**     Diese Gruppen definieren Administratorrollen für ein lync Server Netzwerk.

  - **Infrastrukturgruppen**     Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server Infrastruktur. Sie fungieren als Komponenten von administrativen Gruppen. Sie sollten diese Gruppen weder ändern noch direkt Benutzer zu ihnen hinzufügen.

  - **Dienstgruppen**     Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene lync Server Dienste erforderlich sind.

In der folgenden Tabelle werden die administrativen Gruppen beschrieben.

### <a name="administrative-groups-created-during-forest-preparation"></a>Administrative Gruppen, die während der Gesamtstrukturvorbereitung erstellt werden

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

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Infrastrukturgruppen, die während der Gesamtstrukturvorbereitung erstellt werden

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
<td><p>Gewährt Schreibzugriff auf globale Einstellungsobjekte für lync Server.</p></td>
</tr>
<tr class="even">
<td><p>"RTCUniversalGlobalReadOnlyGroup"</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf globale Einstellungsobjekte für lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server Benutzereinstellungen.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server Einstellungen. Diese Gruppe hat keinen Zugriff auf die Einstellungen auf Poolebene, sondern lediglich auf Einstellungen für einzelne Server.</p></td>
</tr>
<tr class="odd">
<td><p>Gruppe "rtcuniversalsbatechnicians</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server Konfiguration und wird während der Installation in der lokalen Gruppe Administratoren der Survivable Branch Appliances gespeichert.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Dienstgruppen beschrieben.

### <a name="service-groups-created-during-forest-preparation"></a>Dienstgruppen, die während der Gesamtstrukturvorbereitung erstellt werden

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
<td><p>Enthält Dienstkonten, die zum Ausführen von Front-End-Server-und Standard Edition-Servern verwendet werden. Diese Gruppe ermöglicht Servern Lese-/Schreibzugriff auf lync Server globalen Einstellungen und Active Directory Benutzerobjekten.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die zum Ausführen von A/V-Konferenzservern, Webdienste, Vermittlungsserver, Archivierungsserver und Monitoring Server verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die zum Ausführen lync Server Edgeserver verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Enthält Server, die an lync Server Replikation des zentralen Verwaltungsspeichers teilnehmen können.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server Einstellungen, ermöglicht jedoch die Konfiguration für die Installation eines Survivable Branch Servers und einer Survivable Branch Appliance-Bereitstellung.</p></td>
</tr>
</tbody>
</table>


Die Gesamtstrukturvorbereitung fügt den entsprechenden Infrastrukturgruppen dann wie folgt Dienst- und Verwaltungsgruppen hinzu:

  - "RTCUniversalServerAdmins" wird zu "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalGlobalWriteGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

  - "RTCUniversalUserAdmins" wird als Mitglied von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

  - "RTCHSUniversalServices", "RTCComponentUniversalServices" und "RTCUniversalReadOnlyAdmins" werden als Mitglieder von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.

Bei der Gesamtstrukturvorbereitung werden außerdem die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:

  - CSAdministrator

  - Csarchivingadministrator "

  - "Cshelpdesk"

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - Rolle csresponsegroupmanager

Ausführliche Informationen zu RBAC-Rollen und den jeweils zulässigen Aufgaben finden Sie unter [Planning for Role-Based Access Control in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt. Es erstellt private ACEs im Container "globale Einstellungen", der von lync Server verwendet wird. Dieser Container wird nur von lync Server verwendet und befindet sich in Abhängigkeit davon, wo Sie globale Einstellungen speichern, entweder im Konfigurationscontainer oder im System Container in der Stammdomäne. Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgeführt.

### <a name="public-aces-created-by-forest-preparation"></a>Von der Gesamtstruktur erstellte öffentliche ACEs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>"RTCUniversalGlobalReadOnlyGroup"</th>
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


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Nicht geerbte ACEs gewähren keinen Zugriff auf untergeordnete Objekte unterhalb dieser Container. ACEs, die vererbt werden, gewähren Zugriff auf untergeordnete Objekte im betreffenden Container.



</div>

Die Gesamtstrukturvorbereitung führt die folgenden Aufgaben im Konfigurationscontainer unter dem Namenskontext für die Konfiguration durch:

  - Hinzufügen eines Eintrags **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die Seite **RTC property** unter den Attributen "adminContextMenu" und "adminPropertyPages" des Anzeigebezeichners für Sprachen für Benutzer, Kontakte und InetOrgPersons (z. B.: CN=user-Display,CN=409,CN=DisplaySpecifiers)

  - Hinzufügen eines Objekts **RTCPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User- und Contact-Klassen angewendet wird

  - Hinzufügen eines Objekts **RTCUserSearchPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User-, Contact-, OU- und DomainDNS-Klassen angewendet wird

  - Hinzufügen von **msRTCSIP-PrimaryUserAddress** unter dem Attribut **extraColumns** der jeweiligen Anzeigebezeichner für die Sprachen der Organisationseinheit (z. B.: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) und Kopieren der Werte des Attributs **extraColumns** der Standardanzeige (z. B.: CN=default-Display, CN=409,CN=DisplaySpecifiers)

  - Hinzufügen der Filterattribute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** und **msRTCSIP-UserEnabled** unterhalb des Attributs **attributeDisplayNames** der jeweiligen Anzeigebezeichners für Sprachen für Benutzer-, Kontakt- und InetOrgPerson-Objekte (z. B. auf Englisch: CN=user-Display,CN=409,CN=DisplaySpecifiers)

</div>

</div>

<span> </span>

</div>

</div>

</div>

