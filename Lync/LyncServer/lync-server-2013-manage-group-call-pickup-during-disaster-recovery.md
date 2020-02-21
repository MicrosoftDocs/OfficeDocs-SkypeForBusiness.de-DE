---
title: 'Lync Server 2013: Verwalten der gruppenanrufannahme während der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Verwalten der gruppenanrufannahme während der Notfallwiederherstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, wird ein Failover des Diensts an den Sicherungspool ausgeführt. Während des Failovers auf den Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus. Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe anderer Benutzer aufnehmen oder Ihre Anrufe von anderen Benutzern abholen lassen. Nach Abschluss des Failovers können Benutzer die gruppenanrufannahme wie gewohnt wieder verwenden.

Während des Failback zum primären Pool werden Benutzer zum primären Pool umgeleitet und befinden sich erneut im Ausfall Sicherheitsmodus. Die Funktion für die gruppenanrufannahme ist erst verfügbar, wenn sich die Benutzer außerhalb des Ausfall Sicherheitsmodus befinden.

In diesem Abschnitt werden einige Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung erläutert, und es wird auch die Benutzeroberfläche beschrieben.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung

Während der Notfallwiederherstellung verwenden Benutzer, die als Teil des Failover-Prozesses zum Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool für die Nummern der Anrufannahme Gruppe ausgeführt werden. Unterstützung für die gruppenanrufannahme während der Notfallwiederherstellung erfordert daher, dass die Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.

Die Gruppenanruf-Pickup-Nummernbereiche in der Tabelle "Parken von Anrufen" müssen nach Abschluss des Failover-Prozesses an den Sicherungspool an den Sicherungspool umgeleitet werden. Die Nummernbereiche müssen zurück zum primären Pool umgeleitet werden, nachdem der Failback-Prozess für den primären Pool abgeschlossen ist. Verwenden Sie das Cmdlet "CsCallParkOrbit", um die Gruppenanruf **-** Abhol Bereiche umzuleiten.

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie alle Gruppenanruf Pickup-Nummernbereiche, die dem primären Pool zugeordnet sind, dem FQDN des neuen Pools zuweisen. Um Nummernbereiche dem neuen Pool neu zuzuweisen, können Sie das Cmdlet " **CsCallParkOrbit** " verwenden. Ausführliche Informationen zum Cmdlet " **CsCallParkOrbit** " finden Sie unter [festlegen-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Erfahrung bei der gruppenanrufannahme beim Pool Ausfall

Die folgende Tabelle enthält eine Zusammenfassung der Gruppenanruf-Pickup-Umgebung in den Phasen der Notfallwiederherstellung.

### <a name="user-experience-during-disaster-recovery"></a>Benutzererfahrung während der Notfallwiederherstellung

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufstatus</th>
<th>Failover auf Sicherungspool</th>
<th>Failback zum primären Pool</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><p><strong>Während des Failover-Prozesses:</strong></p>
<ul>
<li><p>Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Gruppenanrufannahme verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Abhol Nummernbereiche an Sicherungspool umgeleitet werden</p></li>
</ul></td>
<td><p><strong>Während des Failback-Prozesses:</strong></p>
<ul>
<li><p>Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Die gruppenanrufannahme ist verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Pickup-Nummernbereichen zurück zum primären Pool umgeleitet werden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anrufe in der Warteschlange für die gruppenanrufannahme</p></td>
<td><p><strong>Während des Failover-Prozesses:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Keine Anrufe in diesem Zustand</p></li>
</ul></td>
<td><p><strong>Während des Failback-Prozesses:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Eingerichteter Anruf</p></td>
<td><p><strong>Während des Failover-Prozesses:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul></td>
<td><p><strong>Während des Failback-Prozesses:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul>
<p><strong>Nach Abschluss des Failback:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
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

