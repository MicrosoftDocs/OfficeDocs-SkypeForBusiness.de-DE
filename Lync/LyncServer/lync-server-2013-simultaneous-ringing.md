---
title: 'Lync Server 2013: Paralleles Anrufen'
TOCTitle: Paralleles Anrufen
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994079(v=OCS.15)
ms:contentKeyID: 52056472
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paralleles Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn die angerufene Partei paralleles Anrufen eingerichtet hat, analysiert das standortbasierte Routing den Standort des anrufenden Teilnehmers und die Endpunkte des angerufenen Teilnehmers, um zu bestimmen, ob der Anruf weitergeleitet werden soll.

Die folgende Tabelle zeigt einen Benutzer, für den paralleles Anrufen konfiguriert ist, und das Ziel des parallelen Anrufs ist ein Benutzer am gleichen oder einem unbekannten Netzwerkstandort.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Eingehender Anruf aus dem öffentlichen Telefonnetz für</th>
<th>Am gleichen Netzwerkstandort wie der Angerufene</th>
<th>An einem anderen Netzwerkstandort als der Angerufene</th>
<th>An einem unbekannten Netzwerkstandort oder nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer</p></td>
<td><p>Paralleles Anrufen zugelassen</p></td>
<td><p>Paralleles Anrufen nicht zugelassen</p></td>
<td><p>Paralleles Anrufen nicht zugelassen</p></td>
</tr>
</tbody>
</table>

  
Die folgende Tabelle zeigt die Situation für einen Anruf von einem Lync-Benutzer (d. h. einem Lync-Anrufer) am gleichen Netzwerkstandort, einem anderen Netzwerkstandort oder einem unbekannten Netzwerkstandort. Der Angerufene hat einen Endpunkt im öffentlichen Telefonnetz (z. B. ein Mobiltelefon), der als Ziel für paralleles Anrufen konfiguriert ist. In diesem Szenario wird anhand des standortbasierten Routings bestimmt, ob der Anruf an das parallele Anrufziel (also das Mobiltelefon) des Angerufenen weitergeleitet werden soll oder nicht.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ziel für paralleles Anrufen</th>
<th>Am gleichen Netzwerkstandort wie der Angerufene</th>
<th>An einem anderen Netzwerkstandort als der Angerufene</th>
<th>An einem unbekannten Netzwerkstandort oder nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Paralleles Anrufen durch die VoIP-Weiterleitungsrichtline am Standort des Anrufers zugelassen</p></td>
<td><p>Paralleles Anrufen durch die VoIP-Weiterleitungsrichtline am Standort des Anrufers zugelassen</p></td>
<td><p>Paralleles Anrufen durch die VoIP-Weiterleitungsrichtlinie an Trunks, die nicht für standortbasiertes Routing aktiviert sind, zugelassen</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Weitere Ressourcen

[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

