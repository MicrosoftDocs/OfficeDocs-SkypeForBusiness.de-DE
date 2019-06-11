---
title: Lync Server 2013-Standorte
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server-Standorte für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

In lync Server definieren Sie *Websites* in Ihrem Netzwerk, die lync Server-Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass lync Server-Websites ein separates Konzept von Active Directory-Domänendienst Websites und Microsoft Exchange Server-Websites sind. Ihre lync Server-Websites müssen Ihren Active Directory-Standorten nicht entsprechen.

<div>

## <a name="site-types"></a>Websitetypen

Jede Website ist entweder ein *zentraler Standort*, der mindestens einen Front-End-Pool oder einen Standard Edition-Server oder eine *Verzweigungs Website*enthält. Jede Verzweigungs Website ist genau einem zentralen Standort zugeordnet, und die Benutzer an der Zweigstelle erhalten den größten Teil ihrer lync-Server Funktionen von den Servern auf dem zugehörigen zentralen Standort.

Jede Verzweigungs Website enthält eine der folgenden Optionen:

  - Eine *Survivable Branch Appliance (SBA)*, die ein branchenüblicher Blade-Server mit einer lync Server-Registrierungsstelle und einem auf Windows Server ausgeführten Vermittlungsserver ist. Die Survivable Branch-Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network). Die Survivable Branch-Appliance ist für Zweigstellen mit 25 und 1000-Benutzern konzipiert.

  - Ein *Survivable Branch Server (SBS)*, ein Server, auf dem Windows Server ausgeführt wird, der die angegebenen Hardwareanforderungen erfüllt und auf dem die lync Server Registrar-und Mediation Server-Software installiert ist. Sie muss mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen werden. Der Survivor-Branch-Server ist für Zweigstellen mit zwischen 1000 und 5000-Benutzern konzipiert.

  - Ein PSTN-Gateway und optional ein Vermittlungs *Server*. Details zu dieser und anderen Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).

Eine Zweigstelle mit einer stabilen WAN-Verbindung (Wide Area Network) zu einem zentralen Standort kann die dritte Option (ein PSTN-Gateway) und optional einen Vermittlungs Server verwenden. Zweigstellenstandorte mit unelastischen Links sollten eine Survivable Branch-Appliance oder einen Survivable Branch-Server verwenden, der in Zeiten von Wide-Area-Netzwerkfehlern Ausfallsicherheit bietet. Beispielsweise können Benutzer in einer Website mit einer überlebensfähigen Branch-Appliance oder einem Überlebenden Branch-Server weiterhin Enterprise-VoIP-Anrufe tätigen und empfangen, wenn das WAN, das die Verzweigungs Website mit dem zentralen Standort verbindet, ausgefallen ist. Ausführliche Informationen zur Survivable Branch-Appliance, dem Survivable Branch-Server und zur Widerstandsfähigkeit finden Sie unter [Planen der Enterprise-VoIP-Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.

</div>

<div>

## <a name="site-topologies"></a>Website Topologien

Ihre Bereitstellung muss mindestens einen zentralen Standort umfassen und NULL für viele Verzweigungs Websites enthalten. Jede Verzweigungs Website ist mit einem zentralen Standort verbunden. Der zentrale Standort stellt die lync-Server Dienste für die Zweigstelle bereit, die nicht lokal auf der Zweigstelle gehostet werden, beispielsweise Anwesenheitsinformationen und Konferenzen.

Wenn Sie über mehrere Websites verfügen, können Sie die Front-End-Pools an verschiedenen Standorten kombinieren, um Disaster Recovery-Fähigkeiten zu ermöglichen. Ausführliche Informationen finden Sie unter [Support für höhere Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md)  
[Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

