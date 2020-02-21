---
title: 'Lync Server 2013: UserAgent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9abca1aaaff164759f195f8f60de335e279335
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>UserAgent-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-25_

Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert wird, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Eigen</p></td>
<td><p>Zeichenfolge des Benutzer-Agents.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 ist Vermittlungsserver.</p>
<p>2 ist A/V-Konferenzserver.</p>
<p>4 ist lync.</p>
<p>8 ist IP-Telefon.</p>
<p>16 ist Live Meeting Konsole.</p>
<p>32 ist das Bereitstellungs Überprüfungs Tool (Thrombose).</p>
<p>64 ist lync auf Macintosh-Computern.</p>
<p>128 ist Office Communications Server 2007 R2 Attendant.</p>
<p>256 ist der Konferenzankündigungsdienst.</p>
<p>512 ist eine automatische Telefonzentrale für Konferenzen.</p>
<p>1024 ist Reaktionsgruppenanwendung.</p>
<p>2048 ist außerhalb der Sprachsteuerung.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

