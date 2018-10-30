---
title: 'Lync Server 2013: Abläufe für Reaktionsgruppen während des Ausfalls eines Pools'
TOCTitle: Abläufe für Reaktionsgruppen während des Ausfalls eines Pools
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204886(v=OCS.15)
ms:contentKeyID: 49293955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Abläufe für Reaktionsgruppen während des Ausfalls eines Pools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt wird detailliert beschrieben, wie sich die Aktivitäten von Reaktionsgruppen in den folgenden Phasen auswirken:

  - Es kommt zu einem Ausfall im primären Pool. Ein Failover wurde jedoch noch nicht initiiert.

  - Der Dienst wird in den Sicherungspool verschoben.

  - Der Dienst wird wieder in den primären Pool verschoben.

## Benutzererfahrung beim Ausfall

Wenn ein Pool oder ein Standort ausfallen, jedoch noch kein Failover vom Administrator initiiert wurde, werden die Aktivitäten von Reaktionsgruppen wie in der folgenden Tabelle beschrieben verarbeitet.


> [!NOTE]
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.



### Auftreten eines Ausfalls

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
<td><p>Agent-Anrufe für Reaktionsgruppen.</p></td>
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
<li><p>Importierte Reaktionsgruppen können nicht mit Lync Server-Systemsteuerung oder Konfigurationstool für Reaktionsgruppen angezeigt werden. Sie können jedoch mit den Cmdlets von Lync Server-Verwaltungsshell konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Benutzerfreundlichkeit während des Failovers

Wenn ein Administrator ein Failover zu einem Sicherungspool auslöst, werden die Aktivitäten von Reaktionsgruppen während des Failovers sowie im Anschluss daran gemäß den Angaben in der nachstehenden Tabelle verarbeitet. Die erste Spalte gibt an, welche Art von Aktivität stattfinden kann. Die mittlere Spalte gibt an, wie die einzelnen Aktivitäten während des kurzen Vorgangs zum Verschieben in den Sicherungspool verarbeitet werden. Die rechte Spalte gibt schließlich an, wie die Aktivität während des Failover-Vorgangs sowie im Anschluss daran und während der Nutzung des Sicherungspools anstelle des primären Pools verarbeitet wird.


> [!NOTE]
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.



### Failover wird initiiert

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
<td><p>Agent-Anrufe für Reaktionsgruppen.</p></td>
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
<li><p>Importierte Reaktionsgruppen können nicht mit Lync Server-Systemsteuerung oder Konfigurationstool für Reaktionsgruppen angezeigt werden. Sie können jedoch mit den Cmdlets von Lync Server-Verwaltungsshell konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit Lync Server-Systemsteuerung oder Konfigurationstool für Reaktionsgruppen angezeigt werden. Sie können jedoch mit den Cmdlets von Lync Server-Verwaltungsshell konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Benutzerfreundlichkeit während des Failbacks

Wenn ein Administrator das Failback zum primären Pool initiiert, werden die Aktivitäten von Reaktionsgruppen während des Failbacks sowie im Anschluss daran wie in der folgenden Tabelle verarbeitet.


> [!NOTE]
> Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.



### Behandlung von Anrufen bei Failbacks

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
<li><p>Importierte Reaktionsgruppen können nicht mit Lync Server-Systemsteuerung oder Konfigurationstool für Reaktionsgruppen angezeigt werden. Sie können jedoch mit den Cmdlets von Lync Server-Verwaltungsshell konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</p></li>
<li><p>Importierte Reaktionsgruppen können nicht mit Lync Server-Systemsteuerung oder Konfigurationstool für Reaktionsgruppen angezeigt werden. Sie können jedoch mit den Cmdlets von Lync Server-Verwaltungsshell konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>

