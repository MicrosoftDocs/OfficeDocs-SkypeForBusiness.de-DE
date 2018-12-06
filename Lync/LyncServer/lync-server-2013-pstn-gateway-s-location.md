---
title: 'Lync Server 2013: Standort eines PSTN-Gateways'
TOCTitle: Standort eines PSTN-Gateways
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994031(v=OCS.15)
ms:contentKeyID: 52056327
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standort eines PSTN-Gateways in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Für Anrufe, die über PSTN-Gateways und Nebenstellenanlagen weitergeleitet werden, sind möglicherweise je nach Standort dieser Systeme Einschränkungen für standortbasiertes Routing erforderlich. Standortbasiertes Routing kann mit unterschiedlicher Granularität bis hinunter zu einer Pro-Trunk-Basis aktiviert werden.

Wenn standortbasiertes Routing für einen Trunk aktiviert ist, gelten die folgenden Regeln:

  - Regeln, die für diesen Trunk definiert sind, werden nur auf Anrufe angewendet, die über diesen Trunk weitergeleitet werden.

  - Damit ein Umgehen von Gebühren für das Telefonfestnetz (Public Switched Telephone Network, PSTN) verhindert wird, wenn Anrufe aus einem Netzwerkstandort eingegangen sind, der nicht mit dem Netzwerkstandort identisch ist, in dem sich das PSTN-Gateway befindet, erfolgt mit dem standortbasierten Routing die Zuweisung eines Netzwerkstandorts zu einem bestimmten Trunk.

Trunks können auf zwei Arten für standortbasiertes Routing aktiviert werden:

  - Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonfestnetz weiterleitet. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endgeräte weitergeleitet, die sich im selben Netzwerkstandort befinden wie der Trunk.

  - Der Trunk ist für einen Vermittlungsserverpeer definiert, der Anrufe nicht an das Telefonfestnetz weiterleitet, sondern Benutzer bedient, die herkömmliche Telefone in einem statischen Standort (also Nebenstellentelefone) verwenden. Für diese spezielle Konfiguration wird für alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, angenommen, dass sie aus demselben Netzwerkstandort kommen wie der Trunk. Für Anrufe von Telefonfestnetzbenutzern gilt dieselbe Erzwingung von standortbasiertem Routing wie für Lync-Benutzer, die sich im selben Netzwerkstandort befinden wie der Trunk. Sind zwei Nebenstellenanlagen, die sich in unterschiedlichen Netzwerkstandorten befinden, über Lync Server miteinander verbunden, gestattet standortbasiertes Routing Weiterleitungen von einem Nebenstellenanlagenendgerät in einem Netzwerkstandort an ein anderes Nebenstellenanlagenendgerät im anderen Netzwerkstandort. Dieses Szenario wird von standortbasiertem Routing nicht blockiert. Zusätzlich zu diesem Szenario und ähnlich wie für einen Lync-Benutzer im selben Standort können Endgeräte, die mit einem Vermittlungsserverpeer mit dieser Konfiguration verbunden sind, Anrufe mit einem anderen Vermittlungsserverpeer führen, der Anrufe nicht an das Telefonfestnetz weiterleitet (d. h. ein Endgerät, das mit einer anderen Nebenstellenanlgae verbunden ist), und zwar unabhängig davon, welchem Netzwerkstandort der Vermittlungsserverpeer zugeweisen ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anrufdurchstellungen und Anrufweiterleitungen, die Telefonfestnetzendgeräte betreffen, unterliegen dem standortbasierten Routing, sodass nur PSTN-Gateways verwendet werden, die für einen solchen Vermittlungsserverpeer als lokal definiert sind.

## Siehe auch

#### Weitere Ressourcen

[Anleitungen für das standortbasierte Routing in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

