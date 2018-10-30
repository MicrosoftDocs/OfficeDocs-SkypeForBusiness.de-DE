---
title: 'Lync Server 2013: Vom standortbasierten Routing nicht unterstützte Funktionen'
TOCTitle: Vom standortbasierten Routing nicht unterstützte Funktionen
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994071(v=OCS.15)
ms:contentKeyID: 52056454
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vom standortbasierten Routing nicht unterstützte Funktionen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-12_

Das standortbasierte Routing wird nicht für die folgenden Arten von Interaktionen angewendet. Das standortbasierte Routing wird nicht erzwungen, wenn Lync-Endpunkte über die Funktionen mit PSTN-Endpunkten interagieren.

  - PSTN-Einwahl bei Konferenzen

  - Eingehende und ausgehende PSTN-Anrufe über die Reaktionsgruppe

  - Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen

  - Eingehende PSTN-Anrufe an den Ankündigungsdienst

  - Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden

Zum Erzwingen der Regeln für das standortbasierte Routing für die Arten von Interaktionen in der folgenden Liste müssen Sie das standortbasierte Routing für Konferenzen aktivieren:

  - PSTN-Einwahl von Konferenzen

  - Eskalationen von Peer-zu-Peer-Audiounterhaltungen zu Konferenzen unter Beteiligung von PSTN-Endpunkten

  - Anrufdurchstellung nach Rücksprache unter Beteiligung von PSTN-Endpunkten

Informationen zum Aktivieren von standortbasiertem Routing finden Sie unter [Standortbasiertes Routing für Konferenzen](lync-server-2013-location-based-routing-for-conferencing.md).

## Siehe auch

#### Weitere Ressourcen

[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

