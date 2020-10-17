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
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523762"
---
# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.

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
<td><p>Die Prinzipal-ID.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Die GUID des Prinzipals. Dies wird weitgehend als alternativer Primärschlüssel verwendet, da die Bedeutung in den Active Directory-Domänendienste Raum überschreitet. (Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), not null</p></td>
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
<td><p>smallint, not null</p></td>
<td><ul>
<li><p>0: Der Prinzipal ist aktiv.</p></li>
<li><p>1: Der Prinzipal ist deaktiviert, weil die SIP-Funktionen für den Benutzer deaktiviert sind.</p></li>
<li><p>2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Der Prinzipaltyp (aus der Tabelle „tblPrincipalType“).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Lync-Poolzuweisung für den Prinzipal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Server Richtlinienwert für beständigen Chat für Benutzer, wenn die Transpondertyp Richtlinie vorhanden ist.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>Die Prinzipal-ID des Erstellers.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>Der Zeitstempel für den Zeitpunkt der Erstellung.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>Der Zeitstempel für die letzte Aktualisierung.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, not null</p></td>
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
<td><p>Der Primärschlüssel.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle „ tblPrincipalType.ptypeID“.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

