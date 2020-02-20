---
title: 'Lync Server 2013: SIP-Trunking für Zweigstellenstandorte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0e24a0260e6be0bea8d23158f07ffcffcb53cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>SIP-Trunking für Zweigstellenstandorte in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

In einigen Fällen müssen Sie möglicherweise verteiltes SIP-Trunking an ausgewählten Zweigstellenstandorten implementieren. Um zu ermitteln, ob ein SIP-Trunk für einen Zweigstellenstandort erforderlich ist, lesen Sie die Informationen unter [How do I implement SIP Trunking in lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Ausführliche Informationen zu den unterstützten Topologie-Optionen für die Bereitstellung von SIP-Trunks an Zweigstellenstandorten finden Sie unter [Branch-Site Resilienz Solutions in lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie sich für die Bereitstellungeines Zweigstellenstandort-SIP-Trunks entscheiden, müssen Sie eine standortspezifische Kostenanalyse durchführen. Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einem Zweigstellenstandort in New York eine Analyse durchführen, um zu bestimmen, ob ein SIP-Trunk vom Standort New York an einen lokalen Dienstanbieter implementiert werden soll.

Um zu ermitteln, ob ein verteilter SIP-Trunk in New York kostengünstig ist, ermitteln Sie, welche DID-Nummern (Direct Inward Dialing) den SIP-Trunk verwenden sollen, und analysieren Sie die Anzahl der Anrufe, die New York in andere Bereiche als Redmond (425) vornimmt. Sie können die Beendigung für den Zweigstellenstandort am zentralen Standort haben. Beispielsweise kann der zentrale Standort in Redmond die Nummern für den Zweigstellenstandort in New York hosten. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks niedriger sind als die Kosten für diese Anrufe, sollten Sie einen SIP-Trunk am Zweigstellenstandort in New York implementieren.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie einen SIP-Trunk für eine Zweigstelle bereitstellen, müssen Sie auch die Ausfallsicherheit und die Bandbreitenanforderungen ermitteln. Wenn die Verbindung zwischen dem Zweigstellenstandort und dem zentralen Standort widerstandsfähig ist und über ausreichende Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch Appliance an der Zweigstelle bereitstellen. Wenn die Verknüpfung zwischen dem Zweigstellenstandort und dem zentralen Standort nicht belastbar ist, stellen Sie eine Survivable Branch Appliance bereit, oder stellen Sie eine Survivable Branch Server mit einem Gateway oder einem SIP-Trunk am Zweigstellenstandort bereit.

</div>

</div>

<span> </span>

</div>

</div>

</div>

