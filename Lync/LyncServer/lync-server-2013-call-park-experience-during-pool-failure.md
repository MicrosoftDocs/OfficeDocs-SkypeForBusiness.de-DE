---
title: 'Lync Server 2013: Anruf parken-Erfahrung während des Pool Fehlers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61913ba4ccee86047bbed4d6454988d37081f5a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Parken von Anrufen in lync Server 2013 beim Pool Ausfall

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-10_

Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, werden Anrufe, die geparkt, aber noch nicht abgerufen wurden, getrennt. Während eines Failovers in einen Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus. Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe parken, aber Sie können Anrufe in der Warteschleife platzieren und übertragen. Nach Abschluss des Failovers können Anrufe wieder wie gewohnt geparkt und abgerufen werden. Während des Failback können Benutzer Anrufe erst dann Parken, wenn Sie den Ausfall Sicherheitsmodus verlassen.

Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool bereitgestellt wird. Benutzer, die zum Sicherungspool umgeleitet werden, verwenden daher die Einstellungen für das Parken von anrufen, die für den Anwendung zum Parken von Anrufen im Sicherungspool konfiguriert sind.

In der folgenden Tabelle wird die Funktion zum Parken von Anrufen durch die Phasen der Notfallwiederherstellung zusammengefasst.

### <a name="user-experience-during-disaster-recovery"></a>Benutzererfahrung während der Notfallwiederherstellung

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufstatus</th>
<th>Wenn ein Ausfall auftritt</th>
<th>Während des Failovers</th>
<th>Während des Failbacks</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anruf noch nicht geparkt</p></td>
<td><p>Der Anruf bleibt verbunden, kann aber nicht geparkt werden.</p></td>
<td><ul>
<li><p>Während des Failovers kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</p></li>
<li><p>Nach Abschluss des Failovers kann der Anruf geparkt und abgerufen werden.</p></li>
</ul></td>
<td><ul>
<li><p>Während des Failback kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</p></li>
<li><p>Wenn das Failback abgeschlossen ist, kann der Anruf geparkt und abgerufen werden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anruf geparkt, aber noch nicht abgerufen</p></td>
<td><p>Anruf wird getrennt.</p></td>
<td><p>Keine Anrufe in diesem Zustand.</p></td>
<td><p>Der Anruf bleibt geparkt.</p></td>
</tr>
<tr class="odd">
<td><p>Geparkter Anruf wurde bereits abgerufen.</p></td>
<td><p>Der Anruf bleibt verbunden.</p></td>
<td><p>Der Anruf bleibt verbunden.</p></td>
<td><p>Der Anruf bleibt verbunden.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

