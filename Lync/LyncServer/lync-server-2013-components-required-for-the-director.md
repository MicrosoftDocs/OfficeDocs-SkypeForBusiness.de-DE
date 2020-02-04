---
title: 'Lync Server 2013: Für den Director erforderliche Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Für den Director erforderliche Komponenten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Die einzige Komponente, die zum Erstellen und Konfigurieren eines Directors erforderlich ist, besteht darin, die Director-Serverrolle bereitzustellen. Dazu verwenden Sie den Topologie-Generator und definieren entweder einen einzelnen Computerpool oder einen Pool mit mehreren Computern im Director-Pool-Knoten. Nachdem Sie den Director-oder Director-Pool definiert haben, führen Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, der als Director ausgeführt werden soll. Im Fall eines Director-Pools führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Server aus, der Mitglied des Pools sein soll.

<div>

## <a name="topologies"></a>Topologien verfügen

Sie können einen einzelnen Director-Server oder einen Director-Pool implementieren. Der Director ist immer ein separater Server oder Pool, nicht mit einer anderen Serverrolle in lync Server 2013.

<div>


> [!NOTE]  
> Wenn Sie Directors nicht bereitstellen, übernimmt der Front-End-Server oder der Front-End-Pool die Director-Rolle.



</div>

Ein Pool von Directors muss Load Balanced sein. Sie können eine der folgenden Aktionen ausführen:

  - Erstellen Sie eine Topologie, die ein Hardwarelastenausgleich für Webdienste und DNS (Domain Name System)-Lastenausgleich für die anderen Datenverkehrstypen verwendet.
    
    [Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Erstellen Sie eine Topologie, die ein Hardware-Lastenausgleichsmodul für den für den Director-Pool erforderlichen Lastenausgleich verwendet.
    
    [Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

