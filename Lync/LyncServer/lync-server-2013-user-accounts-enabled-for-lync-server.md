---
title: Benutzerkonten, die für Lync Server 2013 aktiviert sind
TOCTitle: Benutzerkonten, die für Lync Server 2013 aktiviert sind
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182543(v=OCS.15)
ms:contentKeyID: 49294561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Benutzerkonten, die für Lync Server 2013 aktiviert sind

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In den Themen des vorliegenden Abschnitts werden schrittweise Anleitungen zum Konfigurieren von Benutzereinstellungen über die Systemsteuerung für Lync Server 2013 vorgestellt.


> [!IMPORTANT]
> Benutzer, die Mitglieder der Active Directory-Gruppe "Domänen-Admins" sind, können nicht über die Lync Server-Systemsteuerung verwaltet werden. Für Domänen-Admins kann die Lync Server-Systemsteuerung lediglich zum Ausführen von Suchoperationen (nur Lesezugriff) verwendet werden. Zum Ausführen von Schreiboperationen für Domänen-Admins (z.&nbsp;B. zum Aktivieren oder Deaktivieren dieser Benutzer für Lync Server-Systemsteuerung oder zum Ändern von Pool- oder Richtlinienzuweisungen, Telefonieeinstellungen oder SIP-Adresse) müssen Sie die Cmdlets der Windows PowerShell verwenden und sich als Domänen-Admin anmelden. Ausführliche Informationen zum Verwenden der Cmdlets in der Windows PowerShell für die Verwaltung von Benutzern finden Sie unter <A href="lync-server-2013-lync-server-management-shell.md">Lync Server-Verwaltungsshell</A>.



Wenn Sie Lync Server 2013-Verwaltungsaufgaben ausführen, die die Suche nach einem Benutzer oder das Filtern von Ergebnissen der Benutzersuche umfassen, gibt es einige Benutzereigenschaften, die als Attribute in Active Directory-Domänendienste vorhanden sind, jedoch erst mit der Bereitstellung von Microsoft Exchange Server in den globalen Katalog repliziert werden. Microsoft Exchange, nicht Lync Server, kennzeichnet die folgenden Attribute für die Replikation in den globalen Katalog bei der Installation:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzerinformationen</th>
<th>Adresse und Telefon</th>
<th>Organisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initialen</p></td>
<td><p>Adresse</p>
<p>Land/Region</p>
<p>Pager</p>
<p>Fax</p>
<p>Mobil</p></td>
<td><p>Titel</p>
<p>Unternehmen</p>
<p>Abteilung</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


## In diesem Abschnitt

  - [Anzeigen von Informationen zu Benutzerkonten, die für Lync Server 2013 aktiviert sind](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Aktivieren und Deaktivieren von Benutzern für Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Verwalten von Enterprise-VoIP für Benutzer](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Ändern der Eigenschaften von Benutzerkonten](lync-server-2013-modifying-user-account-properties.md)

  - [Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)

## Siehe auch

#### Konzepte

[Cmdlets für die Benutzerverwaltung](lync-server-2013-user-management-cmdlets.md)  

#### Weitere Ressourcen

[Verwalten von Benutzern in Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)

