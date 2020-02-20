---
title: 'Lync Server 2013: globale Medien Umgehungs Optionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0166bee22684c32581acdd1241b2b2442cd460ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Optionen für die globale medienumgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle Trunks mit einem Peer (öffentliches Telefon Festnetz (PSTN), IP-PBX oder einen Session Border Controller (SBC) bei einem Internet Telefonie-Dienstanbieter konfiguriert haben) für einen bestimmten Standort oder Dienst für auf dem die Vermittlungsserver von Medien umgangen werden sollen.



</div>

Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Globale medienumgehungseinstellungen können entweder angeben, dass die medienumgehung immer für Anrufe an das PSTN versucht wird, oder dass die medienumgehung mithilfe der Zuordnung von Subnetzen zu Netzwerkstandorten und netzwerkregionen verwendet wird – ähnlich wie bei der Anrufsteuerung, eine andere Erweiterte Sprachfunktion. Wenn medienumgehung und Anrufsteuerung aktiviert sind, werden die netzwerkregion, der Netzwerkstandort und die Subnetzinformationen, die für die Anrufsteuerung angegeben sind, automatisch verwendet, wenn Sie feststellen, ob die medienumgehung eingesetzt werden soll. Dies bedeutet, dass Sie nicht angeben können, dass die medienumgehung immer für Anrufe an das PSTN versucht wird, wenn die Anrufsteuerung aktiviert ist.

In diesem Thema wird beschrieben, wie Sie lync Server-Systemsteuerung und lync Server-Verwaltungsshell zusammen verwenden, um die globalen Einstellungen für die medienumgehung zu konfigurieren.

<div>


> [!NOTE]  
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>– lync Server unter aufgeführt sind.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Nächste Schritte: Auswählen von globalen Einstellungen für die Medienumgehung

Nachdem Sie für spezifische Standorte oder Dienste die Medienumgehung für beliebige Trunkverbindungen aktiviert haben, können Sie folgendermaßen fortfahren:

  - Aktivieren Sie die medienumgehung immer, wie unter [configure Media Bypass in lync Server 2013 beschrieben, um die Vermittlungsserver immer zu umgehen](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Oder konfigurieren Sie die medienumgehung für die Verwendung von Standort-und Regionsinformationen, wie unter [configure Media Bypass Global Settings in lync Server 2013 to Use Site and Region Information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)beschrieben.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Konfigurieren der medienumgehung in lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Medienumgehung und Vermittlungsserver in lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

