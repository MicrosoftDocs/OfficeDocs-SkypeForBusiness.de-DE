---
title: 'Lync Server 2013: Edgeserver Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad1ac0197c4f7755b334624e46f7cec096897f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528822"
---
# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Edgeserver Notfallwiederherstellung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-12_

Wie bei anderen Serverrollen wird die hohe Verfügbarkeit für Ihre Edgeserver am besten durch die Bereitstellung mehrerer Edgeserver in Pools an den einzelnen Standorten gewährleistet. Fällt ein Edgeserver aus, stellen die anderen Server im Pool weiterhin Edgedienste bereit.

Zur Ermöglichung von Notfallwiederherstellungsprozeduren müssen Sie separate Edgeserver an verschiedenen Standorten bereitstellen. Sie müssen Edgepools nicht wie Front-End-Pools explizit zusammenfassen. Bei mehreren Edgepools besteht jedoch die Möglichkeit, die Arbeit fortzusetzen, falls ein Edgepool ausfällt. Die folgenden Abschnitte enthalten ausführliche Informationen zur Notfallwiederherstellung der verschiedenen Funktionen von Edgeservern.

<div>

## <a name="remote-access"></a>Remotezugriff

Wenn Sie über mehrere Standorte verfügen, die jeweils einen Pool mit Edgeserver haben und ein ganzer Edgepool fehlschlägt, funktionieren die RAS-Dienste weiterhin, ohne dass Administratoraktionen erforderlich sind. Wenn Sie Edge-Pools an unterschiedlichen Standorten erstellen, können Sie nicht den gleichen FQDN verwenden. Jeder Edgepool muss über eindeutige FQDNs (intern und extern) verfügen. In den Edge-Pools werden keine Reverseproxy-Veröffentlichungsregeln verwendet, um mit den Front-End-Servern zu kommunizieren. Das automatische Failover erfolgt, wenn der Client die RAS-DNS-Diensteinträge erneut fragt und Remotebenutzer an die Edgeserver an einem anderen Standort weitergeleitet werden. Der Client versucht jeden externen Edge-FQDN entsprechend der Priorität der DNS-SRV-Einträge.

<div>


> [!NOTE]  
> Damit ein Failover reibungslos funktioniert, müssen Sie sicherstellen, dass die Firewall den Front-End-Servern in jedem Pool die Kommunikation mit allen Edge-Servern ermöglicht.



</div>

</div>

<div>

## <a name="federation"></a>Partnerverbund

Für Verbundbeziehungen mit anderen Organisationen, die lync Server ausgeführt werden, funktionieren eingehende Verbund Anforderungen weiterhin so lange, wie Sie Lösungen wie Geo-DNS-preiswert haben. Beachten Sie, dass das Verbund Failover kein Failover mit Priorität in SRV-Einträgen bereitstellt. Eine frühere Lösung kann Ihnen bei der Bereitstellung von Notfallwiederherstellungsfunktionen für den eingehenden Verbund helfen.

Der ausgehende Partnerverbund wird immer über einen veröffentlichten Edgepool oder Edgeserver in der Organisation eingerichtet. Fällt dieser Edgepool aus, müssen Sie mit dem Topologie-Generator die ausgehende Partnerverbundroute ändern, sodass sie einen Edgepool verwendet, der noch ausgeführt wird. Ausführliche Informationen finden Sie unter [Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) .

</div>

<div>

## <a name="xmpp-federation"></a>XMPP-Partnerverbund

Beim XMPP-Partnerverbund treten beim ausgehenden und eingehenden Datenverkehr Fehler auf, wenn der als XMPP-Verbundpartner-Gateway festgelegte Edgepool ausfällt. Damit der XMPP-Partnerverbund wieder funktioniert, müssen Sie die Verwendung eines anderen Edgepools durch den XMPP-Partnerverbund festlegen. Ausführliche Informationen finden Sie unter [Failover des Edgepool für XMPP-Verbund in lync Server 2013 verwendet](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Ausfall des Edgepools bei weiterer Ausführung des Front-End-Pools

Falls ein Edgepool an einem Standort ausfällt, der Front-End-Pool an diesem Standort jedoch weiterhin ausgeführt wird, müssen Sie den Front-End-Pool so ändern, dass er einen anderen Edgepool an einem anderen Standort verwendet, während der erste Edgepool nicht verfügbar ist. Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

