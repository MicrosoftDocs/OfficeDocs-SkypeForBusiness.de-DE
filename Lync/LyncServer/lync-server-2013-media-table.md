---
title: 'Lync Server 2013: Medientabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c833ab255741b6a2f28ce9d72f46226c42baea3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Medientabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Jeder Datensatz steht für einen Medientyp, der in einer Peer-zu-Peer-Sitzung verwendet wird. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.

<div>


> [!NOTE]  
> Die Media-Tabelle sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Tabelle enthält die Signaldetails für den Austausch von Mediendaten in einer Sitzung. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; "StartTime" gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem der Sitzungsteilnehmer die Sitzung angenommen hat. "EndTime" bezeichnet in der Regel das Ende der Sitzung.



</div>


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
<td><p><strong>SessionID</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mediaid</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Eindeutige Zahl, die diesen Medientyp identifiziert. Weitere Informationen finden Sie <a href="lync-server-2013-medialist-table.md">in der medialist-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primary</p></td>
<td><p>Dies ist der Zeitpunkt, zu dem eine Medienanforderung gesendet wurde, jedoch nicht die tatsächliche Medienstartzeit. <strong>StartTime</strong> schließt die Sitzungseinrichtungszeit mit ein.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Bezeichnet das Ende der Sitzung.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

