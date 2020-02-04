---
title: 'Lync Server 2013: Notfallwiederherstellung für Edgeserver'
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
ms.openlocfilehash: 431b4853407b65bca2b029626cc5659490a493d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Notfallwiederherstellung für Edgeserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-12_

Wie bei anderen Serverrollen besteht die beste Möglichkeit für Sie, eine höhere Verfügbarkeit für Ihre Edgeserver bereitzustellen, darin, mehrere Edgeserver in Pools auf jeder Website bereitzustellen. Wenn ein Edge-Server ausfällt, werden die anderen Server im Pool weiterhin Edge-Dienste bereitstellen.

Zum Aktivieren von Disaster Recovery-Verfahren müssen separate Edge-Server-Pools an verschiedenen Standorten bereitgestellt werden. Sie müssen die Edge-Pools nicht explizit mit den Front-End-Pools koppeln, aber mit mehreren Edge-Pools können Sie weiterhin die Verfügbarkeit durchführen, wenn ein ganzer Edge-Pool ausfällt. Die folgenden Abschnitte enthalten Details zur Disaster Recovery für die verschiedenen Funktionen von Edge-Servern.

<div>

## <a name="remote-access"></a>Remote Zugriff

Wenn Sie über mehrere Websites verfügen, die jeweils einen Pool von Edge-Servern aufweisen und ein ganzer Edge-Pool ausfällt, funktionieren die RAS-Dienste weiterhin, ohne dass eine Administratoraktion erforderlich ist. Wenn Sie Edge-Pools in verschiedenen Websites erstellen, können Sie nicht den gleichen FQDN verwenden. Jeder Edge-Pool muss eindeutige FQDNs (intern und extern) aufweisen. Die Edge-Pools verwenden keine Reverse Proxy-Veröffentlichungsregeln, um mit den Front-End-Servern zu kommunizieren. Automatisches Failover tritt auf, wenn der Client die RAS-DNS-Diensteinträge erneut abfragt und Remotebenutzer an die Edgeserver an einem anderen Standort weitergeleitet werden. Der Client versucht jeden externen Edge-FQDN entsprechend der Priorität der DNS-SRV-Einträge.

<div>


> [!NOTE]  
> Damit ein Failover reibungslos funktioniert, müssen Sie sicherstellen, dass die Firewall den Front-End-Servern aus jedem Pool die Kommunikation mit allen Edge-Servern ermöglicht.



</div>

</div>

<div>

## <a name="federation"></a>Partnerverbund

Für Verbundbeziehungen mit anderen Organisationen, die lync Server ausführen, funktionieren eingehende Verbund Anforderungen weiterhin so lange, wie Sie Lösungen wie Geo-DNS-Unternehmen haben. Es ist wichtig zu wissen, dass Verbund Failover kein Failover mit Priorität in SRV-Einträgen bietet. Eine zuvor bereitgestellte Lösung kann Ihnen bei der Bereitstellung von Disaster Recovery-Funktionen für eingehende Föderation helfen.

Ausgehende Föderationen werden immer über einen veröffentlichten Edge-Pool oder Edgeserver in der Organisation eingerichtet. Wenn dieser Edge-Pool nicht mehr vorhanden ist, müssen Sie den Topologie-Generator verwenden, um die ausgehende Föderations Route so zu ändern, dass ein noch ausgeführter Edge-Pool verwendet wird. Ausführliche Informationen finden Sie unter [Failover des Edge-Pools, der für den lync Server-Verbund in lync Server 2013 verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) .

</div>

<div>

## <a name="xmpp-federation"></a>XMPP-Föderation

Bei der XMPP-Föderation schlägt der ausgehende und eingehende Datenverkehr fehl, wenn der als XMPP Federation Gateway bezeichnete Edge-Pool herunterfällt. Damit die XMPP-Föderation wieder funktioniert, müssen Sie die XMPP-Föderation ändern, um einen anderen Edge-Pool zu verwenden. Ausführliche Informationen finden Sie unter [Failover des für die XMPP-Föderation in lync Server 2013 verwendeten Edge-Pools](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Der Edge-Pool schlägt fehl, aber der Front-End-Pool wird weiterhin ausgeführt

Wenn ein Edge-Pool an einer Website fehlschlägt, der Front-End-Pool dieser Website jedoch weiterhin ausgeführt wird, müssen Sie den Front-End-Pool so ändern, dass ein anderer Edge-Pool an einer anderen Website verwendet wird, während der erste Edge-Pool nicht mehr zur Verfügung steht. Weitere Informationen finden Sie unter [Ändern des Edge-Pools, der einem Front-End-Pool in lync Server 2013 zugeordnet](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

