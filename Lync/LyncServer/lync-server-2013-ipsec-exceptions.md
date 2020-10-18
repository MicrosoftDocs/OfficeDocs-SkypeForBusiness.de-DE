---
title: Lync Server 2013 von IPsec-Ausnahmen
description: IPsec-Ausnahmen lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575001"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a>IPsec-Ausnahmen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-27_

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.

In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.

### <a name="recommended-ipsec-exceptions"></a>Empfohlene IPsec-Ausnahmen

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Regelname</th>
<th>Quell-IP</th>
<th>Ziel-IP</th>
<th>Protokoll</th>
<th>Quellport</th>
<th>Zielport</th>
<th>Authentifizierungsanforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V-Edgeserver, intern eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>A/V-Edgeserver, intern</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgeserver, extern eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>A/V-Edgeserver, extern</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>A/V-Edgeserver, intern ausgehend</p></td>
<td><p>A/V-Edgeserver, intern</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP- &amp; TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgeserver, extern ausgehend</p></td>
<td><p>A/V-Edgeserver, extern</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver, eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>Vermittlungs</p>
<p>Server (s)</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver, ausgehend</p></td>
<td><p>Vermittlungs</p>
<p>Server (s)</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>Konferenzzentrale, eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>Konferenzzentrale (ausgehend)</p></td>
<td><p>Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>A/V-Konferenzserver, eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>Front-End-Server</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>A/V-Konferenzen, ausgehend</p></td>
<td><p>Front-End-Server</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>Exchange, eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>Exchange Unified Messaging</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsfreigabeserver, eingehend</p></td>
<td><p>Beliebig</p></td>
<td><p>Anwendungsfreigabeserver</p></td>
<td><p>TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabeserver, ausgehend</p></td>
<td><p>Anwendungsfreigabeserver</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="even">
<td><p>Exchange, ausgehend</p></td>
<td><p>Exchange Unified Messaging</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP und TCP</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>Beliebig</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP</p></td>
<td><p>Angegebener Medienportbereich</p></td>
<td><p>Beliebig</p></td>
<td><p>Nicht authentifizieren</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

