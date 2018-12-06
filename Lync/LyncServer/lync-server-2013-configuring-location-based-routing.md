---
title: 'Lync Server 2013: Konfigurieren von standortbasiertem Routing'
TOCTitle: Konfigurieren von standortbasiertem Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994036(v=OCS.15)
ms:contentKeyID: 52056352
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von standortbasiertem Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Lync Server 2013 CU1, standortbasiertes Routing ist ein Feature von Enterprise-VoIP. Standortbasiertes Routing ist ein Anrufverwaltungsfeature, das steuert, wie Anrufe von Lync Server 2013 CU1 weitergeleitet werden. Es erzwingt auf Basis des Standorts des jeweiligen Lync-Benutzers Einschränkungen, ob Anrufe an Nebenstellenanlagen- oder Telefonfestnetzziele weitergeleitet werden können. Bei standortbasiertem Routing werden entsprechend dem Netzwerkstandort des Anrufers Autorisierungsregeln auf Telefonfestnetzanrufe angewendet. Der Standort des Anrufers wird anhand des Netzwerkstandorts ermittelt, dem das Netzwerksubnetz zugewiesen ist, zu dem der Anschluss des Anrufers gehört. Damit standortbasiertes Routing konfiguriert werden kann, muss zunächst Enterprise-VoIP bereitgestellt und müssen dann Netzwerkregionen, -standorte und -subnetze konfiguriert werden. Dadurch wird die Grundlage für das Aktivieren von standortbasiertem Routing eingerichtet.

Bevor Sie standortbasiertes Routing bereitstellen, müssen Sie zunächst Enterprise-VoIP bereitstellen, Netzwerkregionen und -standorte konfigurieren sowie den Netzwerkstandorten Netzwerksubnetze zuweisen. Nachdem Sie dies abgeschlossen haben, können Sie standortbasiertes Routing konfigurieren. Beschreibungen der Schritte, wie Netzwerkregionen, -standorte und -subnetze konfiguriert werden, finden Sie unter [Bereitstellen von erweiterten Enterprise-VoIP-Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

In diesem Abschnitt werden Sie durch die Konfiguration von standortbasiertem Routing geleitet, wobei das folgende Beispiel als Veranschaulichung verwendet wird.

![Enterprise VoIP: standortbasiertes Routing (Beispiel)](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise VoIP: standortbasiertes Routing (Beispiel)")

  
In der folgenden Tabelle sind die Benutzer aufgeführt, die in diesem Beispiel definiert sind.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Endgerätetyp</th>
<th>Ort</th>
<th>Benutzer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Delhi, Unternehmensbüro</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad, Unternehmensbüro</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Unbekannt (z. B. Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX (Nebenstellenanlage)</p></td>
<td><p>Delhi, Unternehmensbüro</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX (Nebenstellenanlage)</p></td>
<td><p>Hyderabad, Unternehmensbüro</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>Telefonfestnetz (PSTN)</p></td>
<td><p>Unbekannt</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

In der folgenden Tabelle sind die Systeme aufgeführt, die in diesem Beispiel veranschaulicht werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Ort</th>
<th>Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1-Pool</p></td>
<td><p>Beliebig</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, Vermittlungsserver</p></td>
<td><p>Beliebig</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Gateway 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Gateway 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-PBX</p></td>
</tr>
</tbody>
</table>


## In diesem Abschnitt

  - [Konfigurieren von Enterprise-VoIP in Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Aktivieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen von erweiterten Enterprise-VoIP-Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

