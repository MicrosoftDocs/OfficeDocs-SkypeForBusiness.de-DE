---
title: 'Lync Server 2013: bewährte Methoden für die Anrufsteuerung'
description: 'Lync Server 2013: bewährte Methoden für die Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c32af904dc7fb48a1a5d1903bd6ed1f81f4cb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552131"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Bewährte Methoden für die Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

  - Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.
    
    <div>
    

    > [!NOTE]  
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, zum Beispiel Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreiteneinschränkung überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreiteneinschränkung nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.

    
    </div>

  - Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

  - Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

  - Wenn Sie blockierte Anrufe in das Telefonfestnetz umleiten möchten, überprüfen Sie die PSTN-Funktionalität und -Kapazität. Ausführliche Informationen finden Sie unter [Planning Outbound Voice Routing in lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > Kapazität bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

