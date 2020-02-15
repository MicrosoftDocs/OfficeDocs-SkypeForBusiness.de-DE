---
title: 'Lync Server 2013: ausgehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Ausgehende Anrufe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Das Routing von ausgehenden Anrufen von Benutzern, die für standortbasiertes Routing aktiviert sind, wird von der Netzwerkadresse des Endpunkts des Benutzers beeinflusst. In der folgenden Tabelle wird veranschaulicht, wie sich das standortbasierte Routing auf das Routing ausgehender Anrufe in Abhängigkeit von der Position des Endpunkts des Anrufers auswirkt.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Anrufer, der einen ausgehenden Anruf an das PSTN abgibt

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Benutzer Endpunkt befindet sich an einem Netzwerkstandort, der für standortbasiertes Routing aktiviert ist</th>
<th>Benutzer Endpunkt befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung für ausgehende Anrufe</p></td>
<td><p>Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
<td><p>Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
</tr>
<tr class="even">
<td><p>Weiterleitung des ausgehenden Anrufs</p></td>
<td><p>Der Anruf wird entsprechend der VoIP-Routing Richtlinie des Netzwerkstandorts weitergeleitet.</p></td>
<td><p>Der Anruf wird entsprechend der VoIP-Richtlinie des Benutzers und nur über Trunks weitergeleitet, die nicht für standortbasiertes Routing aktiviert sind (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für das standortbasierte Routing in lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

