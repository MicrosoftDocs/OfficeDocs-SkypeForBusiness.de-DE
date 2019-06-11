---
title: 'Lync Server 2013: Session-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Session-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-09_

Jeder Eintrag stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten beinhaltet. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als SIP-Dialog (Audio-oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.


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
<td><p>Primary</p></td>
<td><p>Wird in der <a href="lync-server-2013-dialog-table.md">Dialog Feld Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Wird in der <a href="lync-server-2013-dialog-table.md">Dialog Feld Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz Taste. Wird aus der <a href="lync-server-2013-conference-table.md">Konferenz Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Korrelationsschlüssel Wird in der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Dialog Feld Kategorie; 0 ist lync Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten. Bei lync Server ist nur ein Wert definiert.</p>
<p>0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Startzeit des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Endzeit des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des Anrufers. Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Pool des anrufempfängers. Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>SIP-URI in der SIP p-asserted Identity (Pai) des empfangenden Endpunkts. Wird in der <a href="lync-server-2013-user-table.md">Tabelle "Benutzer" in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI des Anrufers. Wird in der <a href="lync-server-2013-user-table.md">Tabelle "Benutzer" in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Endpunkt des Anrufers. Wird von der <a href="lync-server-2013-endpoint-table.md">Endpunkt Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Fremd</p></td>
<td><p>Benutzer-Agent des Anrufers. Wird in der <a href="lync-server-2013-useragent-table.md">userAgent-Tabelle in lync Server 2013</a>referenziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Die Priorität dieses Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Diese Spalte wurde als veraltet markiert und wird in Microsoft lync Server 2013 nicht verwendet. Stattdessen werden diese Informationen auf Basis einer einzelnen medienzeile gemeldet. Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>P-bestätigt – Identität des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.</p></td>
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
<td><p>Benutzer-Agent des Benutzers, der den Anruf erhalten hat. Benutzer-Agents stellen das Clientendpunkt Gerät dar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>SIP-URI des Benutzers, der den Anruf erhalten hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

