---
title: 'Lync Server 2013: technische Überlegungen zum Location-Based Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536182"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Technische Überlegungen für Location-Based Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Bei der Planung Location-Based Routings sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

<div>

## <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen normaler Vorgänge für den primären Pool bleibt Location-Based Routing während eines Notfall-und Wiederherstellungsverfahrens zu jeder Zeit erzwungen.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Das Konfigurieren Location-Based Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren Survivable Branch Appliances zugeordnet sind. Das Gateway, das Ihrem SBA zugeordnet ist, muss sich am selben Netzwerkstandort befinden wie Ihr Survivable Branch Appliance; andernfalls dürfen Benutzer, die in Ihrem Survivable Branch Appliance verwaltet werden, keine ausgehenden Anrufe tätigen, wenn Location-Based Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrem Survivable Branch Appliance und dem zentralen Standort nicht aktiv ist, bleiben Location-Based Routing Einschränkungen erzwungen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Location-Based Routing in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

