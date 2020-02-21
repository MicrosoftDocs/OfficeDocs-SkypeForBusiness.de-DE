---
title: 'Lync Server 2013: erforderliche Komponenten für den Director'
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
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Erforderliche Komponenten für den Director in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Die einzige Komponente, die zum Erstellen und Konfigurieren eines Directors erforderlich ist, ist die Bereitstellung der Director-Serverrolle. Hierzu verwenden Sie den Topologie-Generator und definieren entweder einen Pool mit einem einzelnen Computer oder einen Pool mit mehreren Computern im Knoten Directorpool. Nachdem Sie den Director oder Directorpool definiert haben, führen Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, der als Director verwendet werden soll. Im Fall eines Directorpool führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Server aus, der Mitglied des Pools sein soll.

<div>

## <a name="topologies"></a>Topologien

Sie können einen einzelnen Director-Server oder einen Directorpool implementieren. Bei dem Director handelt es sich immer um einen separaten Server oder Pool, der nicht mit einer anderen Serverrolle in lync Server 2013 verbunden ist.

<div>


> [!NOTE]  
> Wenn Sie Directors nicht bereitstellen, übernimmt der Front-End-Server oder Front-End-Pool die Director-Rolle.



</div>

Ein Director-Pool muss Lastenausgleich aufweisen. Führen Sie eine der folgenden Aktionen aus:

  - Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich für Webdienste und einen DNS (Domain Name System)-Lastenausgleich für die anderen Datenverkehrstypen verwendet.
    
    [Skalierte Directorpool-DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich für den Lastenausgleich verwendet, der für den Directorpool erforderlich ist.
    
    [Skaliertes Directorpool-Hardwaregerät zum Lastenausgleich in lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

