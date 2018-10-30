---
title: Verwalten der Gruppenanrufannahme während der Notfallwiederherstellung
TOCTitle: Verwalten der Gruppenanrufannahme während der Notfallwiederherstellung
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945618(v=OCS.15)
ms:contentKeyID: 52056312
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Gruppenanrufannahme während der Notfallwiederherstellung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Front-End-Pool während eines ungeplanten Vorfalls ausfällt, wird ein Failover des Diensts zum Sicherungspool ausgeführt. Während des Failovers zum Sicherungspool werden die Benutzer in den Sicherungspool umgeleitet und in den Ausfallsicherheitsmodus geschaltet. Im Ausfallsicherheitsmodus können Benutzer keine Anrufe an anderen Benutzer annehmen, und ihre eigenen Anrufe können nicht von anderen Benutzern angenommen werden. Nach Abschluss des Failovers können Benutzer die Gruppenanrufannahme wie gewohnt nutzen.

Während des Failbacks zum primären Pool werden die Benutzer in den primären Pool umgeleitet und dabei erneut in den Ausfallsicherheitsmodus geschaltet. Die Gruppenanrufannahme ist erst dann wieder verfügbar, wenn sich die Benutzer nicht mehr im Ausfallsicherheitsmodus befinden.

In diesem Abschnitt werden einige Überlegungen zur Gruppenanrufannahme während der Notfallwiederherstellung erörtert, und die Benutzererfahrung wird beschrieben.

## Überlegungen zur Gruppenanrufannahme während der Notfallwiederherstellung

Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failoververfahrens in den Sicherungspool umgeleitet wurden, die im Sicherungspool ausgeführte Anwendung zum Parken von Anrufen für die Nummern für Anrufannahmegruppe. Daher erfordert die Unterstützung der Gruppenanrufannahme während der Notfallwiederherstellung die Bereitstellung und Aktivierung der Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool.

Die Nummernbereiche für die Gruppenanrufannahme in der Orbittabelle für das Parken von Anrufen müssen in den Sicherungspool umgeleitet werden, nachdem das Failover zum Sicherungspool abgeschlossen ist. Wenn das Failback zum primären Pool abgeschlossen ist, müssen die Nummernbereiche wieder in den primären Pool umgeleitet werden. Zum Umleiten der Bereiche für die Gruppenanrufannahme verwenden Sie das Cmdlet **Set-CsCallParkOrbit**.

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, der den primären Pool ersetzt, müssen Sie alle Nummernbereiche für die Gruppenanrufannahme, die dem primären Pool zugeordnet waren, dem FQDN des neuen Pools zuweisen. Zum Zuweisen von Nummernbereichen an den neuen Pool können Sie das **Set-CsCallParkOrbit**-Cmdlet verwenden. Ausführliche Informationen zum **Set-CsCallParkOrbit**-Cmdlet finden Sie unter [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

## Die Benutzererfahrung der Gruppenanrufannahme während des Ausfalls eines Pools

In der folgenden Tabelle ist die Benutzererfahrung der Gruppenanrufannahme während der Phasen der Notfallwiederherstellung zusammengefasst.

### Vorgänge auf Benutzerseite während der Notfallwiederherstellung

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufstatus</th>
<th>Failover zu einem Sicherungspool</th>
<th>Failback zum primären Pool</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><p><strong>Während des Failoverprozesses:</strong></p>
<ul>
<li><p>Die Gruppenanrufannahme ist für Benutzer im Ausfallsicherheitsmodus nicht verfügbar.</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Die Gruppenanrufannahme ist verfügbar, wenn sich Benutzer nicht im Ausfallsicherheitsmodus befinden und die Nummernbereiche für die Gruppenanrufannahme in den Sicherungspool umgeleitet wurden.</p></li>
</ul></td>
<td><p><strong>Während des Failbackprozesses:</strong></p>
<ul>
<li><p>Die Gruppenanrufannahme ist für Benutzer im Ausfallsicherheitsmodus nicht verfügbar.</p></li>
</ul>
<p><strong>Nach Abschluss des Failbacks:</strong></p>
<ul>
<li><p>Die Gruppenanrufannahme ist verfügbar, wenn sich Benutzer nicht im Ausfallsicherheitsmodus befinden und die Nummernbereiche für die Gruppenanrufannahme zurück in den primären Pool geleitet wurden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anrufe in der Warteschlange der Gruppenanrufannahme</p></td>
<td><p><strong>Während des Failoverprozesses:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanrufannahme angenommen werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Keine Anrufe in diesem Status</p></li>
</ul></td>
<td><p><strong>Während des Failbackprozesses:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanrufannahme angenommen werden.</p></li>
</ul>
<p><strong>Nach Abschluss des Failbacks:</strong></p>
<ul>
<li><p>Anrufe in der Warteschlange können nicht über die Gruppenanrufannahme angenommen werden.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Aktuelle Anrufe</p></td>
<td><p><strong>Während des Failoverprozesses:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul>
<p><strong>Nach Abschluss des Failovers:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul></td>
<td><p><strong>Während des Failbackprozesses:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul>
<p><strong>Nach Abschluss des Failbacks:</strong></p>
<ul>
<li><p>Anrufe bleiben verbunden</p></li>
</ul></td>
</tr>
</tbody>
</table>

