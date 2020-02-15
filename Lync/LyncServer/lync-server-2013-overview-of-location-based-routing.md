---
title: 'Lync Server 2013: Übersicht über das standortbasierte Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Übersicht über das standortbasierte Routing in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Mit dem standortbasierten Routing wird ein neuer Satz von Regeln eingeführt, durch den das Routing von nationalen und internationalen PSTN-anrufen geändert wird, um eine Maut Umgehung zu verhindern. Durch das standortbasierte Routing können diese Regeln flexibel auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzersätze beschränkt werden.

Die folgenden Szenarien illustrieren die Haupttypen von Einschränkungen, die standortbasiertes Routing erzwingen kann:

  - Ausstiegs Aufrufe – standortbasiertes Routing kann ausgehende Anrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, was verhindert, dass Anrufe von einem PSTN-Gateway in einer anderen Region als Anrufer.

  - Ingress-Anrufe – standortbasiertes Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte Ringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleitet, nicht in derselben Region wie der angerufene lync-Benutzer befindet.

  - Unbekannte Regionen – standortbasiertes Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die eine Verbindung über das Internet herstellen oder sich in unbekannten Regionen befinden).

  - Internationale Regionen – durch das standortbasierte Routing wird das Weiterleiten von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway für den Standort des Benutzers nicht gefunden werden kann.

<div>

## <a name="see-also"></a>Siehe auch


[Planen des standortbasierten Routings in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

