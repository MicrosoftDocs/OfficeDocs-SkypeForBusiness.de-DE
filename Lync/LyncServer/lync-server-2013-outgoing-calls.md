---
title: 'Lync Server 2013: Ausgehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Ausgehende Anrufe in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Das Routing von ausgehenden Anrufen von Benutzern, die für standortbasierte Routings aktiviert sind, ist vom Netzwerkspeicherort des Endpunkts des Benutzers betroffen. Die folgende Tabelle zeigt, wie sich der standortbasierte Routing auf das Routing von ausgehenden Anrufen auswirkt, abhängig von der Position des Endpunkts des Anrufers.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Der Anrufer tätigt einen ausgehenden Anruf in das öffentliche Telefonnetz

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Der Benutzerendpunkt befindet sich an einem Netzwerkstandort, der für standortbasiertes Routing aktiviert ist</th>
<th>Der Benutzerendpunkt befindet sich an einem unbekannten Netzwerkstandort oder einem Standort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung ausgehender Anrufe</p></td>
<td><p>Der Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
<td><p>Der Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
</tr>
<tr class="even">
<td><p>Routing ausgehender Anrufe</p></td>
<td><p>Das Routing des Anrufs erfolgt gemäß der VoIP-Routingrichtlinie des Netzwerkstandorts</p></td>
<td><p>Der Anruf wird gemäß der VoIP-Richtlinie des Benutzers geroutet, jedoch nur durch Trunks, die nicht für standortbasiertes Routing aktiviert sind (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

