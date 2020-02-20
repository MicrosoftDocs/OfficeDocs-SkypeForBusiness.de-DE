---
title: 'Lync Server 2013: technische Überlegungen für standortbasiertes Routing'
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
ms.openlocfilehash: e672e35771ec3cc4ecbd3655af350231f1583b52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Technische Überlegungen zum standortbasierten Routing in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Bei der Planung des standortbasierten Routings sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

<div>

## <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen normaler Vorgänge für den primären Pool bleibt das standortbasierte Routing während eines Notfall-und Wiederherstellungsverfahrens zu jeder Zeit erzwungen.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Das Konfigurieren des standortbasierten Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren Survivable Branch Appliances zugeordnet sind. Das Gateway, das Ihrem SBA zugeordnet ist, muss sich am selben Netzwerkstandort befinden wie Ihr Survivable Branch Appliance; andernfalls dürfen Benutzer, die in Ihrem Survivable Branch Appliance verwaltet werden, keine ausgehenden Anrufe tätigen, wenn das standortbasierte Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrem Survivable Branch Appliance und dem zentralen Standort nicht aktiv ist, bleiben standortbasierte Routing Einschränkungen bestehen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen des standortbasierten Routings in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

