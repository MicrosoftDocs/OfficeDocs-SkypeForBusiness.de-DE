---
title: 'Lync Server 2013: Konfigurieren einer Failover-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520062"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Konfigurieren einer Failover-Route in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways „Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.

### <a name="table-1-user-policy"></a>Tabelle 1. Benutzerrichtlinie

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
<td><p>Lokal</p>
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


### <a name="table-2-routes"></a>Tabelle 2. Routen

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
<th>Stamm</th>
<th>Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Route für Ortsgespräche am Standort Redmond</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d {7} ) $</p></td>
<td><p>Lokal</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Route für Ortsgespräche am Standort Dallas</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d {7} ) $</p></td>
<td><p>Lokal</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Universalroute</p></td>
<td><p>^\+? (\d *) $</p></td>
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
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


In Tabelle 1 wird die Telefonverwendung „GlobalPSTNHopoff“ nach der Telefonverwendung „DallasUsers“ zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für „GlobalPSTNHopoff“ konfiguriert sind, wenn eine Route für die Telefonverwendung „DallasUsers“ nicht verfügbar ist.

</div>

<span> </span>

</div>

</div>

</div>

