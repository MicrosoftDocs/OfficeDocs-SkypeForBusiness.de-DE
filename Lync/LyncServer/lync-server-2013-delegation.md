---
title: 'Lync Server 2013: Delegierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b31224228a4f2fbdad879e43bab61292852e009c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516303"
---
# <a name="delegation-in-lync-server-2013"></a>Delegation in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Die Delegierungsfunktionen in lync sind von Location-Based Routing auf folgende Weise betroffen:

  - Wenn ein Stellvertreter, der für Location-Based Routing aktiviert ist, einen Anruf im Namen eines Managers tätigt, wird die VoIP-Richtlinie des Stellvertreters verwendet, um den Anruf zu autorisieren, und die Website VoIP-Routing Richtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.

  - Für eingehende PSTN-Anrufe an einen Vorgesetzten gelten dieselben Regeln wie für die Anrufweiterleitung oder gleichzeitiges Klingeln, wie in den Themen Anrufweiterleitung und Weiterleitung und gleichzeitiges Klingeln beschrieben.

  - Wenn ein Delegat einen PSTN-Endpunkt als gleichzeitiges Ring Ziel festlegt, wird für einen eingehenden Anruf an den Vorgesetzten die VoIP-Routing Richtlinie des Standorts, der dem eingehenden trunk zugeordnet ist, zum Weiterleiten des Anrufs an den PSTN-Endpunkt des Stellvertreters verwendet.

  - Für die Delegierung empfiehlt es sich, dass sich der Vorgesetzte und die zugehörigen Stellvertretungen normalerweise am selben Netzwerkstandort befinden.

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für Location-Based Routing in lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

