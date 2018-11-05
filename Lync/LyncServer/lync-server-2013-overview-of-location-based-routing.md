---
title: 'Lync Server 2013: Übersicht über das standortbasierte Routing'
TOCTitle: Übersicht über das standortbasierte Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994032(v=OCS.15)
ms:contentKeyID: 52056329
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über das standortbasierte Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das standortbasierte Routing stellt einen neuen Regelsatz zur Verfügung, mit dem das Routing nationaler und internationaler PSTN-Anrufe modifiziert werden kann, um eine Gebührenumgehung zu verhindern. Beim standortbasierten Routing lassen sich die Regeln flexibel auf bestimmte Regionen und Gateways und sogar auf bestimmte Benutzergruppen beschränken.

Die folgenden Szenarien sollen die wichtigsten Einschränkungen aufzeigen, die mithilfe des standortbasierten Routings durchgesetzt werden können:

  - Ausgehende Anrufe – Das standortbasierte Routing kann ausgehende Anrufe auf PSTN-Gateways beschränken, die sich in derselben Region befinden wie der Anrufer, um so eine Umgehung von PSTN-Gebühren zu verhindern. Auf diese Weise wird vermieden, dass Anrufe von einem PSTN-Gateway abgehen, das sich in einer anderen Region befindet als der Anrufer.

  - Eingehende Anrufe – Das standortbasierte Routing kann eingehende PSTN-Verbindungen mit Lync-Endpunkten verhindern, wenn das PSTN-Gateway, über das die Verbindung geroutet wird, sich nicht in derselben Region befindet, wie der angerufene Lync-Benutzer.

  - Unbekannte Regionen – Mit standortbasiertem Routing lassen sich eingehende und ausgehende PSTN-Verbindungen für Benutzer einschränken, die sich an nicht eindeutig bestimmbaren Standorten aufhalten (d. h. Remotebenutzer, die eine Verbindung über das Internet herstellen oder sich in unbekannten Regionen aufhalten).

  - Internationale Regionen – Mit standortbasiertem Routing können ausgehende Anrufe obligatorisch über internationale PSTN-Gateways geroutet werden, wenn am Standort des Benutzers kein lokales Gateway zur Verfügung steht.

## Siehe auch

#### Weitere Ressourcen

[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

