---
title: 'Lync Server 2013: traceroute-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>TraceRoute-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-21_

Die traceroute-Tabelle enthält Routinginformationen aus anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Das Datum und die Uhrzeit, zu der der Anruf begonnen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Eindeutiger Bezeichner, der verwendet wird, um zwischen mehreren Anrufen zu unterscheiden, die möglicherweise am gleichen Datum und zur gleichen Zeit begonnen haben.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Stellt den Typ der im Anruf verwendeten Videozeile dar. Gültige Werte sind:</p>
<ul>
<li><p>0 – Audio</p></li>
<li><p>1 – Video</p></li>
<li><p>2 – Panorama Video</p></li>
<li><p>3 – Anwendung/Desktop Freigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>Endpunkt, der den Anruf getätigt hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Netzwerk-Hop/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Eindeutiger Bezeichner für die IP-Adresse. IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">Tabelle IPAddress in lync Server 2013</a>gespeichert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Roundtrip-Zeit. Die Roundtrip-Zeit misst die Zeitdauer, die ein Sprachpaket benötigt, um sein Ziel zu erreichen, und sendet dann eine Benachrichtigung, dass es empfangen wurde.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

