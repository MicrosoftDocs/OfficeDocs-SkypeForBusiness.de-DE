---
title: 'Lync Server 2013: Übersicht über das Location-Based Routing'
description: 'Lync Server 2013: Übersicht über das Location-Based Routing.'
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
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562811"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Übersicht über Location-Based Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Mit Location-Based Routing wird ein neuer Satz von Regeln eingeführt, durch den das Routing von nationalen und internationalen PSTN-anrufen geändert wird, um eine Maut Umgehung zu verhindern. Location-Based Routing bietet die Möglichkeit, diese Regeln auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzersätze zu übersetzen.

In den folgenden Szenarien werden die wichtigsten Arten von Einschränkungen veranschaulicht, die Location-Based Routing erzwingen kann:

  - Ausstiegs Aufrufe – Location-Based Routing kann ausgehende Anrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, wodurch Anrufe von einem PSTN-Gateway in einer anderen Region als der Anrufer verhindert werden.

  - Ingress-Anrufe – Location-Based Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte Ringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleitet, nicht in derselben Region wie der angerufene lync-Benutzer befindet.

  - Unbekannte Regionen – Location-Based Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die über das Internet eine Verbindung herstellen oder sich in unbekannten Regionen befinden).

  - Internationale Regionen – durch Location-Based Routing wird das Routing von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway für den Standort des Benutzers nicht gefunden werden kann.

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Location-Based Routing in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

