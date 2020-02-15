---
title: 'Lync Server 2013: Anruf Übertragungen und Anrufweiterleitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b16ad2faac58a5999b803c75d02e01da0da2dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Anruf Übertragungen und Anrufweiterleitung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert das standortbasierte Routing die Position des Endpunkts der Calle und den Endpunkt, an den der Anruf übertragen oder weitergeleitet wird (d. h.: Transfer/Forward-Ziel). Das standortbasierte Routing bestimmt, ob der Anruf je nach Standort beider Endpunkte übertragen oder weitergeleitet werden soll.

In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem PSTN-Endpunkt veranschaulicht, und der lync-Benutzer übergibt den Anruf an einen anderen lync-Benutzer. Je nach Standort des Netzwerkstandorts des Endpunkts des Empfängers wirkt sich das standortbasierte Routing auf das Routing der Anrufweiterleitung oder der Weiterleitung aus.

### <a name="initiating-call-transfer-or-forward"></a>Initiieren der Anrufweiterleitung oder Weiterleitung

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzer, der die Anrufweiterleitung/-Weiterleitung initiiert</th>
<th>Der Zielendpunkt befindet sich am gleichen Netzwerkstandort wie der Benutzer, der die Anrufweiterleitung oder Weiterleitung initiiert.</th>
<th>Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als der Benutzer, der die Anrufweiterleitung initiiert oder weiterleitet.</th>
<th>Der Zielendpunkt ist im unbekannten Netzwerkstandort oder Netzwerkstandort nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist zulässig</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist nicht zulässig</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist nicht zulässig</p></td>
</tr>
</tbody>
</table>

  

Beispiel: ein lync-Benutzer in einem Anruf mit einem PSTN-Endpunkt überträgt den Anruf an einen anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet. In diesem Fall ist die Anrufweiterleitung zulässig.

In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem anderen lync-Benutzer dargestellt, und einer der Benutzer übergibt den Anruf an einen PSTN-Endpunkt. Abhängig vom Standort des Benutzers, an den der Anruf weitergeleitet wird, wird in der Tabelle ausführlich beschrieben, wie sich das standortbasierte Routing auf den Anruf auswirkt.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Anrufweiterleitung oder Weiterleitung an PSTN-Endpunkt

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufweiterleitung/Endpunkt Ziel weiterleiten</th>
<th>Lync-Benutzer am gleichen Netzwerkstandort</th>
<th>Lync-Benutzer an unterschiedlichen Netzwerkstandorten</th>
<th>Ein oder beide lync-Benutzer an einem unbekannten Netzwerkstandort oder Netzwerkstandort sind für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Anrufweiterleitung oder-Übertragung zulässig durch die Website VoIP-Routing Richtlinie des übertragenen Benutzers</p></td>
<td><p>Anrufweiterleitung oder-Übertragung zulässig durch die Website VoIP-Routing Richtlinie des übertragenen Benutzers</p></td>
<td><p>Anrufweiterleitung oder Übertragung, die von der VoIP-Richtlinie des übertragenen Benutzers zugelassen wird, nur über Trunks, die für standortbasiertes Routing nicht aktiviert sind</p></td>
</tr>
</tbody>
</table>

  
Beispiel: ein lync-Benutzer in einem Anruf mit einem anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufweiterleitung wird zugelassen.

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für das standortbasierte Routing in lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

