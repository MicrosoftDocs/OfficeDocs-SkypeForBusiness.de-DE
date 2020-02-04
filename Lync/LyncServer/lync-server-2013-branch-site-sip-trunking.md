---
title: 'Lync Server 2013: Branch Site SIP Trunking'
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
ms.openlocfilehash: 9c31f0f42a10905f784536b08f10370be9694800
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Branch site SIP trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In einigen Fällen müssen Sie möglicherweise verteilte SIP-Trunking an ausgewählten Zweigstellen implementieren. Wenn Sie feststellen möchten, ob ein SIP-Trunk für eine Zweigstelle benötigt wird, lesen Sie die Informationen unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Details zu den unterstützten Topologie-Optionen für die Bereitstellung von SIP-Stämmen in Zweigstellen finden Sie unter Lösungen für die [Standort Stabilität in lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie sich für die Bereitstellung einer Zweigstelle SIP Trunk entscheiden, müssen Sie eine Website spezifische Kostenanalyse durchführen. Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einer Zweigstelle in New York eine Analyse durchführen, um zu ermitteln, ob ein SIP-Trunk vom Standort New York zu einem lokalen Dienstanbieter implementiert werden soll.

Wenn Sie feststellen möchten, ob ein verteilter SIP-Trunk in New York kostengünstig ist, ermitteln Sie, welche Direktwahlnummern (DID) den SIP-Stamm verwenden, und analysieren Sie die Anzahl der Anrufe, die in New York an andere Bereiche als Redmond (425) vorgenommen werden. Sie können für die Verzweigungs Website am zentralen Standort beendet haben. So kann beispielsweise auf der zentralen Website von Redmond die Nummer für die Niederlassung in der New York Branch-Website gehostet werden. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks kleiner als die Kosten dieser Anrufe sind, sollten Sie einen SIP-Trunk an der New York Branch-Website implementieren.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie eine Verzweigungs Website SIP-Trunk bereitstellen, müssen Sie auch ihre Stabilitäts-und Bandbreitenanforderungen ermitteln. Wenn der Link zwischen Ihrer Zweigstelle und dem zentralen Standort widerstandsfähig ist und über genügend Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch-Appliance an der Zweigstelle bereitstellen. Wenn der Link zwischen Ihrer Verzweigungs Website und dem zentralen Standort nicht belastbar ist, stellen Sie eine Survivable Branch-Appliance bereit, oder stellen Sie einen überlebensfähigen Verzweigungs Server mit einem Gateway oder SIP-Trunk an der Zweigstelle bereit.

</div>

</div>

<span> </span>

</div>

</div>

</div>

