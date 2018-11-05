---
title: 'Lync Server 2013: Modi für die Medienumgehung'
TOCTitle: Modi für die Medienumgehung
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425862(v=OCS.15)
ms:contentKeyID: 49293696
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modi für die Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Sie müssen die Medienumgehung sowohl global als auch für jeden einzelnen PSTN-Trunk konfigurieren. Wenn Sie die Medienumgehung global aktivieren, haben Sie die Auswahl zwischen zwei Optionen: **Immer umgehen** und **Informationen zu Standort und Region verwenden** .

Wie der Name vermuten lässt, wird die Medienumgehung bei Auswahl von **Immer umgehen** auf alle PSTN-Anrufe angewendet. **Immer umgehen** wird in Bereitstellungen verwendet, in denen weder eine Anrufsteuerung noch die Bereitstellung detaillierter Konfigurationsinformationen für die Medienumgehung erforderlich ist. Darüber hinaus wird die Option **Immer umgehen** verwendet, wenn vollständige Konnektivität zwischen Clients und PSTN-Gateways gegeben ist. In dieser Konfiguration sind alle Subnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.

Bei Auswahl der Option **Informationen zu Standort und Region verwenden** werden Entscheidungen zur Medienumgehung anhand der ID für die Umgehung und der zugeordneten Standort- und Regionenkonfiguration getroffen. Diese Konfiguration bietet die Flexibilität, die Medienumgehung für die gängigsten Topologien zu konfigurieren, da einerseits genau gesteuert werden kann, wann eine Umgehung stattfindet, und andererseits eine Interaktion mit der Anrufsteuerung unterstützt wird. Das System versucht, diese Aufgabe zu vereinfachen, indem automatisch IDs für die Umgehung zugewiesen werden:

  - Das System weist jeder Region eine einzelne, eindeutige ID für die Umgehung zu.

  - Jeder Standort, der über eine WAN-Verbindung ohne Bandbreiteneinschränkungen mit einer Region verbunden ist, erbt dieselbe Umgehungs-ID wie die Region.

  - Einem Standort, der über eine WAN-Verbindung mit Bandbreiteneinschränkungen mit der Region verbunden ist, wird eine andere ID für die Umgehung zugewiesen als der Region.

  - Die jedem Standort zugeordneten Subnetze erben die Umgehungs-ID für diesen Standort.

## Siehe auch

#### Konzepte

[Übersicht über die Medienumgehung in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Medienumgehung und Anrufsteuerung in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Technische Anforderungen für die Medienumgehung in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

