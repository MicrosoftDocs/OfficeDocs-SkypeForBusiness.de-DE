---
title: 'Lync Server 2013: Ausgehende Anrufe'
TOCTitle: Ausgehende Anrufe
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994049(v=OCS.15)
ms:contentKeyID: 52056381
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausgehende Anrufe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Routing von ausgehenden Anrufen von Benutzern, die für standortbasiertes Routing aktiviert sind, wird vom Netzwerkstandort des Endpunkts des Benutzers beeinflusst. In der folgenden Tabelle wird dargestellt, wie sich standortbasiertes Routing in Abhängigkeit vom Standort des Endpunkts des Anrufers auf ausgehende Anrufe auswirkt.

### Der Anrufer führt einen ausgehenden Anruf in das öffentliche Telefonnetz

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Benutzerendpunkt befindet sich an einem Netzwerkstandort, der für standortbasiertes Routing aktiviert ist</th>
<th>Benutzerendpunkt befindet sich an einem unbekannten Netzwerkstandort oder einem Standort der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung ausgehender Anrufe</p></td>
<td><p>Der Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
<td><p>Der Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</p></td>
</tr>
<tr class="even">
<td><p>Routing ausgehender Anrufe</p></td>
<td><p>Das Routing des Anrufs erfolgt gemäß der VoIP-Routingrichtlinie des Netzwerkstandorts</p></td>
<td><p>Der Anruf wird gemäß der VoIP-Richtlinie des Benutzers geroutet, jedoch nur durch Trunks, die nicht für standortbasiertes Routing aktiviert sind (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Weitere Ressourcen

[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

