---
title: 'Lync Server 2013: VoipDetails-Tabelle'
description: 'Lync Server 2013: VoipDetails-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566281"
---
# <a name="voipdetails-table-in-lync-server-2013"></a>VoipDetails-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.


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
<td><p>Primary</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p><strong>PhoneId</strong> des Anrufers. Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> . Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p><strong>PhoneId</strong> des Anrufempfängers. Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> . Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Vermittlungsserver, von dem der Anruf kommt. Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Vermittlungsserver, an den der Anruf geht. Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gateway, von dem der Anruf kommt. Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Togateways</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gateway, an das der Anruf geht. Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde. Weitere Informationen finden Sie <a href="lync-server-2013-phones-table.md">in der Tabelle Telefone in lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

