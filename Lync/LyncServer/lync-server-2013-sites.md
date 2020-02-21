---
title: Lync Server 2013 Websites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server Websites für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

In lync Server definieren Sie *Websites* in Ihrem Netzwerk, die lync Server Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass lync Server Websites ein separates Konzept von Active Directory-Domänendienste Websites und Exchange Server Websites sind. Ihre lync Server Websites müssen nicht Ihren Active Directory Websites entsprechen.

<div>

## <a name="site-types"></a>Standorttypen

Jeder Standort ist entweder ein *zentraler Standort*, auf dem mindestens eine Front-End-Pool oder ein Standard Edition-Server oder ein Zweigstellen *Standort*vorhanden ist. Jeder Zweigstellenstandort ist genau einem zentralen Standort zugeordnet, und die Benutzer am Zweigstellenstandort erhalten den Großteil ihrer lync Server Funktionalität von den Servern am zugeordneten zentralen Standort.

Jeder Zweigstellenstandort umfasst eine der folgenden Komponenten:

  - Ein *Survivable Branch Appliance (SBA)*, bei dem es sich um einen standardmäßigen Blade-Server mit einer lync Server Registrierungsstelle und einem Vermittlungsserver, der unter Windows Server läuft, handelt. Das Survivable Branch Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network). Das Survivable Branch Appliance wurde für Zweigstellen mit 25 bis 1000 Benutzern entwickelt.

  - Ein *Survivable Branch Server (SBS)*, bei dem es sich um einen Server mit Windows Server handelt, der die angegebenen Hardwareanforderungen erfüllt und auf dem lync Server Registrierungsstelle und Vermittlungsserver Software installiert ist. Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein. Das Survivable Branch Server wurde für Zweigstellen mit 1000-und 5000-Benutzern entwickelt.

  - Ein PSTN-Gateway und optional ein *Vermittlungsserver*. Ausführliche Informationen zu dieser und anderen Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).

Ein Zweigstellenstandort mit einer ausfallsicheren WAN-Verbindung (Wide Area Network) zu einem zentralen Standort kann die dritte Option nutzen – ein PSTN-Gateway und optional einen Vermittlungsserver. Zweigstellenstandorte mit eher unelastischen Links sollten eine Survivable Branch Appliance oder Survivable Branch Server verwenden, die in Zeiten von weit reichenden Netzwerkfehlern Ausfallsicherheit bieten. Beispielsweise können Benutzer bei einer Website mit einer Survivable Branch Appliance oder bereitgestellten Survivable Branch Server weiterhin Enterprise-VoIP-Anrufe tätigen und empfangen, wenn das WAN, das den Zweigstellenstandort mit dem zentralen Standort verbindet, nicht aktiv ist. Ausführliche Informationen zu Survivable Branch Appliance, Survivable Branch Server und Ausfallsicherheit finden Sie in der Planungsdokumentation unter [Planning for Enterprise Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) .

</div>

<div>

## <a name="site-topologies"></a>Standorttopologien

Ihre Bereitstellung muss mindestens einen zentralen Standort enthalten und kann einen oder mehrere Zweigstellenstandorte umfassen. Jeder Zweigstellenstandort ist mit einem zentralen Standort verbunden. Der zentrale Standort stellt die lync Server Dienste für den Zweigstellenstandort bereit, die nicht lokal am Zweigstellenstandort gehostet werden, beispielsweise Anwesenheitsinformationen und Konferenzen.

Wenn Sie über mehrere Standorte verfügen, können Sie die Front-End-Pools an unterschiedlichen Standorten zu Paaren verknüpfen, um die Notfallwiederherstellung zu ermöglichen. Ausführliche Informationen finden Sie unter [Support für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Server Rollen in lync Server 2013](lync-server-2013-server-roles.md)  
[Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

