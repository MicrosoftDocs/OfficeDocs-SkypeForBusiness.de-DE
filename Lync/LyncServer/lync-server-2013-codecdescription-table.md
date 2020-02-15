---
title: 'Lync Server 2013: CodecDescription-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be7b878d3d9b6457fbda7a081db9b6b6cb80314
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a>CodecDescription-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-17_

Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs Ihrem entsprechenden Codec zu. Codecs werden zur Codierung digitaler Signale für die Übertragung und Ausstrahlung verwendet und dann zur Dekodierung dieser Signale für die Wiedergabe. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID, die dem Codec zugewiesen ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Eigen</p></td>
<td><p>Eindeutige Beschreibung des Codecs, der dem  CodecDescriptionKey entspricht.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

