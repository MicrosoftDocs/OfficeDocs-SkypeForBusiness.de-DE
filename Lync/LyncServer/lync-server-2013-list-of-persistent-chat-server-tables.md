---
title: 'Lync Server 2013: Liste der Tabellen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d5c16160d51373fe1eef5b7cbaefe728b904545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Das Datenbank-Schema des beständigen Chats besteht aus den folgenden Tabellen.

<div>

## <a name="active-directory-sync"></a>Active Directory-Synchronisierung


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
<td><p>Enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol). Jede Zeile entspricht einer Active Directory-Domänendienst Domäne, die vom beständigen Chat Server aktiv auf Änderungen überwacht wird. (In dieser Tabelle werden nur die Active Directory-Domänen dargestellt, die für den beständigen Chat Server relevant sind.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></p></td>
<td><p>Enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblADUpdates-Tabelle) sind, die im ersten Schritt der Active Directory-Synchronisierung verwendet werden.</p>
<p>Mitgliedschaftsänderungen werden gespeichert, verarbeitet oder beides, nur für Gruppen, die in der tblPrincipal-Tabelle aufgelistet sind oder in denen bereits Mitglieder aufgelistet sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></p></td>
<td><p>Enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblPrincipalMemberDifference-Tabelle) sind, die im ersten Schritt von Active Directory verwendet werden. Synchronisieren.</p>
<p>Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beides, die bereits in der tblPrincipal-Tabelle aufgeführt sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></p></td>
<td><p>Enthält Prinzipal Mitgliedschaften.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></p></td>
<td><p>Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></p></td>
<td><p>Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, in der Regel aufgrund von Active Directory-Zugriffsfehlern.</p>
<p>Diese Tabelle dient nur zu Informationszwecken. Der Inhalt wird nicht verwendet.</p>
<p>Die Prinzipale mit Zuordnungen, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle aufbewahrt und erhalten eine weitere Chance, aktualisiert zu werden.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Prinzipale, Zuordnungen, Knoten, Bereiche und Rollen


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
<td><p>Enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist. Diese Tabelle ist statisch. Sie wird während der Datenbankerstellung eingerichtet und ändert sich nicht.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></p></td>
<td><p>Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.). Der Server für beständigen Chat behandelt dies als flache heterogene Liste. Verschiedene Spalten basieren auf dem Typ jedes Prinzipals.</p>
<p>Bei den meisten dieser Prinzipale handelt es sich um zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind. Das Erstellen der zwischengespeicherten Kopie in der Prinzipal Tabelle dieser Active Directory-Objekte wird als <em>Bereitstellung</em>bezeichnet.</p>
<p>Einige Prinzipale werden aggressiver als andere erstellt, und einige Active Directory-Objekte werden insgesamt ignoriert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></p></td>
<td><p>Enthält Haupt Zuordnungen, die Mitgliedschaften in Active Directory-Sicherheitsgruppen, Active Directory-Container usw. beschreiben.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></p></td>
<td><p>Enthält den Kategorie-Knoten, wie in der lync Server-Systemsteuerung verwaltet.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></p></td>
<td><p>Enthält Rollentypen und die zugehörigen Berechtigungssätze. Diese Nachschlagetabelle ist statisch.</p></td>
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
<td><p>Enthält nur die hart &quot;codierten&quot; Sichtbarkeits-und &quot;Verhaltens&quot; Attribute, die in der tblNode-Tabelle verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></p></td>
<td><p>Enthält die Werte der hartcodierten &quot;Sichtbarkeits-und Verhaltens&quot; Attribute, die in der tblNode-Tabelle verwendet werden.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Einladungen, Chats und andere Client Unterstützung


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
<td><p>Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten, bei denen die automatische Einladung aktiviert ist.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></p></td>
<td><p>Enthält alle Chatnachrichten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></p></td>
<td><p>Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></p></td>
<td><p>Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></p></td>
<td><p>Enthält Benutzer-Client-Einstellungen (nur von Legacy-Clients verwendet).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></p></td>
<td><p>Enthält temporäre Token für Datei Übertragungs Zwecke. Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der beständige Chat Dienst ein Token, das der Client für den Zugriff auf den Webdienst-Dateispeicher verwendet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Serverunterstützung


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
<td><p>Enthält die aktiven Server im Server Pool für beständigen Chat.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></p></td>
<td><p>Enthält die administratorsperre zum Ausführen einiger Administrator Befehle. Der systemrevision-Eintrag in der tblSystemRevision-Tabelle wird nach jeder Version der Sperre inkrementiert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></p></td>
<td><p>Enthält den Eintrag für die Revisionsnummer (zusammen mit der tblAdminLock-Tabelle), um die Konsistenz auf mehreren Servern zu erreichen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Peer-to-Peer-Verbindungen zwischen beständigen Chat Diensten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></p></td>
<td><p>Enthält die Konfiguration des beständigen Chat Servers, die nicht unterstützt wird.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

