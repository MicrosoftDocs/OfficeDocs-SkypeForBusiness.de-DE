---
title: 'Lync Server 2013: Eingehende Anrufe'
TOCTitle: Eingehende Anrufe
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994038(v=OCS.15)
ms:contentKeyID: 52056356
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eingehende Anrufe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Routing von eingehenden Anrufen an Benutzer, die für standortbasiertes Routing aktiviert sind, hängt vom Standort des Endgeräts des Benutzers ab. Das Routing von eingehenden Anrufen ist auf folgende Weise betroffen. Gibt es für einen Benutzer einen Anruf an ein Endgerät, das sich in einem Standort mit aktiviertem standortbasiertem Routing befindet, und gehört das Endgerät zum selben Netzwerkstandort wie das PSTN-Gateway, wird der Anruf weitergeleitet. Gibt es für einen Benutzer einen Anruf an ein Endgerät, das sich in einem Standort mit aktiviertem standortbasiertem Routing befindet, und gehört das Endgerät nicht zum selben Netzwerkstandort wie das PSTN-Gateway, wird der Anruf nicht weitergeleitet. Gibt es für einen Benutzer keine Endgeräte in dem Netzwerkstandort, zu dem das PSTN-Gateway gehört, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet und eine Benachrichtigung über einen verpassten Anruf an den angerufenen Benutzer gesendet.

Die Anrufweiterleitungseinstellungen eines Benutzers, für den standortbasiertes Routing aktiviert ist, werden auch weiterhin erzwungen, aber weitergeleitete Anrufe werden den Einschränkungen unterworfen, die wegen des standortbasierten Routings für den Benutzer gelten.

In der folgenden Tabelle wird dargestellt, wie sich standortbasiertes Routing in Abhängigkeit vom Standort des Endgeräts des Angerufenen auf eingehende Anrufe auswirkt. Der Netzwerkstandort des PSTN-Gateways ist für standortbasiertes Routing aktiviert, und das standortbasierte Routing gestattet nur Routing von Telefonfestnetzanrufen an Endgeräte im selben Netzwerkstandort.

### Angerufener, der einen eingehenden Anruf aus dem Telefonfestnetz (PSTN) empfängt

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Endgerät des Angerufenen befindet sich im selben Netzwerkstandort wie das PSTN-Gateway</th>
<th>Endgerät des Angerufenen befindet sich nicht im selben Netzwerkstandort wie das PSTN-Gateway</th>
<th>Endgerät des Angerufenen befindet sich in unbekanntem Netzwerkstandort oder ist nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routing eines eingehenden Telefonfestnetzanrufs</p></td>
<td><p>Eingehender Anruf wird an die Endgeräte des Angerufenen weitergeleitet</p></td>
<td><p>Eingehender Anruf wird nicht an die Endgeräte des Angerufenen weitergeleitet</p></td>
<td><p>Eingehender Anruf wird nicht an die Endgeräte des Angerufenen weitergeleitet</p></td>
</tr>
</tbody>
</table>

  

## Siehe auch

#### Weitere Ressourcen

[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

