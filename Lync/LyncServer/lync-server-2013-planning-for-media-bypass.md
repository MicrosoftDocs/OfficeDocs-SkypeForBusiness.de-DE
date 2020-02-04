---
title: 'Lync Server 2013: Planung der Medienumgehung'
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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Planung der Medienumgehung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Medienumgehung bezieht sich auf das Entfernen des Vermittlungsservers aus dem Medienpfad, wenn möglich, für Anrufe, deren Signalisierung den Vermittlungsserver durchquert.

Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Die Skalierbarkeit kann verbessert werden, da durch die Eliminierung der Medienverarbeitung für Umgehungs Anrufe die Belastung des Vermittlungsservers verringert wird. Diese Verringerung der Auslastung ergänzt die Möglichkeit des Vermittlungsservers, mehrere Gateways zu steuern.

Wenn eine Verzweigungs Website ohne einen Vermittlungs Server über eine oder mehrere WAN-Links mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, senkt die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einer Zweigstelle direkt an sein lokales Gateway fließen können, ohne Zunächst müssen Sie über die WAN-Verbindung zu einem Vermittlungs Server am zentralen Standort und zurückfließen.

Durch die Entlastung des Vermittlungsservers von der Medienverarbeitung kann die medienumgehung auch die Anzahl der Vermittlungsserver verringern, die für eine Enterprise-VoIP-Infrastruktur erforderlich sind.

Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.

**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**

![Voice CAC Media Bypass-Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass-Verbindungserzwingung")

Generell gilt, dass die Medienumgehung möglichst immer aktiviert werden sollte.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über die medienumgehung in lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modi für die Medienumgehung in Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Medienumgehung und Anrufsteuerung in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Technische Anforderungen für die Medienumgehung in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

[Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

