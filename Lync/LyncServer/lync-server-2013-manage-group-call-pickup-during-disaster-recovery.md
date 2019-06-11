---
title: 'Lync Server 2013: Verwalten der Gruppenanruf Abholung während der Disaster Recovery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Verwalten der Gruppenanruf Abholung während der Disaster Recovery in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr zur Verfügung steht, ist der Dienst für den Sicherungspool nicht verfügbar. Beim Failover zum Sicherungspool werden die Benutzer in den Sicherungspool umgeleitet und befinden sich im Widerstands Modus. Im Resilienz-Modus können Benutzer keine Anrufe anderer Benutzer aufnehmen oder deren Anrufe von anderen Benutzern abgeholt werden. Nach Abschluss des Failovers können Benutzer die Gruppenanruf-Abholung wie gewohnt wieder verwenden.

Während des Failbacks an den primären Pool werden die Benutzer in den primären Pool umgeleitet und befinden sich wieder im Stabilitäts Modus. Die Funktion für die Gruppenanruf Abholung steht erst zur Verfügung, wenn die Benutzer den Stabilitäts Modus verlassen.

In diesem Abschnitt werden einige Überlegungen zur Abholung von Gruppen anrufen während der Disaster Recovery erläutert und auch die Benutzeroberfläche beschrieben.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Überlegungen zur Abholung von Gruppen anrufen während der Disaster Recovery

Während der Disaster Recovery verwenden Benutzer, die im Rahmen des Failovers an den Backup-Pool umgeleitet wurden, die Anruf Park Anwendung, die im Backup-Pool für die Gruppennummern der Anruf Abholung ausgeführt wird. Daher erfordert die Unterstützung für die Gruppenanruf Abholung während der Disaster Recovery, dass die Anwendung "Parken" im primären Pool und im Backup-Pool bereitgestellt und aktiviert wird.

Die Nummernbereiche für den Gruppenanruf-Pickup in der Umlaufbahn Tabelle des Anruf Parks müssen nach Abschluss des Failovers an den Sicherungspool an den Sicherungspool umgeleitet werden. Nach Abschluss des Failback-Vorgangs für den primären Pool müssen die Nummernbereiche wieder an den primären Pool umgeleitet werden. Verwenden Sie das Cmdlet " **Satz-CsCallParkOrbit** ", um die Gruppenanruf-Abhol Bereiche umzuleiten.

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie dem FQDN des neuen Pools alle Nummernbereiche für die Gruppenanruf Abholung neu zuweisen, die dem primären Pool zugeordnet waren. Wenn Sie dem neuen Poolnummern Bereiche erneut zuweisen möchten, können Sie das Cmdlet " **festlegen-CsCallParkOrbit** " verwenden. Details zum Cmdlet " **setCsCallParkOrbit** " finden Sie unter [Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Gruppenanruf-Pickup-Erfahrung beim Pool-Fehler

In der folgenden Tabelle sind die Erfahrungen der Gruppenanruf Abholung in den Phasen der Disaster Recovery zusammengefasst.

### <a name="user-experience-during-disaster-recovery"></a>Benutzererfahrung bei der Disaster Recovery

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anruf Zustand</th>
<th>Failover zu Backup-Pool</th>
<th>Failback zu primärem Pool</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><p><strong>Während des Failover-Vorgangs:</strong></p>
<ul>
<li><p>Gruppenanruf Abholung für Benutzer im Resilienz-Modus nicht verfügbar</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Gruppenanruf-Pickup verfügbar, wenn Benutzer, die aus der Widerstandsfähigkeit und dem Gruppenanruf-Nummernbereich abgeholt werden, in den Backup-Pool umgeleitet werden</p></li>
</ul></td>
<td><p><strong>Während des Failback-Vorgangs:</strong></p>
<ul>
<li><p>Gruppenanruf Abholung für Benutzer im Resilienz-Modus nicht verfügbar</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Gruppenanruf-Abholung ist verfügbar, wenn Benutzer, die aus der Widerstandsfähigkeit und dem Gruppenanruf-Nummernbereich abgeholt werden, zurück zum primären Pool umgeleitet werden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anrufe in der Gruppenanruf-Pickup-Warteschlange</p></td>
<td><p><strong>Während des Failover-Vorgangs:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Keine Anrufe in diesem Zustand</p></li>
</ul></td>
<td><p><strong>Während des Failback-Vorgangs:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Festgelegter Anruf</p></td>
<td><p><strong>Während des Failover-Vorgangs:</strong></p>
<ul>
<li><p>Anrufe bleiben in Verbindung</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Anrufe bleiben in Verbindung</p></li>
</ul></td>
<td><p><strong>Während des Failback-Vorgangs:</strong></p>
<ul>
<li><p>Anrufe bleiben in Verbindung</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Anrufe bleiben in Verbindung</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

