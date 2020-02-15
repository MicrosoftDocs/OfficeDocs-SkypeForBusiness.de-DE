---
title: 'Lync Server 2013: Planung der medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planen der medienumgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Bei der Medienumgehung wird der Vermittlungsserver nach Möglichkeit für Anrufe aus dem Medienpfad entfernt, deren Signaldaten über den Vermittlungsserver verarbeitet werden.

Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Der Vermittlungsserver muss für Anrufe mit Umgehung keine Mediendatenverarbeitung durchführen, sodass die Vermittlungsserverlast reduziert und die Skalierbarkeit verbessert wird. Diese Verringerung der Auslastung ergänzt die Fähigkeit des Vermittlungsserver, mehrere Gateways zu steuern.

Wenn ein Zweigstellenstandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die medienumgehung die Bandbreitenanforderung, da Medien von einem Client an einem Zweigstellenstandort direkt an das lokale Gateway weiter fließen können, ohne Zunächst müssen Sie über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurückfließen.

Durch die Entlastung der Vermittlungsserver von der Medienverarbeitung kann die medienumgehung auch die Anzahl von Vermittlungsservern verringern, die eine Enterprise-VoIP-Infrastruktur benötigt.

Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.

**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**

![VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung")

Allgemein gilt, dass die Medienumgehung wenn möglich aktiviert werden sollte.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über die medienumgehung in lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Medien Umgehungs Modi in lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Medienumgehung und Anrufsteuerung in lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Technische Anforderungen für die medienumgehung in lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

[Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Optionen für die globale medienumgehung in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

