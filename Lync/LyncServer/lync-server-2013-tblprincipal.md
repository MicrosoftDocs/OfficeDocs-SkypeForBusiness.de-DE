---
title: 'Lync Server 2013: tblPrincipal'
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558667(v=OCS.15)
ms:contentKeyID: 49294491
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipal in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle "tblPrincipal" enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Die GUID des Prinzipals. Diese wird allgemein als alternativer Primärschlüssel verwendet, da sie auch im Active Directory-Domänendienste-Bereich von Bedeutung ist. (Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Der URI des Prinzipals. Für Benutzer wird das SIP-Schema verwendet, für fast alles andere das ma-grp-Schema.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der allgemeine Name. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Der Anzeigename. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Firmenname. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Die E-Mail-Adresse. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Der Domänenname des Active Directory-Objekts, von dem der Prinzipal eine zwischengespeicherte Version ist. Kann für Typen, die keine Active Directory-Objekte sind (z. B. Systembenutzer), null sein.</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von regulären Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><ul>
<li><p>0: Der Prinzipal ist aktiv.</p></li>
<li><p>1: Der Prinzipal ist deaktiviert, weil die SIP-Funktionen für den Benutzer deaktiviert sind.</p></li>
<li><p>2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Der Prinzipaltyp (aus der Tabelle &quot;tblPrincipalType&quot;).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Lync-Poolzuordnung für den Prinzipal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Server für beständigen Chat-Richtlinienwert für den Benutzer, wenn eine Tagtyprichtlinie vorhanden ist.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>Die Prinzipal-ID des Erstellers.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Der Zeitstempel für den Zeitpunkt der Erstellung.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Der Zeitstempel für die letzte Aktualisierung.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle &quot; tblPrincipalType.ptypeID&quot;.</p></td>
</tr>
</tbody>
</table>

