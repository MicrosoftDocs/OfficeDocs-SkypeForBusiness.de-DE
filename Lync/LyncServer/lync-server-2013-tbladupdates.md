---
title: 'Lync Server 2013: tblADUpdates'
description: 'Lync Server 2013: tblADUpdates.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573681"
---
# <a name="tbladupdates-in-lync-server-2013"></a>tblADUpdates in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblADUpdates enthält Active Directory-Domänendienste Änderungen, die von den späteren Active Directory Synchronisierungs Schritten noch nicht verarbeitet wurden.

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
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Prinzipal-GUID des geänderten Objekts.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), nicht NULL</p></td>
<td><p>Distinguished Name (DN) des Objekts.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn sich mindestens ein Attribut des Objekts geändert hat.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn sich die Mitgliedschaft geändert hat.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>Nicht verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn das Objekt gelöscht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Zeitstempel für den Zeitpunkt, an dem die Zeile eingefügt wurde.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

