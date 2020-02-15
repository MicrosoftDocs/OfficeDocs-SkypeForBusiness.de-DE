---
title: 'Lync Server 2013: SIPResponseMetaData-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>SIPResponseMetaData-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Die SIPResponseMetaData-Tabelle enthält eine Liste der SIP-Antwortcodes und die Klassifizierung und Definition für jeden dieser Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die SIP-Geräte und SIP-Kommunikationssitzungen betreffen. Beispielsweise wird der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung ausstellt, aber der Server diese Anforderung ablehnt.

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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Numerischer Wert, der den SIP-Antwortcode repräsentiert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Klasse</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Allgemeine Klassifizierung für den Antwortcode. Es gibt folgende Klassifizierungen:</p>
<ul>
<li><p>1 – Informative Antworten</p></li>
<li><p>2 – Erfolgreiche Antworten</p></li>
<li><p>3 – Umleitungsantworten</p></li>
<li><p>4 – Clientfehlerantworten</p></li>
<li><p>5--Server Fehlerantworten</p></li>
<li><p>6 – Globale Fehlerantworten</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Beschreibung</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Beschreibung des SIP-Antwortcodes. Beispielsweise gibt es für den Antwortcode 181 die folgende Beschreibung:</p>
<p>Anruf wird weitergeleitet</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

