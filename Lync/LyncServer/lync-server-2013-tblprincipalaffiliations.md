---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>tblPrincipalAffiliations in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.

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
<td><p>Prinzipal-Nr</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des verbundenen Prinzipals.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des Prinzipals, der die Zuordnung darstellt. Jeder Prinzipal (mit Ausnahme von System-User-Typen) hat ebenfalls eine Selbstzuordnung.</p></td>
</tr>
<tr class="odd">
<td><p>Index</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Index. Der Wert für Self-Affiliations ist-1, und für die anderen Zuordnungen wird er sequenziell von 1 innerhalb der einzelnen &lt;Prinzipal-affiliationId&gt; -Buckets erhöht.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal, der das neueste Update durchführte. Dies ist normalerweise 1, was bedeutet, dass die Active Directory-Synchronisierung erfolgt.</p></td>
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
<th>Spalten</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Prinzipal-, Index-, affiliationID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>Prinzipal-Nr</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

