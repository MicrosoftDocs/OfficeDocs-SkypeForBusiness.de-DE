---
title: 'Lync Server 2013: Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Dieses Thema enthält eine Übersicht über die Überlegungen, die Sie zu den Regionen, Websites und den Verknüpfungen zwischen Websites in Ihrer Topologie vornehmen müssen, und wie diese wichtig sind, wenn Sie Enterprise-VoIP bereitstellen. Details, die Ihnen bei diesen Entscheidungen helfen, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in der Planungsdokumentation.

<div>

## <a name="sites-and-regions"></a>Websites und Regionen

Identifizieren Sie zunächst die Websites in Ihrer Topologie, in denen Sie Enterprise-VoIP und die netzwerkregionen bereitstellen, denen diese Websites angehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Entscheiden Sie, wo Gateways lokal bereitgestellt werden sollen, wo Survival Branch Appliances (SBAS) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) an einen Internet-Telefoniedienst (ITSP) konfigurieren können.

</div>

<div>

## <a name="network-links-between-sites"></a>Netzwerkverknüpfungen zwischen Websites

Sie müssen auch die Bandbreitennutzung in Frage stellen, die Sie bei den Netzwerkverbindungen zwischen ihrer zentralen Website und ihren Zweigstellen erwarten. Wenn Sie über eine stabile WAN-Verbindung zwischen Websites verfügen oder diese bereitstellen möchten, empfiehlt es sich, ein Gateway an jeder Verzweigungs Website bereitzustellen, um den Benutzern an diesen Standorten eine direkte Durchwahl (DID)-Kündigung zu ermöglichen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, aber die Bandbreite einer WAN-Verbindung wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn Sie nicht über belastbare WAN-Links verfügen, weniger als 1000-Benutzer an ihrer Zweigstelle hosten und keine lokal ausgebildeten lync Server-Administratoren verfügbar sind, empfehlen wir, dass Sie eine Survivable Branch-Appliance an der Zweigstelle bereitstellen. Wenn Sie zwischen 1000-und 5000-Benutzern an ihrer Zweigstelle hosten, keine robuste WAN-Verbindung haben und die lync Server-Administratoren zur Verfügung stehen, empfehlen wir, dass Sie einen überlebensfähigen Verzweigungs Server mit einem kleinen Gateway auf der Zweigstelle bereitstellen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

