---
title: 'Lync Server 2013: Durchstellung und Weiterleitung von Anrufen'
TOCTitle: Durchstellung und Weiterleitung von Anrufen
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994051(v=OCS.15)
ms:contentKeyID: 52056407
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Durchstellung und Weiterleitung von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Endpunkt im öffentlichen Telefonnetz beteiligt ist, analysiert das standortbasierte Routing den Standort des Endpunkts des Anrufers sowie des Endpunkts, an den der Anruf durchgestellt oder weitergeleitet werden soll (d. h. das Durchstellungs- oder Weiterleitungsziel). Das standortbasierte Routing bestimmt anhand des Standorts der beiden Endpunkte, ob der Anruf durchgestellt oder weitergeleitet werden soll.

Die folgende Tabelle veranschaulicht das Szenario eines Lync-Benutzers in einem Anruf mit einem Endpunkt im öffentlichen Telefonnetz, wenn der Lync-Benutzer den Anruf an einen anderen Lync-Benutzer durchstellt. Abhängig vom Netzwerkstandort des Endpunkts, an den durchgestellt werden soll, wirkt sich das standortbasierte Routing beim Durchstellen oder Weiterleiten auf das Routing aus.

### Einleitung der Anrufdurchstellung oder -weiterleitung

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzer, der die Durchstellung oder Weiterleitung des Anrufs einleitet</th>
<th>Der Zielendpunkt befindet sich am gleichen Netzwerkstandort wie der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet</th>
<th>Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet</th>
<th>Der Zielendpunkt befindet sich an einem unbekannten Netzwerkstandort oder einem Netzwerkstandort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
</tr>
</tbody>
</table>

  

Beispiel: Ein Lync-Benutzer, der einen Anruf mit einem Endpunkt im öffentlichen Telefonnetz führt, überträgt den Anruf an einen anderen Lync-Benutzer, der sich am gleichen Netzwerkstandort befindet. In diesem Fall ist die Durchstellung des Anrufs erlaubt.

Die folgende Tabelle veranschaulicht das Szenario eines Lync-Benutzers in einem Anruf mit einem anderen Lync-Benutzer, wenn einer der Benutzer den Anruf an einen Endpunkt im öffentlichen Telefonnetz durchstellt. Die Tabelle zeigt im Detail, wie sich das standortbasierte Routing, abhängig vom Standort des Benutzers, an den der Anruf durchgestellt werden soll, auf den Anruf auswirkt.

### Anrufdurchstellung oder -weiterleitung an einen Endpunkt im öffentlichen Telefonnetz

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Zielendpunkt für die Anrufdurchstellung oder -weiterleitung</th>
<th>Lync-Benutzer am gleichen Netzwerkstandort</th>
<th>Lync-Benutzer an verschiedenen Netzwerkstandorten</th>
<th>Ein oder beide Lync-Benutzer an einem unbekannten Netzwerkstandort oder einem nicht für standortbasiertes Routing aktivierten Netzwerkstandort</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Anrufweiterleitung oder -durchstellung wird von der VoIP-Routingrichtlinie am Standort des durchgestellten Benutzers zugelassen</p></td>
<td><p>Anrufweiterleitung oder -durchstellung wird von der VoIP-Routingrichtlinie am Standort des durchgestellten Benutzers zugelassen</p></td>
<td><p>Anrufweiterleitung oder -durchstellung wird von der VoIP-Richtlinie des durchgestellten Benutzers nur durch Trunks zugelassen, die nicht für standortbasiertes Routing aktiviert sind</p></td>
</tr>
</tbody>
</table>

  
Beispiel: Ein Lync-Benutzer in einem Anruf mit einem anderen Lync-Benutzer, der sich am gleichen Netzwerkstandort befindet, stellt den Anruf an einen Endpunkt im öffentlichen Telefonetz durch, und die Anrufdurchstellung wird zugelassen.

## Siehe auch

#### Weitere Ressourcen

[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

