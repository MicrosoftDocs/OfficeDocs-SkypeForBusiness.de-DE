---
title: 'Lync Server 2013: ConferenceUris-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 143e2b44c5b5ddd9cbf630ac17267e0747029aed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>ConferenceUris-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-25_

Bei der ConferenceUris-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primary</p></td>
<td><p>Zeitstempel; zu internen Zwecken.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>Konferenz-URI</p></td>
</tr>
<tr class="even">
<td><p><strong>Prüfsumme</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Prüfsumme von ConferenceUri. Wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI-Typ, beispielsweise conf: Chat für Sofortnachrichtenkonferenz oder conf: Audio-Video für Audio/Videokonferenz. Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-uritypes-table.md">UriTypes in lync Server 2013</a> Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

