---
title: 'Lync Server 2013: Interoperabilitäts Überlegungen für Videokonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Interoperabilitäts Überlegungen für Videokonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

In diesem Abschnitt werden die Benutzererfahrung während der Koexistenzphase der Migration beschrieben, wenn es Interoperabilität zwischen Legacyclients und einem lync Server 2013-Pool oder lync Server 2013-Clients und einem Legacy Pool gibt.

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013-Pools

Benutzer erleben das folgende Verhalten, wenn ein Legacyclient in einem lync Server 2013-Pool verwendet wird:

  - Bei Anrufen mit zwei Teilnehmern ist die Videoauflösung identisch mit der des Legacy Pools.

  - Für Konferenzen mit mehreren Teilnehmern sind Videoauflösung und Videokonferenz Features identisch mit dem Legacy Pool. Eine Katalogansicht und eine höhere Auflösung sind nicht verfügbar.

</div>

<div>

## <a name="legacy-pools"></a>Legacy Pools

Benutzer erleben das folgende Verhalten, wenn ein lync Server 2013-Client in einem Legacy Pool verwendet wird:

  - Bei Anrufen mit zwei Teilnehmern können lync Server 2013-Clients neue Features wie folgt verwenden:
    
      - H. 264 steht zur Verfügung, wenn beide Teilnehmer lync Server 2013-Clients verwenden.
    
      - Der lync Server 2013-Client verwendet den Standardwert für TotalReceiveVideoBitRateKb, da diese Informationen vom Legacy Server nicht an die in-Band-Bereitstellung gesendet werden.

  - Für Konferenzen mit mehreren Teilnehmern sind Videoauflösungen und Videokonferenz Features identisch mit den Erfahrungen eines Legacyclients im Legacy Pool.

<div>


> [!NOTE]  
> Wenn ein Legacy Server einen lync Server 2013-Client hostet, ist es möglich, die Bandbreite für Videokonferenzen so zu konfigurieren, dass alle Benutzer im Pool nur Videos mit niedriger Auflösung empfangen, aber Video mit hoher Auflösung senden. Ein Beispiel hierfür ist, wenn MaxVideoRateAllowed in der Medienkonfiguration auf cif-250K und VideoBitRateKb auf 2000 Kbit/s in Konferenzrichtlinien eingestellt ist. Der Nettoeffekt in dieser Situation ist, dass eine höhere Auflösung für Benutzer im Pool nicht möglich ist.<BR>Da MaxVideoRateAllowed nicht mehr für lync Server 2013-Clients verwendet wird, kann es nicht verhindern, dass lync Server 2013-Clients ein Video mit hoher Auflösung anfordern. Setzen Sie stattdessen VideoBitRateKb in der konferenzrichtlinie für alle Benutzer im Pool auf den gleichen Wert wie MaxVideoRateAllowed (das heißt, CIF ist auf 250 KBit/s festgesetzt, oder VGA ist auf 600 KBit/s festgesetzt, oder HD ist auf 1500 kBit/s festgesetzt).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

