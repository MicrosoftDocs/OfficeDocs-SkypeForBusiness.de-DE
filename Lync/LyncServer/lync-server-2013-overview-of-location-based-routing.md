---
title: 'Lync Server 2013: Übersicht über standortbasiertes Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Übersicht über standortbasiertes Routing in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das standortbasierte Routing stellt einen neuen Regelsatz zur Verfügung, mit dem das Routing nationaler und internationaler PSTN-Anrufe modifiziert werden kann, um eine Gebührenumgehung zu verhindern. Beim standortbasierten Routing lassen sich die Regeln flexibel auf bestimmte Regionen und Gateways und sogar auf bestimmte Benutzergruppen beschränken.

Die folgenden Szenarien veranschaulichen die Haupttypen von Einschränkungen, die standortbasiertes Routing erzwingen kann:

  - Ausstiegs Anrufe – standortbasiertes Routing kann ausgehende Aufrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, die das Auslaufen von einem PSTN-Gateway in einer anderen Region wie die Rufnummernanzeige.

  - Ingress-Anrufe – standortbasiertes Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte ablaufen, wenn sich das PSTN-Gateway, das den eingehenden Anruf leitet, nicht in der gleichen Region wie der angerufene lync-Benutzer befindet.

  - Unbekannte Regionen – standortbasiertes Routing schränkt eingehende und ausgehende PSTN-Anrufe von und zu Benutzern ein, die sich an unbestimmten Speicherorten befinden (d. h. Remotebenutzer, die eine Verbindung mit dem Internet herstellen oder sich in unbekannten Regionen befinden).

  - Internationale Regionen – durch standortbasiertes Routing wird das Routing von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway zum Standort des Benutzers nicht gefunden werden kann.

<div>

## <a name="see-also"></a>Siehe auch


[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

