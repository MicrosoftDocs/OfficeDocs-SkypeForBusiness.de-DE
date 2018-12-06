---
title: 'Lync Server 2013: Konfigurieren einer Failoverroute'
TOCTitle: Konfigurieren einer Failoverroute
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398581(v=OCS.15)
ms:contentKeyID: 49294458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer Failoverroute in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways "Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.

### Tabelle 1. Benutzerrichtlinie

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzerrichtlinie</th>
<th>Telefonverwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standardanrufrichtlinie</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Richtlinie für Ortsgespräche am Standort Redmond</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Anrufrichtlinie für Dallas</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### Tabelle 2. Routen

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
<th>Name der Route</th>
<th>Nummernmuster</th>
<th>Telefonverwendung</th>
<th>Trunk</th>
<th>Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Route für Ortsgespräche am Standort Redmond</p></td>
<td><p>^\+1(425|206|253)(\d{7})$</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Route für Ortsgespräche am Standort Dallas</p></td>
<td><p>^\+1(972|214|469)(\d{7})$</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Universalroute</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Route für Benutzer in Dallas</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


In Tabelle 1 wird die Telefonverwendung "GlobalPSTNHopoff" nach der Telefonverwendung "DallasUsers" zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für "GlobalPSTNHopoff" konfiguriert sind, wenn eine Route für die Telefonverwendung "DallasUsers" nicht verfügbar ist.

