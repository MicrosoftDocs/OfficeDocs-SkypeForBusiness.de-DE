---
title: 'Lync Server 2013: eingehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5a6cd54732bb6c33e358eeb1a5dbb72a1a4e789
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Eingehende Anrufe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Das Routing eingehender Anrufe an Benutzer, die für standortbasiertes Routing aktiviert sind, hängt vom Speicherort des Endpunkts des Benutzers ab. Das Routing eingehender Anrufe wird wie folgt beeinflusst. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem standortbasierten Routing fähigen Netzwerkstandort befindet, und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf weitergeleitet. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem standortbasierten Routing fähigen Netzwerkstandort befindet und sich der Endpunkt an einem anderen Netzwerkstandort befindet als das PSTN-Gateway, wird der Anruf nicht weitergeleitet. Wenn ein Benutzer keine Endpunkte am selben Netzwerkstandort wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet, und eine Benachrichtigung über verpasste Anrufe wird an den angerufenen Teilnehmer gesendet.

Die Anrufweiterleitungseinstellungen eines Benutzers, der für das standortbasierte Routing aktiviert ist, werden weiterhin erzwungen, jedoch werden weitergeleitete Anrufe den standortbasierten Routing Einschränkungen des Benutzers unterworfen.

In der folgenden Tabelle wird veranschaulicht, wie sich das standortbasierte Routing auf das Routing eingehender Anrufe in Abhängigkeit von der Position des Endpunkts des angerufenen auswirkt. Der Netzwerkstandort des PSTN-Gateways ist für das standortbasierte Routing aktiviert, und das standortbasierte Routing ermöglicht nur das Routing von PSTN-Anrufen an Endpunkte innerhalb desselben Netzwerkstandorts.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Angerufener empfängt einen eingehenden Anruf aus dem PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Endpunkt des angerufenen befindet sich am selben Netzwerkstandort wie das PSTN-Gateway</th>
<th>Der Endpunkt des angerufenen befindet sich nicht am gleichen Netzwerkstandort wie das PSTN-Gateway</th>
<th>Endpunkt des angerufenen befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routing eines eingehenden PSTN-Anrufs</p></td>
<td><p>Eingehende Anrufe werden an die Endpunkte des angerufenen weitergeleitet</p></td>
<td><p>Eingehende Anrufe werden nicht an die Endpunkte des angerufenen weitergeleitet</p></td>
<td><p>Eingehende Anrufe werden nicht an die Endpunkte des angerufenen weitergeleitet</p></td>
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

