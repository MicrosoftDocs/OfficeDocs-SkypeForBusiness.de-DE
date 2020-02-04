---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a>tblPrincipalMeta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn Prinzipal Attribute aktualisiert werden müssen.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn der Prinzipal gelöscht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>datetime</p></td>
<td><p>Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</p></td>
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
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

