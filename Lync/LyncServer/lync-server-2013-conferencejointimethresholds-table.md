---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle'
description: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561671"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>ConferenceJoinTimeThresholds-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:

  - Weniger als 2 Sekunden.

  - Zwischen 2 Sekunden und 5 Sekunden.

  - Zwischen 5 Sekunden und 10 Sekunden.

  - Mehr als 10 Sekunden.

Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungswerte 2 Sekunden, 5 Sekunden und 10 Sekunden.

Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>Schwellenwert</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID für die Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Schwellenwert</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Oberer Grenzwert für die Klassifizierung. Gültige Werte sind:</p>
<ol>
<li><p>2</p></li>
<li><p>5 </p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

