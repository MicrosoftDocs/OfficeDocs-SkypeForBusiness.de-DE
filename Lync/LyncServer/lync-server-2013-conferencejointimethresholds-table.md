---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>ConferenceJoinTimeThresholds-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden. Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:

  - Weniger als 2 Sekunden.

  - Zwischen 2 Sekunden und 5 Sekunden.

  - Zwischen 5 Sekunden und 10 Sekunden.

  - Mehr als 10 Sekunden.

Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungs Werte 2 Sekunden, 5 Sekunden und 10 Sekunden.

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
<td><p>Eindeutiger Bezeichner für die Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Obergrenze für die Klassifizierung. Gültige Werte sind:</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

