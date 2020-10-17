---
title: 'Lync Server 2013: von Location-Based Routing nicht unterstützte Funktionen'
description: 'Lync Server 2013: von Location-Based Routing nicht unterstützte Funktionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9cd03a8cbdd50e136605c4f172598b2ad3f523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565161"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Von Location-Based Routing in lync Server 2013 nicht unterstützte Funktionen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-12_

Location-Based Routing gilt nicht für die folgenden Arten von Interaktionen. Location-Based Routing wird nicht erzwungen, wenn lync-Endpunkte mithilfe dieser Funktionen mit PSTN-Endpunkten interagieren.

  - PSTN-Einwahl in Konferenzen

  - Eingehende und ausgehende PSTN-Anrufe über Reaktionsgruppen

  - Parken von anrufen oder Abrufen von PSTN-anrufen über das Parken von Anrufen

  - Eingehende PSTN-Anrufe an den Ankündigungsdienst

  - Eingehende PSTN-Anrufe, die über Gruppenanruf Pickup abgerufen werden

Um Location-Based Weiterleitungsregeln für die Arten von Interaktionen in der folgenden Liste zu erzwingen, müssen Sie Location-Based Routing für Konferenzen aktivieren:

  - PSTN-Einwahlkonferenzen

  - Eskalationen von Peer-zu-Peer-Audiounterhaltungen zu Konferenzen mit PSTN-Endpunkten

  - Beratende Übertragungen mit PSTN-Endpunkten

Informationen zum Aktivieren des Location-Based Routings für Konferenzen finden Sie unter [standortbasiertes Routing für Konferenzen in lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Location-Based Routing in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

