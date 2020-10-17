---
title: 'Lync Server 2013: VoIPDetails-Ansicht'
description: 'Lync Server 2013: VoIPDetails-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566201"
---
# <a name="voipdetails-view-in-lync-server-2013"></a>VoIPDetails-Ansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.

<div>


> [!NOTE]  
> Die VoIPDetails-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Vom Telefon</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tophone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.</p></td>
</tr>
<tr class="even">
<td><p><strong>Togateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

