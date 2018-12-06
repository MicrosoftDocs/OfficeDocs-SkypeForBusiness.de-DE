---
title: 'Lync Server 2013: Bereitstellungsvorgang beim standortbasierten Routing'
TOCTitle: Bereitstellungsvorgang beim standortbasierten Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994055(v=OCS.15)
ms:contentKeyID: 52056419
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsvorgang beim standortbasierten Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieses Thema gibt einen Überblick des Prozesses beim Konfigurieren des standortbasierten Routings. Sie müssen Lync ServerEnterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie standortbasiertes Routing konfigurieren können. Die für das standortbasierte Routing erforderlichen Komponenten sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.

### Bereitstellungsvorgang beim standortbasierten Routing

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Erforderliche Gruppen und Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bereitstellen von Enterprise-VoIP</p></td>
<td><ul>
<li><p>Konfigurieren von Trunks</p></li>
<li><p>Erstellen von VoIP-Richtlinien</p></li>
<li><p>Definieren von VoIP-Routen</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Bereitstellen von Enterprise-VoIP</p></td>
</tr>
<tr class="even">
<td><p>Überprüfen der Bereitstellung von Enterprise-VoIP</p></td>
<td><p></p></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Konfigurieren von Netzwerkregionen, Standorten und Subnetzen</p></td>
<td><ul>
<li><p>Erstellen von Netzwerkregionen</p></li>
<li><p>Erstellen von Netzwerkstandorten</p></li>
<li><p>Zuordnen von Subnetzen zu Netzwerkstandorten</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Grundlegende Informationen zu Netzwerkregionen, Standorten und Subnetzen<br />
Erstellen oder Ändern einer Netzwerkregion<br />
Erstellen oder Ändern eines Netzwerkstandorts<br />
Zuordnen eines Subnetzes zu einem Netzwerkstandort</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von standortbasiertem Routing</p></td>
<td><ul>
<li><p>Erstellen von VoIP-Routingrichtlinien</p></li>
<li><p>Definieren einer separaten Trunkkonfiguration pro Trunk</p></li>
<li><p>Ändern von VoIP-Richtlinien</p></li>
<li><p>Aktivieren der Konfiguration für das standortbasierte Routing</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Beispielbereitstellung

Die folgende Bereitstellung dient dazu, die durch das standortbasierte Routing in Kraft gesetzten Mechanismen weiter zu erläutern.

![Topologie für das standortbasierte Routing](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "Topologie für das standortbasierte Routing")

## Eingehende Anrufe aus dem öffentlichen Telefonnetz

Ein Administrator kann den Trunk, der für das Routen von Anrufen an "Gateway Standort 1" definiert ist, für standortbasiertes Routing aktivieren und das "Gateway Standort 1" dem Standort 1 zuordnen. Nach der Aktivierung werden Anrufe, die über das "Gateway Standort 1" geroutet werden, nur an Benutzer weitergeleitet, die sich am Standort 1 befinden. Alle Anrufe, die über den Trunk "Gateway Standort 1" geroutet werden und für Benutzer an einem anderen Standort - z. B. Standort 2 - bestimmt sind, werden blockiert, um eine Umgehung der Gebühren im öffentlichen Telefonnetz zu vermeiden.

Für alle eingehenden Anrufe aus dem öffentlichen Telefonnetz über "Gateway Standort 1" wird nur das Routing an Endpunkte zugelassen, die sich am Standort 1 befinden. Wenn z. B. "Lync-Benutzer 1" an den Standort 2 reist, werden alle eingehenden Anrufe aus dem öffentlichen Telefonnetz über "Gateway Standort 1" nicht an die "Lync-Benutzer 1"-Endpunkte geroutet, die sich an Standort 2 befinden. Die gleiche Routingregel wird angewendet, wenn "Lync-Benutzer 1" an einen unbekannten Netzwerkstandort reist, an dem der Standort des Benutzers nicht bestimmt werden kann.

Die folgende Tabelle umreißt die Benutzererfahrung von "Lync-Benutzer 1" in diesem Kontext.


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
<th>Endpunkte von Lync-Benutzer 1 am Netzwerkstandort 1</th>
<th>Endpunkte von Lync-Benutzer 1 am Netzwerkstandort 2</th>
<th>Endpunkte von Lync-Benutzer 1 an einem unbekannten Netzwerkstandort</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Eingehende Anrufe aus dem öffentlichen Telefonnetz an Lync-Benutzer 1</p></td>
<td><p>Anrufe werden an Endpunkte an diesem Standort geroutet</p></td>
<td><p>Anrufe werden nicht an Endpunkte an diesem Standort geroutet</p></td>
<td><p>Anrufe werden nicht an Endpunkte an diesem Standort geroutet</p></td>
</tr>
</tbody>
</table>


## Ausgehende Anrufe über das öffentliche Telefonnetz

Auf VoIP-Routen wird sowohl in VoIP-Richtlinien, die Benutzern direkt zugeordnet sind, als auch in VoIP-Richtlinien, die Netzwerkstandorten zugewiesen sind, verwiesen. Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders zu routen. Beispielsweise kann ein Administrator eine VoIP-Routingrichtlinie für alle Benutzer am Netzwerkstandort 1 definieren, die alle ausgehenden Anrufe über das "Gateway Standort 1" routet, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das "Gateway Standort 2" definiert. Solange sich diese Benutzer am Netzwerkstandort 1 befinden, werden ihre ausgehenden Anrufe über das "Gateway Standort 1" geroutet.

Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für standortbasiertes Routing konfiguriert ist, setzt die VoIP-Routingrichtlinie des Netzwerkstandorts die in der VoIP-Richtlinie des Benutzers festgelegte Route außer Kraft. Diese Regel ist besonders für Benutzer, die vorübergehend an einen anderen Standort umziehen, nützlich. In diesem besonderen Fall verwendet ein Benutzer immer ein Gateway, das lokal zu seinem Standort ist; wenn sich "Lync-Benutzer 3" an "Standort 2" befindet, werden seine sämtlichen ausgehenden Anrufe über das "Gateway Standort 2" geroutet, wenn er jedoch zum Standort 1 reist, werden alle seine ausgehenden Anrufe, die er vornimmt, während er sich am Standort 1 aufhält, über das "Gateway Standort 1" geroutet.

Die folgende Tabelle veranschaulicht die Benutzererfahrung von Lync-Benutzer 1 beim Führen eines ausgehenden Anrufs von den folgenden Netzwerkstandorten.


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
<th>Netzwerkstandort 1</th>
<th>Netzwerkstandort 2</th>
<th>Unbekannter Netzwerkstandort oder nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung ausgehender Anrufe</p></td>
<td><p>VoIP-Richtlinie Lync-Benutzer 1</p></td>
<td><p>VoIP-Richtlinie Lync-Benutzer 1</p></td>
<td><p>VoIP-Richtlinie Lync-Benutzer 1</p></td>
</tr>
<tr class="even">
<td><p>Routing ausgehender Anrufe</p></td>
<td><p>VoIP-Routingrichtlinie Standort 1</p></td>
<td><p>VoIP-Routingrichtlinie Standort 2</p></td>
<td><p>VoIP-Richtlinie des Benutzers und nur zu Systemen, die nicht für standortbasiertes Routing aktiviert sind</p></td>
</tr>
</tbody>
</table>


## Durchstellung und Weiterleitung von Anrufen

Wenn Anrufe durchgestellt oder weitergeleitet werden, wirkt sich das standortbasierte Routing auf das Routing der Anrufe aus.

Die folgende Tabelle zeigt Lync-Benutzer 1 beim Durchstellen oder Weiterleiten eines Anrufs aus dem öffentlichen Telefonnetz an einen anderen Lync-Benutzer.


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
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer an einem Netzwerkstandort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
</tr>
</tbody>
</table>

  
Die folgende Tabelle zeigt, wie sich standortbasiertes Routing auf das Routing des Anrufs abhängig vom Standort des an einen Endpunkt im öffentlichen Telefonnetz durchgestellten Lync-Benutzers (Lync-Benutzer 2, Lync-Benutzer 4 usw.) auswirkt


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpunkt, an den der Anruf durchgestellt oder weitergeleitet wird</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer an einem Netzwerkstandort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Die Durchstellung oder Weiterleitung des Anrufs erfolgt durch die VoIP-Routingrichtlinie von Standort 1 und geht über das Gateway von Standort 1 aus</p></td>
<td><p>Die Durchstellung oder Weiterleitung des Anrufs erfolgt durch die VoIP-Routingrichtlinie von Standort 2 und geht über das Gateway von Standort 2 aus</p></td>
<td><p>Die Durchstellung oder Weiterleitung des Anrufs erfolgt über die VoIP-Richtlinie des Lync-Benutzers und geht über ein Gateway aus, das nicht für standortbasiertes Routing aktiviert ist (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


## Paralleles Anrufen

Nachdem das standortbasierte Routing in der Beispieltopologie konfiguriert wurde, werden die folgenden Interaktionen durchgesetzt.

Die folgende Tabelle zeigt, ob das standortbasierte Routing paralleles Anrufen (gleichzeitiges Klingeln) für verschiedene Lync-Benutzer (d. h. Lync-Benutzer 2, Lync-Benutzer 4 usw.) zulässt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ziel des eingehenden Anrufs aus dem öffentlichen Telefonnetz</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer an einem Netzwerkstandort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1</p></td>
<td><p>Paralleles Anrufen wird zugelassen</p></td>
<td><p>Paralleles Anrufen wird nicht zugelassen</p></td>
<td><p>Paralleles Anrufen wird nicht zugelassen</p></td>
</tr>
</tbody>
</table>

  
Die folgende Tabelle zeigt, ob das standortbasierte Routing paralleles Anrufen (gleichzeitiges Klingeln) an einen Endpunkt im öffentlichen Telefonnetz von verschiedenen Lync-Benutzern (d. h. Lync-Benutzer 2, Lync-Benutzer 4 usw.) zulässt.


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
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer an einem Netzwerkstandort, der nicht für standortbasiertes Routing aktiviert ist</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mobiltelefon von Lync-Benutzer (Endpunkt im öffentlichen Telefonnetz)</p></td>
<td><p>Der Anruf wird durch die VoIP-Routingrichtlinie von Netzwerkstandort 1 geroutet und geht über das Gateway von Standort 1 aus</p></td>
<td><p>Der Anruf wird durch die VoIP-Routingrichtlinie von Netzwerkstandort 2 geroutet und geht über das Gateway von Standort 2 aus</p></td>
<td><p>Der Anruf wird durch die VoIP-Richtlinie des Anrufers geroutet und geht über ein Gateway in das öffentliche Telefonnetz aus, das nicht für standortbasiertes Routing aktiviert ist</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Weitere Ressourcen

[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

