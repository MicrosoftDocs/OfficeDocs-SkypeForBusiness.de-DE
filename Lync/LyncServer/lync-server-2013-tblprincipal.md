---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblPrincipal enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.

### <a name="columns"></a>Spalten

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
<td><p>Prinzipal-ID.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Prinzipal-GUID. Dies wird im Allgemeinen als alternativer Primärschlüssel verwendet, da dessen Bedeutung in den Bereich der Active Directory-Domänendienste überschritten wird. (Die GUID für einen zwischengespeicherten Prinzipal entspricht der entsprechenden GUID des Active Directory-Objekts.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Prinzipal-URI. Das SIP-Schema wird für Benutzer verwendet, und MA-GRP wird für fast alles andere verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Allgemeiner Name Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Anzeigename Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name des Unternehmens. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>E-Mail. Wird nur von Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Der Domänenname des Active Directory-Objekts, in dem der Prinzipal eine zwischengespeicherte Version von ist. Kann NULL für Typen sein, die keine Active Directory-Objekte (wie Systembenutzer) sind.</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von normalen Benutzertypen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><ul>
<li><p>0: Principal ist aktiv.</p></li>
<li><p>1: Principal ist deaktiviert, da die SIP-Funktionen des Benutzers deaktiviert sind.</p></li>
<li><p>2: Principal wird gelöscht, weil das zugeordnete anzeigen Objekt gelöscht wurde.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Principal Type (aus tblPrincipalType-Tabelle).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Lync-Pool Aufgabe für den Prinzipal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Server Richtlinienwert des beständigen Chats für Benutzer, wenn die Kategorie-typrichtlinie vorhanden ist.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>Prinzipal-ID des Erstellers.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel für die Erstellungszeit.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>Die ID des Prinzipals, der diesen zuletzt aktualisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel für das letzte Update.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>DateTime, nicht NULL</p></td>
<td><p>Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Schlüssel

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
<td><p>Fremdschlüssel mit Lookup in der tblPrincipalType. ptypeID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

