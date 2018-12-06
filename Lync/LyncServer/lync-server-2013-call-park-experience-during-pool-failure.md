---
title: 'Lync Server 2013: Abläufe für das Parken von Anrufen während des Ausfalls eines Pools'
TOCTitle: Abläufe für das Parken von Anrufen während des Ausfalls eines Pools
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205383(v=OCS.15)
ms:contentKeyID: 49295919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Abläufe für das Parken von Anrufen in Lync Server 2013 während des Ausfalls eines Pools

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Front-End-Pool wegen eines ungeplanten Zwischenfalls nicht mehr verfügbar ist, werden Anrufverbindungen, die geparkt, aber noch nicht wiederaufgenommen wurden, getrennt. Während des Failovers zu einem Sicherungspool werden die Benutzer in den Sicherungspool umgeleitet und in den Ausfallsicherheitsmodus geschaltet. Solange sie sich in diesem Modus befinden, können Benutzer keine Anrufe parken, aber Anrufe halten und weiterleiten. Nach Abschluss des Failovers können Anrufe wie gewohnt geparkt und wiederaufgenommen werden. Während des Failbacks können die Benutzer erst dann wieder Anrufe parken, wenn sie sich nicht mehr im Ausfallsicherheitsmodus befinden.

Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers in den Sicherungspool umgeleitet worden sind, die Anwendung zum Parken von Anrufen, die im Sicherungspool bereitgestellt ist. Daher verwenden die in den Sicherungspool umgeleiteten Benutzer die Einstellungen für das Parken von Anrufen, die für die Anwendung zum Parken von Anrufen im Sicherungspool konfiguriert sind.

In der folgenden Tabelle werden die Vorgänge beim Parken von Anrufen auf Benutzerseite während der einzelnen Phasen der Notfallwiederherstellung zusammengefasst.

### Vorgänge auf Benutzerseite während der Notfallwiederherstellung

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
<th>Bei Eintreten des Ausfalls</th>
<th>Während des Failovers</th>
<th>Während des Failbacks</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anruf noch nicht geparkt</p></td>
<td><p>Anrufverbindungen bleiben bestehen, Anrufe können aber nicht geparkt werden.</p></td>
<td><ul>
<li><p>Während des Failovers kann der Anruf nicht geparkt werden, solange der Benutzer im Ausfallsicherheitsmodus ist, aber gehalten und weitergeleitet werden.</p></li>
<li><p>Nach Abschluss des Failovers kann der Anruf geparkt und wiederaufgenommen werden.</p></li>
</ul></td>
<td><ul>
<li><p>Während des Failbacks kann der Anruf nicht geparkt werden, solange der Benutzer im Ausfallsicherheitsmodus ist, aber gehalten und weitergeleitet werden.</p></li>
<li><p>Nach Abschluss des Failbacks kann der Anruf geparkt und wiederaufgenommen werden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anruf geparkt, aber noch nicht wiederaufgenommen</p></td>
<td><p>Die Anrufverbindung wird getrennt.</p></td>
<td><p>Keine Anrufe in diesem Status.</p></td>
<td><p>Anruf bleibt geparkt.</p></td>
</tr>
<tr class="odd">
<td><p>Geparkter Anruf bereits wiederaufgenommen</p></td>
<td><p>Die Anrufverbindung bleibt bestehen.</p></td>
<td><p>Die Anrufverbindung bleibt bestehen.</p></td>
<td><p>Die Anrufverbindung bleibt bestehen.</p></td>
</tr>
</tbody>
</table>

