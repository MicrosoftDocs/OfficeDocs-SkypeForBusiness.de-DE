---
title: 'Lync Server 2013: Definieren der Anforderungen für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88a70796282fe09941ce7632d8c13258defc515
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definieren der Anforderungen für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-07_

Dieses Thema enthält eine Übersicht über die Überlegungen, die Sie bei der Bereitstellung von Enterprise-VoIP für die Regionen, Websites und die Verknüpfungen zwischen Websites in Ihrer Topologie vornehmen müssen und wie diese wichtig sind. Ausführliche Informationen, die Sie bei diesen Entscheidungen unterstützen, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in der Planungsdokumentation.

<div>

## <a name="sites-and-regions"></a>Standorte und Regionen

Geben Sie zunächst die Standorte in Ihrer Topologie an, in denen Sie Enterprise-VoIP und die netzwerkregionen bereitstellen, zu denen diese Websites gehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Entscheiden Sie, wo Gateways lokal bereitgestellt werden, wo Survivable Branch Appliances (SBAS) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) an einen Internet Telefonie-Dienstanbieter (ITSP) konfigurieren können.

</div>

<div>

## <a name="network-links-between-sites"></a>Netzwerkverbindungen zwischen Standorten

Sie müssen auch die Bandbreitenauslastung in Anspruch nehmen, die Sie von den Netzwerkverbindungen zwischen dem zentralen Standort und den Zweigstellenstandorten erwarten. Wenn Sie stabile WAN-Verbindungen Zwischenstand Orten bereitstellen möchten, empfehlen wir, an jedem Zweigstellenstandort ein Gateway bereitzustellen, um Benutzern an diesen Standorten eine lokale direkte Inward-Wählverbindung (DID) zur Verfügung zu stellen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, die Bandbreite einer WAN-Verbindung jedoch wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn Sie über keine elastischen WAN-Verbindungen verfügen, weniger als 1000-Benutzer an Ihrem Zweigstellenstandort hosten und nicht über lokal geschulte lync Server Administratoren verfügen, wird empfohlen, eine Survivable Branch Appliance am Zweigstellenstandort bereitzustellen. Wenn Sie zwischen 1000-und 5000-Benutzern an Ihrem Zweigstellenstandort hosten, keine stabile WAN-Verbindung haben und lync Server Administratoren verfügbar gemacht haben, wird empfohlen, eine Survivable Branch Server mit einem kleinen Gateway am Zweigstellenstandort bereitzustellen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

