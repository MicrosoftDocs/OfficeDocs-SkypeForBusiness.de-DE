---
title: 'Lync Server 2013: Session-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Sitzungstabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-09-09_

Jeder Datensatz stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten umfasst. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als SIP-Dialog (Audio oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.


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
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenzschlüssel. Referenziert aus dem <a href="lync-server-2013-conference-table.md">Konferenztisch in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Korrelationsschlüssel. Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Dialog Feld Kategorie; 0 ist lync Server Vermittlungsserver Bein; 1 ist Vermittlungsserver auf das PSTN-Gateway-Bein.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs abgeglichen wurden. Für lync Server ist nur ein Wert definiert.</p>
<p>0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Die Startzeit des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Die Endzeit des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des Anrufers. Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des anrufempfängers. Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>SIP-URI in der vom SIP p-asserted Identity (Pai) des empfangenden Endpunkts. Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI des Anrufers. Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Endpunkt des Anrufers. Referenziert von der <a href="lync-server-2013-endpoint-table.md">Endpunkt Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>Bit</p></td>
<td><p>Fremd</p></td>
<td><p>Benutzer-Agent des Anrufers. Verweist auf die <a href="lync-server-2013-useragent-table.md">userAgent-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Die Priorität dieses Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Diese Spalte ist veraltet und wird in Microsoft lync Server 2013 nicht verwendet. Stattdessen werden diese Informationen auf einer pro-Medien-Basis angegeben. Weitere Informationen hierzu erhalten Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle "medialinie" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>P-Asserted-Identity des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Endpunkt, der den Anruf empfangen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Benutzer-Agent, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde. Benutzer-Agents stellen das Clientendpunkt Gerät dar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>SIP-URI des Benutzers, der den Anruf empfangen hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

