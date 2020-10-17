---
title: Lync Server 2013 Reaktionsgruppen Erfahrung beim Pool Ausfall
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684d33219bb6146a0c5dc85894c060affd6745a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511642"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Reaktionsgruppen Erfahrung in lync Server 2013 während eines Pool Fehlers

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

In diesem Abschnitt wird detailliert beschrieben, wie sich die Aktivitäten von Reaktionsgruppen in den folgenden Phasen auswirken:

  - Es kommt zu einem Ausfall im primären Pool. Ein Failover wurde jedoch noch nicht initiiert.

  - Der Dienst wird in den Sicherungspool verschoben.

  - Der Dienst wird wieder in den primären Pool verschoben.

<div>

## <a name="user-experience-when-outage-occurs"></a>Benutzererfahrung beim Ausfall

Wenn ein Pool oder ein Standort ausfallen, jedoch noch kein Failover vom Administrator initiiert wurde, werden die Aktivitäten von Reaktionsgruppen wie in der folgenden Tabelle beschrieben verarbeitet.

<div>


> [!NOTE]  
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden. Verweise auf importierte Reaktionsgruppen in der folgenden Tabelle geben an, dass die Reaktionsgruppen des primären Pools während der Notfallwiederherstellung in den Sicherungspool importiert wurden.



</div>

### <a name="outage-occurs"></a>Auftreten eines Ausfalls

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Art der Anruf- oder Benutzeraktion</th>
<th>Während des Ausfalls</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agent verbunden sind</p></td>
<td><ul>
<li><p>Bei regulären Anrufen bleibt die Verbindung erhalten.</p></li>
<li><p>Anonyme Anrufe werden getrennt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</p></td>
<td><p>Die Anrufe werden getrennt.</p></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><ul>
<li><p>Die Anrufe werden getrennt.</p></li>
<li><p>Wenn Reaktionsgruppen importiert wurden, werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Agent-Anrufe für Reaktionsgruppen</p></td>
<td><p>Diese Funktion ist in der aktuellen Phase deaktiviert.</p></td>
</tr>
<tr class="odd">
<td><p>Agent-Anmeldungen und Agent-Informationen</p></td>
<td><ul>
<li><p>Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</p></li>
<li><p>Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Konfiguration von Reaktionsgruppen</p></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Benutzererfahrung beim Failover

Wenn ein Administrator ein Failover zu einem Sicherungspool auslöst, werden die Aktivitäten von Reaktionsgruppen während des Failovers sowie im Anschluss daran gemäß den Angaben in der nachstehenden Tabelle verarbeitet. Die erste Spalte gibt an, welche Art von Aktivität stattfinden kann. Die mittlere Spalte gibt an, wie die einzelnen Aktivitäten während des kurzen Vorgangs zum Verschieben in den Sicherungspool verarbeitet werden. Die rechte Spalte gibt schließlich an, wie die Aktivität während des Failover-Vorgangs sowie im Anschluss daran und während der Nutzung des Sicherungspools anstelle des primären Pools verarbeitet wird.

<div>


> [!NOTE]  
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.



</div>

### <a name="failover-is-initiated"></a>Failover wird initiiert

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Art der Anruf- oder Benutzeraktion</th>
<th>Während des Failovers</th>
<th>Nach Abschluss des Failovers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agent verbunden sind</p></td>
<td><ul>
<li><p>Bei regulären Anrufen bleibt die Verbindung erhalten.</p></li>
<li><p>Anonyme Anrufe werden getrennt.</p></li>
</ul></td>
<td><ul>
<li><p>Bei regulären Anrufen bleibt die Verbindung erhalten.</p></li>
<li><p>Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten, die den Sicherungspool erreicht haben.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</p></td>
<td><p>Die Anrufe werden getrennt.</p></td>
<td><ul>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</p></li>
<li><p>Bei importierten Reaktionsgruppen wird die Verbindung von Anrufen erhalten, die den Sicherungspool erreicht haben.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><ul>
<li><p>Die Anrufe werden getrennt.</p></li>
<li><p>Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</p></li>
</ul></td>
<td><ul>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, werden die Anrufe getrennt.</p></li>
<li><p>Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Agent-Anrufe für Reaktionsgruppen</p></td>
<td><p>Diese Funktion ist in der aktuellen Phase deaktiviert.</p></td>
<td><ul>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, tritt bei Anrufen ein Fehler auf.</p></li>
<li><p>Bei importierten Reaktionsgruppen können die Anrufe erfolgreich getätigt werden.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Agent-Anmeldungen und Agent-Informationen</p></td>
<td><ul>
<li><p>Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</p></li>
<li><p>Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</p></li>
</ul></td>
<td><ul>
<li><p>Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</p></li>
<li><p>Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Konfiguration von Reaktionsgruppen</p></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Benutzererfahrung beim Failback

Wenn ein Administrator das Failback zum primären Pool initiiert, werden die Aktivitäten von Reaktionsgruppen während des Failbacks sowie im Anschluss daran wie in der folgenden Tabelle verarbeitet.

<div>


> [!NOTE]  
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.



</div>

### <a name="call-handling-in-failback"></a>Behandlung von Anrufen bei Failbacks

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Art der Anruf- oder Benutzeraktion</th>
<th>Während des Failbacks</th>
<th>Nach Abschluss des Failbacks</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agent verbunden sind</p></td>
<td><ul>
<li><p>Bei regulären Anrufen bleibt die Verbindung erhalten.</p></li>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</p></li>
<li><p>Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</p></li>
</ul></td>
<td><ul>
<li><p>Bei regulären Anrufen bleibt die Verbindung erhalten.</p></li>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</p></li>
<li><p>Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</p></td>
<td><ul>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</p></li>
<li><p>Die Anrufe von importierten Reaktionsgruppen werden getrennt.</p></li>
</ul></td>
<td><ul>
<li><p>Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</p></li>
<li><p>Die Anrufe von importierten Reaktionsgruppen werden getrennt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><p>Anrufe werden mit dem primären Pool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</p></td>
<td><p>Anrufe werden mit dem primären Pool verbunden.</p></td>
</tr>
<tr class="even">
<td><p>Agent-Anrufe für Reaktionsgruppen.</p></td>
<td><p>Diese Funktion ist in der aktuellen Phase deaktiviert.</p></td>
<td><p>Die Anrufe können getätigt werden.</p></td>
</tr>
<tr class="odd">
<td><p>Agent-Anmeldungen und Agent-Informationen</p></td>
<td><ul>
<li><p>Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</p></li>
<li><p>Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</p></li>
</ul></td>
<td><ul>
<li><p>Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</p></li>
<li><p>Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Konfiguration von Reaktionsgruppen</p></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
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

