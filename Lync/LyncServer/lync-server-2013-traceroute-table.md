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
ms.openlocfilehash: 1bc4a6d990c91f87022b041d9478b6dde5a71bb5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>TraceRoute-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-21_

Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</p>
<ul>
<li><p>0 – Audio</p></li>
<li><p>1 – Video</p></li>
<li><p>2 -- Panoramavideo</p></li>
<li><p>3 – Anwendungs-/Desktop Freigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>Bit</p></td>
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
<td><p>Eindeutige ID für die IP-Adresse. IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle in lync Server 2013</a>gespeichert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

