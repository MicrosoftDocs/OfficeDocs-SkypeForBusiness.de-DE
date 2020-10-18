---
title: 'Lync Server 2013: Unterstützte Clients aus vorherigen Bereitstellungen'
description: 'Lync Server 2013: Unterstützte Clients aus vorherigen Bereitstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f83723a571bb63cb012d6ef8a8b502af2717213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575321"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Unterstützte Clients aus vorherigen Bereitstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-14_

In einem Szenario mit Koexistenz können lync Server 2013 Clients mit Clients aus früheren Versionen von lync Server und Office Communications Server interagieren. Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 die neuen lync 2013-Clients. Auf diese Weise können Organisationen, die ein Upgrade von lync Server 2010 durchführen, neue Clients unabhängig von lync Server Upgrades Ausrollen.

<div>

## <a name="supported-server-and-client-combinations"></a>Unterstützte Kombinationen von Server und Client

In der folgenden Tabelle ist aufgeführt, welche Kombinationen von Client- und Serverversionen unterstützt werden. Lync Server 2013 unterstützt zwei frühere Clientversionen, und lync Server 2010 unterstützt den neuen lync 2013-Client.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Gruppen Chat</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Unterstützt1</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Nicht Supported2</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


1In Microsoft lync Server 2010 war die gruppenchatfunktion mit dem Gruppenchat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar. Lync 2013 Clients sind nicht mit lync Server 2010, Gruppen Chat, kompatibel.

2Lync-Webanwendung 2013 bietet nun eine umfassende Besprechungs Erfahrung, einschließlich Computer-Audio und-Video, und gilt als Ersatz für lync 2010 Attendee.

3Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht. Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.

<div>


> [!NOTE]  
> Ausführliche Informationen dazu, wie lync Server 2013 Clients in früheren Versionen von lync Server und Office Communications Server nebeneinander bestehen und mit Clients interagieren können, finden Sie unter <A href="lync-server-2013-client-interoperability-in-lync-2013.md">Client Interoperability in lync 2013</A> in der Planungsdokumentation.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

