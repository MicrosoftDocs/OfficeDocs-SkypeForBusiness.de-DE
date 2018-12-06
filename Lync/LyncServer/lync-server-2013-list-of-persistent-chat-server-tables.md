---
title: 'Lync Server 2013: Liste der Tabellen für den Server für beständigen Chat'
TOCTitle: Liste der Tabellen für den Server für beständigen Chat
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558628(v=OCS.15)
ms:contentKeyID: 49293473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Beständiger Chat-Datenbankschema besteht aus den folgenden Tabellen.

## Active Directory-Synchronisierung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></p></td>
<td><p>Enthält die aktuellen LDAP-Synchronisierungscookies (Lightweight Directory Access-Protokoll). Jede Zeile entspricht einer Active Directory-Domänendienste-Domäne, die vom Server für beständigen Chat aktiv auf Änderungen überwacht wird. (Nur die für Server für beständigen Chat relevanten Active Directory-Domänen sind in dieser Tabelle aufgeführt.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></p></td>
<td><p>Enthält Gruppenmitgliedschaftsänderungen (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht mittels der späteren Active Directory-Synchronisierungsschritte verarbeitet wurden, und ist eine der temporären Tabellen (neben der <strong>tblADUpdates</strong> -Tabelle), die vom ersten Active Directory-Synchronisierungsschritt verwendet wird.</p>
<p>Mitgliedschaftsänderungen werden nur für Gruppen gespeichert und/oder verarbeitet, die in der <strong>tblPrincipal</strong> -Tabelle aufgelistet sind oder für die hier bereits Mitglieder aufgelistet sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></p></td>
<td><p>Enthält Änderungen der Active Directory-Domänendienste-Domänendienste, die noch nicht mittels der späteren Active Directory-Synchronisierungsschritte verarbeitet wurden, und ist eine der temporären Tabellen (neben der <strong>PrincipalMemberDifference</strong> -Tabelle), die vom ersten Active Directory-Synchronisierungsschritt verwendet wird.</p>
<p>Änderungen von Active Directory werden nur für Prinzipale gespeichert und/oder verarbeitet, die bereits in der <strong>tblPrincipal</strong> -Tabelle aufgelistet sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></p></td>
<td><p>Enthält Prinzipalmitgliedschaften.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></p></td>
<td><p>Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></p></td>
<td><p>Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, und zwar gewöhnlich aufgrund von Active Directory-Zugriffsfehlern.</p>
<p>Diese Tabelle dient nur zu Informationszwecken. Der Inhalt dieser Tabelle wird nicht verwendet.</p>
<p>Die Prinzipale mit Zugehörigkeiten, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der <strong>tblPrincipalMeta</strong> -Tabelle gespeichert und bei Gelegenheit aktualisiert.</p></td>
</tr>
</tbody>
</table>


## Prinzipale, Zugehörigkeiten, Knoten, Bereiche und Rollen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></p></td>
<td><p>Enthält Prinzipaltypen zur Kategorisierung des Inhalts der Tabelle <strong>tblPrincipal</strong> . Diese Tabelle ist statisch. Sie wird beim Erstellen der Datenbank eingerichtet und nicht geändert.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></p></td>
<td><p>Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.). Der Server für beständigen Chat behandelt diese als unstrukturierte, heterogene List. Verschiedene Spalten basieren auf dem Typ des jeweiligen Prinzipals.</p>
<p>Die meisten dieser Prinzipale sind zwischengespeicherte Kopien von in Active Directory gespeicherten Objekten. Das Erstellen der zwischengespeicherten Kopie in der <strong>Principal</strong> -Tabelle dieser Active Directory-Objekte wird als <em>Bereitstellung</em> bezeichnet.</p>
<p>Einige Prinzipale werden im Vergleich zu anderen Prinzipalen offensiver erstellt, und einige Active Directory-Objekte werden vollständig ignoriert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></p></td>
<td><p>Enthält Prinzipalzugehörigkeiten, welche die Mitgliedschaft bei Active Directory-Sicherheitsgruppen, Active Directory-Containern, Verbundgruppen usw. beschreiben.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></p></td>
<td><p>Enthält den Kategorieknoten, wie in Lync Server-Systemsteuerung definiert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></p></td>
<td><p>Enthält Rollentypen und die zugehörigen Berechtigungsgruppen. Diese Nachschlagetabelle ist statisch.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></p></td>
<td><p>Enthält Bereiche, die Knoten zugewiesen sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></p></td>
<td><p>Enthält Rollen, die Knoten zugewiesen sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></p></td>
<td><p>Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></p></td>
<td><p>Enthält nur die hartcodierten Attribute <strong>Visibility</strong> und <strong>Behavior</strong> , die in der <strong>tblNode</strong> -Tabelle verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></p></td>
<td><p>Enthält die Werte der hartcodierten Attribute <strong>Visibility</strong> und <strong>Behavior</strong> , die in der <strong>tblNode</strong> -Tabelle verwendet werden.</p></td>
</tr>
</tbody>
</table>


## Einladungen, Chats und sonstige Clientunterstützung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></p></td>
<td><p>Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten mit aktivierter automatischer Einladung.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></p></td>
<td><p>Enthält alle Chatnachrichten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></p></td>
<td><p>Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der <strong>tblPrincipalInvite</strong> -Tabelle) verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></p></td>
<td><p>Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der <strong>tblChat</strong> -Tabelle) verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></p></td>
<td><p>Enthält Benutzerclienteinstellungen (nur von Legacyclients verwendet).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></p></td>
<td><p>Enthält temporäre Token für Dateiübertragungszwecke. Jedes Mal, wenn eine Datei hoch- oder heruntergeladen wird, generiert der Beständiger Chat-Dienst ein Token, das der Client für den Zugriff auf den Webdienste-Dateispeicher verwendet.</p></td>
</tr>
</tbody>
</table>


## Serverunterstützung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></p></td>
<td><p>Enthält die aktiven Server im Serverpool für beständigen Chat-Pool.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></p></td>
<td><p>Enthält die Administratorsperre für die Ausführung einiger Administratorbefehle. Der Systemrevisionseintrag in der <strong>tblSystemRevision</strong> -Tabelle wird nach jeder Freigabe der Sperre schrittweise erhöht.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></p></td>
<td><p>Enthält den Revisionsnummerneintrag, der (zusammen mit der <strong>AdminLock</strong> -Tabelle) zur Einhaltung der Konsistenz bei mehreren Servern verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Peer-zu-Peer-Verbindungen zwischen Beständiger Chat-Diensten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></p></td>
<td><p>Enthält die nicht unterstützte Server für beständigen Chat-Konfiguration.</p></td>
</tr>
</tbody>
</table>

