---
title: Konfigurieren von Enterprise-VoIP in Lync Server 2013
TOCTitle: Konfigurieren von Enterprise-VoIP in Lync Server 2013
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994041(v=OCS.15)
ms:contentKeyID: 52056390
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn Sie Enterprise-VoIP bereitstellen möchten, müssen Sie Folgendes konfigurieren:

  - Erstellen eines Trunks

  - Definieren einer VoIP-Richtlinie

  - Definieren einer VoIP-Route

  - Aktivieren von Benutzern für Enterprise-VoIP

## Erstellen eines Trunks

Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren. Für standortbasiertes Routing müssen Sie eine Trunkkonfiguration pro Trunk erstellen. Verwenden Sie den Lync ServerTopologie-Generator, um Ihre Trunks zu definieren, und verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsTrunkConfiguration" oder die Lync Server-Systemsteuerung, um die entsprechenden Trunkkonfigurationen zu definieren. Weitere Informationen, wie standortbasiertes Routing für Trunkkonfigurationen aktiviert werden kann, finden Sie im Abschnitt "Aktivieren von standortbasiertem Routing zu Trunks" im Thema [Aktivieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Für dieses Beispiel sind in der folgenden Tabelle die Trunks aufgeführt, die im vorliegenden Szenario verwendet werden.

Weitere Informationen hierzu finden Sie unter [Definieren von zusätzlichen Trunks im Topologie-Generator in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Trunkname</th>
<th>Systemtyp</th>
<th>Name</th>
<th>Standort</th>
<th>Vermittlungsserver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>PSTN-Gateway</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>PSTN-Gateway</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>PBX (Nebenstellenanlage)</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 HYD-PBX</p></td>
<td><p>PBX (Nebenstellenanlage)</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>



## Definieren von VoIP-Richtlinien

Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren. Definieren Sie eine VoIP-Richtlinie, um für eine Teilmenge von Benutzern Einschränkungen für standortbasiertes Routing zu erzwingen, wenn nur für einige Benutzer die Verwendung von standortbasiertem Routing erforderlich. Für dieses Beispiel werden in der folgenden Tabelle die VoIP-Richtlinien veranschaulicht, die im vorliegenden Szenario verwendet werden. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

Weitere Informationen hierzu finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Richtlinie 1</th>
<th>VoIP-Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinien-ID</p></td>
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>PSTN usages</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>



## Definieren von VoIP-Routen

Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren. Für dieses Beispiel werden in der folgenden Tabelle die VoIP-Routen veranschaulicht, die im vorliegenden Szenario verwendet werden. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

Weitere Informationen hierzu finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Route 1</th>
<th>VoIP-Route 2</th>
<th>VoIP-Route 3</th>
<th>VoIP-Route 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Delhi route</p></td>
<td><p>Hyderabad route</p></td>
<td><p>PBX Del route</p></td>
<td><p>PBX Hyd route</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Delhi usage</p></td>
<td><p>Hyderabad usage</p></td>
<td><p>PBX Del usage</p></td>
<td><p>PBX Hyd usage</p></td>
</tr>
<tr class="odd">
<td><p>Trunk</p></td>
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Trunk 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>



## Aktivieren von Benutzern für Enterprise-VoIP

Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie ihnen eine der VoIP-Richtlinien zu, die Sie zuvor definiert haben. Für dieses Beispiel werden in der folgenden Tabelle die Zuweisungen veranschaulicht, die im vorliegenden Szenario verwendet werden. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

Weitere Informationen hierzu finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Benutzer am Standort Delhi</th>
<th>Benutzer am Standort Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zugewiesene VoIP-Richtlinie</p></td>
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>Beispielbenutzer</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>



## Siehe auch

#### Weitere Ressourcen

[Konfigurieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

