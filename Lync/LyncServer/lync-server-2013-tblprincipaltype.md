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
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.

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
<td><p>Prinzipaltyp-ID.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Beschreibung des Typs.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn der Typ den Prinzipalen entspricht, die für interne Zwecke verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn es sich bei dem Typ um einen Benutzertyp handelt.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Schlüssel

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


### <a name="principal-values"></a>Prinzipal Werte

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
<th>User</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Beliebig</p></td>
<td><p>Generischer Prinzipal ohne bekannten Typ. Wird in der tblPrincipal-Tabelle nicht verwendet.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Generisches Prinzipal des Benutzertyps. Wird in der tblPrincipal-Tabelle nicht verwendet.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Generischer Prinzipal mit Gruppen Semantik Wird in der tblPrincipal-Tabelle nicht verwendet.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Multiswitch</p></td>
<td><p>Prinzipal, der intern vom beständigen Chat Server verwendet wird.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Benutzer</p></td>
<td><p>Normaler Benutzer.</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Active Directory-Domänendienste-Domänencontroller.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Gruppe</p></td>
<td><p>Active Directory-Sicherheitsgruppe.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Ordner</p></td>
<td><p>Active Directory-Container oder-Organisationseinheit.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[tblPrincipal in Lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

