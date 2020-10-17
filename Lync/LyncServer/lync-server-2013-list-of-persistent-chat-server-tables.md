---
title: 'Lync Server 2013: Liste der Server Tabellen für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da3069fdd039cb394308f3901ae9805b9023e15d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513882"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Liste der Server Tabellen für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Das Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.

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
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie in lync Server 2013</a></p></td>
<td><p>Enthält die aktuellen LDAP-Synchronisierungscookies (Lightweight Directory Access-Protokoll). Jede Zeile entspricht einer Active Directory-Domänendienste Domäne, die der Server für beständigen Chat aktiv auf Änderungen überwacht. (In dieser Tabelle werden nur die Active Directory Domänen dargestellt, die für den Server für beständigen Chat relevant sind.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">principalmemberdifference in lync Server 2013</a></p></td>
<td><p>Enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblADUpdates-Tabelle) sind, die im ersten Schritt der Active Directory Synchronisierung verwendet werden.</p>
<p>Mitgliedschaftsänderungen werden nur für Gruppen gespeichert und/oder verarbeitet, die in der  tblPrincipal-Tabelle aufgelistet sind oder für die hier bereits Mitglieder aufgelistet sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates in lync Server 2013</a></p></td>
<td><p>Enthält Änderungen an Active Directory-Domänendienste, die von den späteren Active Directory Synchronisierungs Schritten noch nicht verarbeitet wurden und eine der temporären Tabellen (zusammen mit der principalmemberdifference-Tabelle) sind, die im ersten Schritt der Active Directory Synchronisierung verwendet werden.</p>
<p>Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beide, die bereits in der tblPrincipal-Tabelle aufgeführt sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in lync Server 2013</a></p></td>
<td><p>Enthält Prinzipalmitgliedschaften.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in lync Server 2013</a></p></td>
<td><p>Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in lync Server 2013</a></p></td>
<td><p>Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, in der Regel aufgrund von Active Directory Zugriffsfehlern.</p>
<p>Diese Tabelle dient nur zu Informationszwecken. Der Inhalt dieser Tabelle wird nicht verwendet.</p>
<p>Die Prinzipale mit Zugehörigkeiten, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle gespeichert und bei Gelegenheit aktualisiert.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Prinzipale, Zugehörigkeiten, Knoten, Bereiche und Rollen


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
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in lync Server 2013</a></p></td>
<td><p>Enthält Prinzipaltypen zur Kategorisierung des Inhalts der Tabelle tblPrincipal. Diese Tabelle ist statisch. Sie wird beim Erstellen der Datenbank eingerichtet und nicht geändert.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal in lync Server 2013</a></p></td>
<td><p>Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.). Der Server für beständigen Chat verarbeitet dies als flache heterogene Liste. Verschiedene Spalten basieren auf dem Typ des jeweiligen Prinzipals.</p>
<p>Die meisten dieser Prinzipale sind zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind. Das Erstellen der zwischengespeicherten Kopie in der Prinzipal Tabelle dieser Active Directory-Objekte wird als <em>Provision</em>bezeichnet.</p>
<p>Einige Prinzipale werden aggressiver als andere erstellt, und einige Active Directory-Objekte werden insgesamt ignoriert.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in lync Server 2013</a></p></td>
<td><p>Enthält Haupt Zuordnungen, in denen Mitgliedschaften in Active Directory Sicherheitsgruppen, in Active Directory Container usw. beschrieben werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode in lync Server 2013</a></p></td>
<td><p>Enthält den Category-Knoten, der in lync Server-Systemsteuerung verwaltet wird.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType in lync Server 2013</a></p></td>
<td><p>Enthält Rollentypen und die zugehörigen Berechtigungsgruppen. Diese Nachschlagetabelle ist statisch.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in lync Server 2013</a></p></td>
<td><p>Enthält Bereiche, die Knoten zugewiesen sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in lync Server 2013</a></p></td>
<td><p>Enthält Rollen, die Knoten zugewiesen sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in lync Server 2013</a></p></td>
<td><p>Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in lync Server 2013</a></p></td>
<td><p>Enthält nur die hartcodierten &quot; Sichtbarkeits &quot; -und &quot; Verhaltens &quot; Attribute, die in der tblNode-Tabelle verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in lync Server 2013</a></p></td>
<td><p>Enthält die Werte der hartcodierten &quot; Sichtbarkeits-und Verhaltens &quot; Attribute, die in der tblNode-Tabelle verwendet werden.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Einladungen, Chats und sonstige Clientunterstützung


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
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in lync Server 2013</a></p></td>
<td><p>Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten mit aktivierter automatischer Einladung.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat in lync Server 2013</a></p></td>
<td><p>Enthält alle Chatnachrichten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in lync Server 2013</a></p></td>
<td><p>Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvite-Tabelle) verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in lync Server 2013</a></p></td>
<td><p>Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle) verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference in lync Server 2013</a></p></td>
<td><p>Enthält Benutzerclienteinstellungen (nur von Legacyclients verwendet).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken in lync Server 2013</a></p></td>
<td><p>Enthält temporäre Token für Dateiübertragungszwecke. Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der beständige Chat Dienst ein Token, das der Client für den Zugriff auf den Webdienstdatei Speicher verwendet.</p></td>
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
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in lync Server 2013</a></p></td>
<td><p>Enthält die aktiven Server im Serverpool für beständigen Chat.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">adminlock in lync Server 2013</a></p></td>
<td><p>Enthält die Administratorsperre für die Ausführung einiger Administratorbefehle. Der Systemrevisionseintrag in der tblSystemRevision -Tabelle wird nach jeder Freigabe der Sperre schrittweise erhöht.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in lync Server 2013</a></p></td>
<td><p>Enthält den Revisionsnummerneintrag, der (zusammen mit der AdminLock-Tabelle) zur Einhaltung der Konsistenz bei mehreren Servern verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Peer-to-Peer-Verbindungen zwischen beständigen Chat Diensten.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig in lync Server 2013</a></p></td>
<td><p>Enthält die nicht unterstützte Konfiguration für den beständigen Chat Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

