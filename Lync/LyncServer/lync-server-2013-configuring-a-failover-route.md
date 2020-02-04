---
title: 'Lync Server 2013: Konfigurieren einer Failoverroute'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Konfigurieren einer Failoverroute in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failover-Route für die Verwendung definieren kann, wenn der Dallas-GW1 für die Wartung ausgefallen ist oder anderweitig nicht verfügbar ist. Die folgenden Tabellen veranschaulichen die erforderliche Konfigurationsänderung.

### <a name="table-1-user-policy"></a>Tabelle 1 Benutzerrichtlinien

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzerrichtlinie</th>
<th>Telefonnutzung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standardanrufrichtlinie</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Lokale Redmond-Richtlinie</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Dallas-Anrufrichtlinie</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>Tabelle 2. Routen

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
<th>Routenname</th>
<th>Nummernmuster</th>
<th>Telefonnutzung</th>
<th>Stamm</th>
<th>Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lokale Redmond-Route</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d{7}) $</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Rot-GW1</p>
<p>Rot-GW2</p></td>
</tr>
<tr class="even">
<td><p>Lokale Route für Dallas</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d{7}) $</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Universelle Route</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Rot-GW1</p>
<p>Rot-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Route für Dallas-Benutzer</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


In Tabelle 1 wird nach der DallasUsers-Telefonnutzung in der Dallas-Anrufrichtlinie eine Telefonverwendung von GlobalPSTNHopoff hinzugefügt. Dies ermöglicht es anrufen mit der Dallas-Anrufrichtlinie, Routen zu verwenden, die für die GlobalPSTNHopoff-Telefonverwendung konfiguriert sind, wenn eine Route für die DallasUsers-Telefonnutzung nicht verfügbar ist.

</div>

<span> </span>

</div>

</div>

</div>

