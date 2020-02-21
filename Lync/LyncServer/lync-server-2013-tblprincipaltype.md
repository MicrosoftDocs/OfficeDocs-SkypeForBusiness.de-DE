---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblPrincipalType enthält Prinzipaltypen zur Kategorisierung des Inhalts der tblPrincipal-Tabelle.

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
<td><p>ptypeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Prinzipaltyp-ID</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Beschreibung des Typs.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn es sich beim Typ um einen Benutzertyp handelt.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

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
<td><p>ptypeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Prinzipalwerte

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Rolle</th>
<th>Beschreibung</th>
<th>Benutzer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Any</p></td>
<td><p>Allgemeiner Prinzipal ohne bekannten Typ. Keine Verwendung in tblPrincipal-Tabelle.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Allgemeiner Prinzipal vom Typ Benutzer. Keine Verwendung in tblPrincipal-Tabelle.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Allgemeiner Prinzipal mit Gruppensemantik. Keine Verwendung in tblPrincipal-Tabelle.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Multiswitch</p></td>
<td><p>Prinzipal, der intern vom Server für beständigen Chat verwendet wird.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Benutzer</p></td>
<td><p>Regelmäßiger Benutzer.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>Gleichstrom</p></td>
<td><p>Active Directory-Domänendienste Domänencontroller.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Group</p></td>
<td><p>Active Directory-Sicherheitsgruppe</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>Ordner</p></td>
<td><p>Active Directory-Container oder Organisationseinheit</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[tblPrincipal in lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

