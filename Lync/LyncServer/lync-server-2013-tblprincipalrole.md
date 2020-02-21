---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685e8ae3e767e3dc237da1698fd593a9c56021c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>tblPrincipalRole in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblPrincipalRole enthält explizite Rollen, die Knoten zugeordnet sind.

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
<td><p>prinRoleNodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID, auf die sich die Rolle bezieht.</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int, not null</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Rollentyp-ID (von tblRoleType).</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</p></td>
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
<td><p>&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

