---
title: 'Lync Server 2013: Überlegungen zur Interoperabilität für Videokonferenzen'
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
ms.openlocfilehash: 6157b9dc8867b2f458eafb6f0343fd43a19af537
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Überlegungen zur Interoperabilität für Videokonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

In diesem Abschnitt wird die Benutzererfahrung während der Koexistenzphase der Migration beschrieben, wenn Interoperabilität zwischen Legacyclients und einem lync Server 2013 Pool oder lync Server 2013 Clients und einem Legacy Pool besteht.

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 Pools

Benutzer erleben das folgende Verhalten, wenn ein Legacyclient in einem lync Server 2013-Pool verwendet wird:

  - Bei Gesprächen mit zwei Teilnehmern ist die Videoauflösung mit der im Legacypool identisch.

  - Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen im Legacypool. Profilfotoansicht und hohe Auflösung sind nicht verfügbar.

</div>

<div>

## <a name="legacy-pools"></a>Legacypools

Benutzer erleben das folgende Verhalten, wenn ein lync Server 2013-Client in einem Legacy Pool verwendet wird:

  - Für Anrufe mit zwei Teilnehmern können lync Server 2013-Clients wie folgt neue Features verwenden:
    
      - H. 264 ist verfügbar, wenn beide Teilnehmer lync Server 2013 Clients verwenden.
    
      - Der lync Server 2013-Client verwendet den Standardwert für TotalReceiveVideoBitRateKb, da der Legacy Server diese Informationen nicht mit in-Band-Übermittlung sendet.

  - Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen eines Legacyclients im Legacypool.

<div>


> [!NOTE]  
> Wenn ein Legacy Server einen lync Server 2013-Client hostet, ist es möglich, die Bandbreiten für Videokonferenzen so zu konfigurieren, dass alle Benutzer im Pool nur Video mit niedriger Auflösung empfangen, aber hochauflösende Videos senden. Ein Beispiel hierfür ist, wenn MaxVideoRateAllowed auf cif-250K in der Medienkonfiguration festgelegt ist und VideoBitRateKb in der konferenzrichtlinie auf 2000 Kbit/s festgelegt ist. Der Nettoeffekt in dieser Situation ist, dass eine hohe Auflösung für Benutzer im Pool nicht möglich ist.<BR>Da MaxVideoRateAllowed nicht mehr für lync Server 2013-Clients verwendet wird, kann es nicht verhindern, dass lync Server 2013 Clients hochauflösende Videos anfordern. Legen Sie stattdessen VideoBitRateKb in der konferenzrichtlinie für alle Benutzer im Pool auf denselben Wert fest wie MaxVideoRateAllowed (CIF ist auf 250 KBit/s festgelegt, oder VGA ist auf 600 KBit/s festgelegt, oder HD ist auf 1500 kBit/s festgelegt).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

