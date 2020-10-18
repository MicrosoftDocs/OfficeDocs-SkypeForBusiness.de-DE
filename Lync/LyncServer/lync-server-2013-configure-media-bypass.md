---
title: 'Lync Server 2013: Konfigurieren der medienumgehung'
description: 'Lync Server 2013: Configure Media Bypass.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eefe960b9811f16544b7dabdd6aa07960e273806
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577611"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a>Konfigurieren der medienumgehung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver veröffentlicht und konfiguriert haben (wie unter [define a Vermittlungsserver in Topology Builder in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)oder in [definieren und Konfigurieren einer Front-End-Pool oder Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)jeweils in der Bereitstellungsdokumentation beschrieben).

In diesem Abschnitt wird auch davon ausgegangen, dass Sie mindestens einen Gateway-Peer für die Bereitstellung der PSTN-Konnektivität definiert haben, wie unter [define a Gateway in Topology Builder in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)beschrieben. Wenn es sich bei dem Peer, mit dem Sie eine Verbindung herstellen, um den SBC eines SIP-Trunking-Anbieters handelt, stellen Sie sicher, dass der Anbieter ein qualifizierter Anbieter ist und dass der Anbieter die medienumgehung unterstützt. Beispielsweise können viele SIP-Trunking-Anbieter nur deren SBC Datenverkehr vom Vermittlungsserver empfangen. Wenn dies der Fall ist, muss Bypass für den betreffenden trunk nicht aktiviert werden. Außerdem können Sie die medienumgehung nur aktivieren, wenn Ihre Organisation die internen Netzwerk-IP-Adressen dem SIP-Trunking-Anbieter offenbart.

<div>


> [!NOTE]  
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

In diesem Abschnitt wird beschrieben, wie Sie die medienumgehung aktivieren, um die für den Vermittlungsserver erforderliche Verarbeitung zu reduzieren. Bevor Sie die medienumgehung aktivieren, müssen Sie sicherstellen, dass Ihre Umgebung die Bedingungen erfüllt, die zur Unterstützung der medienumgehung erforderlich sind, wie in [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation beschrieben. Stellen Sie außerdem sicher, dass Sie die Informationen in [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) verwendet haben, um zu entscheiden, ob die globalen Einstellungen für die medienumgehung aktiviert werden sollen, um die Vermittlungsserver zu umgehen oder Standort-und Regionsinformationen zu verwenden, wenn Sie bestimmen, ob die Vermittlungsserver umgangen werden soll.

Wenn Sie die Anrufsteuerung (Call Admission Control, CAC), eine andere erweiterte Enterprise-VoIP-Funktion, bereits konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung, die von der Anrufsteuerung durchgeführt wird, nicht für Anrufe gilt, für die die medienumgehung verwendet wird. Die Überprüfung, ob die medienumgehung verwendet wird, wird zuerst durchgeführt, und wenn die medienumgehung eingesetzt wird, wird die Anrufsteuerung für den Anruf nicht verwendet. nur wenn die Medien Umgehungs Überprüfung fehlschlägt, wird die Überprüfung für die Anrufsteuerung durchgeführt. Die beiden Features schließen sich somit gegenseitig für einen bestimmten Anruf aus, der an das PSTN weitergeleitet wird. Dies ist die Logik, da die medienumgehung davon ausgeht, dass Bandbreiteneinschränkungen zwischen den Medien Endpunkten eines Anrufs nicht vorhanden sind. die medienumgehung kann für Links mit eingeschränkter Bandbreite nicht ausgeführt werden. Als Ergebnis gilt eine der folgenden Optionen für einen PSTN-Anruf: a) Medien umgehen die Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf; oder b) Anrufsteuerung wendet Bandbreiten Reservierungen für den Anruf an, und Medien werden von dem Vermittlungsserver verarbeitet, die an dem Anruf beteiligt sind.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Nächste Schritte: Aktivieren der medienumgehung für die trunk Verbindung

Nachdem Sie die anfänglichen Einstellungen für die PSTN-Konnektivität (Wählpläne, VoIP-Richtlinien, PSTN-Verwendungsdaten Sätze, ausgehende Anrufrouten und Übersetzungsregeln) konfiguriert haben, beginnen Sie mit der Aktivierung der medienumgehung mithilfe der Schritte unter [Configure a trunk with Media Bypass in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren der medienumgehung in lync Server 2013, um die Vermittlungsserver immer zu umgehen](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Konfigurieren der globalen Einstellungen für die medienumgehung in lync Server 2013 zur Verwendung von Standort-und Regionsinformationen](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Optionen für die globale medienumgehung in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

