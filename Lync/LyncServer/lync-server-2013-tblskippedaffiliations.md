---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31997276c95fb3908ab33d0a21017833f10fddcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a>tblSkippedAffiliations in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblSkippedAffiliations enthält die Zugehörigkeiten, die nicht gelesen werden konnten (in der Regel aufgrund von Active Directory-Domänendienste Zugriffsfehlern).

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
<td><p>int, not null</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Zeichenfolge, die die Zuordnung identifiziert.</p>
<p>Das Format lautet: GUID: {0} URI: {1} &gt; ID:{2}</p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</p></td>
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
<th>Spalte (n)</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

