---
title: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d3be41dd4ca3f942d5b57e1954cecf105fcc714
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

Lync Server 2013 bietet hohe Verfügbarkeit durch Server Redundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors. Ausführliche Informationen zu Serverrollen finden Sie unter [Server Roles in lync Server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 bietet auch Maßnahmen zur Notfallwiederherstellung, indem die Pool Kopplung aktiviert wird. Wenn Sie diese Topologie bereitstellen, bestimmen Sie Paare von Front-End-Pools, wobei sich jeder Pool in einem Paar in einem separaten Datencenter und in einem separaten geografischen Bereich befindet. Wenn ein Pool oder eine Website ausfällt, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool im Paar mit minimaler Unterbrechung des Diensts zu verwenden.

Lync Server 2013 unterstützt auch die hohe Verfügbarkeit von Back-End-Servern. Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für eine Front-End-Pool bereitstellen und synchrone SQL Server Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausführen.

Ausführliche Informationen zur Pool Kopplung und zur Back-End-Server Spiegelung finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Siehe auch


[Server Rollen in lync Server 2013](lync-server-2013-server-roles.md)  
[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

