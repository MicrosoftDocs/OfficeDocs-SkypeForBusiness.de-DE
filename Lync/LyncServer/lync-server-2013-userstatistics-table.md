---
title: 'Lync Server 2013: UserStatistics-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876d861e62014738816c02e2a6c2628f5dd46fc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>UserStatistics-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Die UserStatistics-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über die Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Der letzte Zeitpunkt, an dem sich der Benutzer angemeldet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisierte.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler aufgetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erfuhr.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

