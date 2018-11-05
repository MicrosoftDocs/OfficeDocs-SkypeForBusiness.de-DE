---
title: 'Lync Server 2013: Standort des Benutzers'
TOCTitle: Standort des Benutzers
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994073(v=OCS.15)
ms:contentKeyID: 52056447
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standort des Benutzers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Beim standortbasierten Routing werden die Netzwerkbereiche, Websites und Subnetze so zugrunde gelegt, wie sie in Lync Server definiert sind und von E9-1-1, Anrufsteuerung und Medienumgehung verwendet werden, um Einschränkungen für die Anrufweiterleitung zum Vermeiden von Gebührenumgehungen in öffentlichen Telefonnetzen zu implementieren. Der Standort eines Benutzers wird anhand des IP-Subnetzes bestimmt, von dem aus der bzw. die Lync-Endpunkt(e) verbunden wird/werden. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, von denen mehrere zu vom Administrator definierten Netzwerkbereichen zusammengefasst sind. Das standortbasierte Routing wird auf der Grundlage des Netzwerkstandorts des Benutzers durchgesetzt.

Regeln für das standortbasierte Routing werden auf der Grundlage des Netzwerkstandorts angewendet, was bedeutet, dass ein bestimmter Satz Regeln auf alle Endpunkte angewendet wird, die für standortbasiertes Routing aktiviert sind und sich am gleichen Netzwerkstandort befinden. Administratoren können standortbasiertes Routing auf Netzwerkstandorte anwenden, die dies erfordern.

Richtlinien für das VoIP-Routing können auf der Grundlage von Netzwerkstandorten definiert werden, um ein bestimmtes Gateway in das öffentliche Telefonnetz zu definieren, das dann von allen Benutzern, die sich am gleichen Netzwerkstandort befinden, für Verbindungen mit Rufnummern im öffentlichen Telefonnetz verwendet werden muss. Derartige Richtlinien für das VoIP-Routing haben Vorrang gegenüber dem in der VoIP-Richtlinie des Benutzers definierten Routing, wenn sich der Benutzer an einem Netzwerkstandort befindet, für den standortbasiertes Routing aktiviert ist, und verhindern das Routing von Anrufen über andere Gateways in das öffentliche Telefonnetz, die für standortbasiertes Routing aktiviert sind. Wenn ein Lync-Benutzer einen Anruf in das öffentliche Telefonnetz tätigt, bestimmt die VoIP-Richtlinie des Benutzers, ob der Benutzer zum Tätigen des Anrufs autorisiert werden kann. Wenn die VoIP-Richtlinie des Benutzers dem Benutzer das Führen des Anrufs erlaubt, bestimmt das standortbasierte Routing, von welchem Gateway in das öffentliche Telefonnetz der Anruf ausgehen soll. Das standortbasierte Routing nimmt diese Bestimmung auf der Grundlage des Standorts des Benutzers vor.

Der Standort eines Benutzers kann auf folgende Weise kategorisiert werden:

  - Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für standortbasiertes Routing aktiviert ist, und seine direkte interne Durchwahlnummer endet bei einem Gateway in das öffentliche Telefonnetz, das sich am gleichen Netzwerkstandort (d. h. Firmenstandort) befindet. Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Aus dem öffentlichen Telefonnetz für den Benutzer eingehende Anrufe werden an Endpunkte geroutet, die sich am gleichen Netzwerkstandort wie das Gateway in das öffentliche Telefonnetz befinden.

  - Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich von dem Netzwerkstandort unterscheidet, an dem sich das Gateway in das öffentliche Telefonnetz befindet (d. h., der Benutzer ist zu einem anderen Unternehmensstandort gereist). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Für den Benutzer aus dem öffentlichen Telefonnetz eingehende Anrufe werden nicht an Endpunkte geroutet, die sich an anderen Standorten als das Gateway in das öffentliche Telefonnetz befinden, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

  - Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für die Lync Server-Bereitstellung unbekannt ist, erfolgt das Routing ausgehender Anrufe anhand der VoIP-Richtlinie, die dem Benutzer zugeordnet ist, zu Gateways in das öffentliche Telefonnetz, die nicht an die Einschränkungen des standortbasierten Routings gebunden sind. Eingehende Anrufe aus dem öffentlichen Telefonnetz werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

## Siehe auch

#### Weitere Ressourcen

[Anleitungen für das standortbasierte Routing in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

