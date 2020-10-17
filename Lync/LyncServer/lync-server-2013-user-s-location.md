---
title: 'Lync Server 2013: Speicherort des Benutzers'
description: 'Lync Server 2013: Speicherort des Benutzers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561211"
---
# <a name="users-location-in-lync-server-2013"></a>Speicherort des Benutzers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Location-Based Routing nutzt dieselben netzwerkregionen, Standorte und Subnetze, die in lync Server verwendet werden, die von E9-1-1, CAC und medienumgehung definiert wurde, um Anruf Weiterleitungs Einschränkungen anzuwenden, um die PSTN-Maut Umgehung zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der lync-Endpunkte des Benutzers festgelegt, von denen eine Verbindung hergestellt wird. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, der in vom Administrator definierten netzwerkregionen aggregiert wird. Location-Based Routing wird basierend auf dem Netzwerkstandort des Benutzers erzwungen.

Location-Based Routingregeln werden auf einer pro Netzwerkstandort Basis angewendet, was bedeutet, dass ein bestimmter Satz von Regeln auf alle für Location-Based Routing aktivierten Endpunkte angewendet wird, die sich innerhalb desselben Netzwerkstandorts befinden. Administratoren können Location-Based Routing auf Netzwerkstandorte anwenden, die dies erfordern.

VoIP-Routing Richtlinien können auf einer pro Netzwerkstandort Basis definiert werden, um ein bestimmtes PSTN-Gateway zu definieren, das von allen Benutzern am Netzwerkstandort zum Anrufen von PSTN-Telefonnummern verwendet werden soll. Solche VoIP-Routing Richtlinien haben Vorrang vor dem Routing, das durch die VoIP-Richtlinie des Benutzers definiert wird, wenn sich der Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing aktiviert ist, und er verhindert das Weiterleiten von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind. Wenn ein lync-Benutzer einen PSTN-Anruf tätigt, bestimmt die VoIP-Richtlinie des Benutzers, ob der Benutzer zum tätigen des Anrufs autorisiert werden kann. Wenn die VoIP-Richtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu tätigen, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf ausgehen soll. Durch Location-Based Routing wird diese Bestimmung basierend auf dem Standort des Benutzers festgelegt.

Ein Benutzer Speicherort kann wie folgt kategorisiert werden:

  - Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und seine DID-Nummer (direkte Inward Dial) wird auf einem PSTN-Gateway am gleichen Netzwerkstandort (also Office) beendet. Das Routing von ausgehenden Anrufen erfolgt über die VoIP-Routing Richtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Eingehende PSTN-Anrufe an den Benutzer werden an Endpunkte geroutet, die sich am selben Netzwerkstandort wie das PSTN-Gateway befinden.

  - Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich vom Netzwerkstandort unterscheidet, auf dem sich das PSTN-Gateway befindet. (d. h., der Benutzer hat in ein anderes Unternehmensbüro gereist). Für das Routing von ausgehenden Anrufen wird die VoIP-Routing Richtlinie des Netzwerkstandorts verwendet, an dem sich der Benutzer befindet. Eingehende PSTN-Anrufe an den Benutzer werden nicht an Endpunkte geroutet, die sich an unterschiedlichen Standorten befinden als das PSTN-Gateway, um eine PSTN-Maut Umgehung zu verhindern.

  - Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der der lync Server-Bereitstellung unbekannt ist, basiert das Routing von ausgehenden Anrufen auf der VoIP-Richtlinie, die dem Benutzer für PSTN-Gateways zugewiesen ist, die nicht an Location-Based Routing Einschränkungen gebunden sind. Eingehende PSTN-Anrufe werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um eine PSTN-Maut Umgehung zu verhindern.

<div>

## <a name="see-also"></a>Siehe auch


[Leitfaden für Location-Based Routing in lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

