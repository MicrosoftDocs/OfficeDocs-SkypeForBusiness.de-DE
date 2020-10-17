---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2ef70b70ff496852a753a9e15a38f80de1509b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523742"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>tblPrincipalAffiliations in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblPrincipalAffiliations enthält die Haupt Zuordnungen, in denen Mitgliedschaften an Standorten, einschließlich Active Directory-Domänendienste Sicherheitsgruppen, in Active Directory Containern in Domänen beschrieben werden.

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
<td><p>principalID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des zugeordneten Prinzipals.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, die für die Zuordnung steht. Jeder Prinzipal (ausgenommen system-user-types) verfügt auch über eine Selbstzuordnung.</p></td>
</tr>
<tr class="odd">
<td><p>Index</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Index. Der Wert für Self-Affiliations ist-1, und bei den anderen Zuordnungen steigt er nacheinander von 1 innerhalb der einzelnen &lt; affiliationId- &gt; Buckets an.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal, der die letzte Aktualisierung durchführte. Der Wert ist in der Regel 1, was der Active Directory-Synchronisierung entspricht.</p></td>
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
<td><p>principalID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

