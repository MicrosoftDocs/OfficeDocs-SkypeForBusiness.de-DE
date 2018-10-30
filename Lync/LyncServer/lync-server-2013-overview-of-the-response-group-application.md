---
title: 'Lync Server 2013: Übersicht über die Reaktionsgruppenanwendung'
TOCTitle: Übersicht über die Reaktionsgruppenanwendung
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398513(v=OCS.15)
ms:contentKeyID: 49294323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Reaktionsgruppenanwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die Reaktionsgruppenanwendung verwendet standardmäßige Reaktionsgruppenroutingmethoden, um den Anruf an den nächsten verfügbaren Agent weiterzuleiten. Die Methoden zur Anrufweiterleitung umfassen serielles, Longest-Idle-, paralleles, Roundrobin- sowie das neue Routing über die Telefonzentrale (hier werden bei einem eingehenden Anruf alle Agents gleichzeitig angerufen) unabhängig von ihrem aktuellen Anwesenheitsstatus. Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Ist die Warteschleife belegt oder wenn für einen Anruf ein Timeout auftritt, während er sich in der Warteschleife befindet, kann für den Anrufer eine Nachricht wiedergegeben werden, und anschließend wird der Anrufer entweder getrennt oder an ein anderes Ziel übergeben. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.


> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von der lokalen Verwendung zur Onlinebereitstellung wechselt, werden die Anrufe der Reaktionsgruppe nicht mehr an diesen Agent weitergeleitet.




> [!NOTE]
> Die Reaktionsgruppenanwendung verwendet einen internen Dienst, den Matchmakingdienst, um Anrufe in der Warteschleife zu platzieren und verfügbare Agents zu ermitteln. Jeder Computer, auf dem die Reaktionsgruppenanwendung ausgeführt wird, führt den Matchmakingdienst aus. Pro Lync Server-Pool ist jedoch jeweils nur ein Matchmakingdienst aktiv, die anderen Dienste sind passiv. Wenn der aktive Matchmakingdienst aufgrund eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Matchmakingdienste aktiv. Die Reaktionsgruppenanwendung versucht, Unterbrechungen beim Anrufrouting und Queuing zu vermeiden. Beim Wechsel des aktiven Matchmakingdiensts gehen Anrufe, die zum Zeitpunkt des Wechsels übergeben werden, jedoch verloren. Wenn der Wechsel z.&nbsp;B. durch den Ausfall des Front-End-Servers bedingt wird, gehen zusätzlich alle vom aktiven Matchmakingdienst auf diesem Front-End-Server verarbeiteten Anrufe verloren.



Bei Lync Server 2013 sind zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen verfügbar: Reaktionsgruppenmanager und Reaktionsgruppenadministrator. Reaktionsgruppenadministratoren können sämtliche Aspekte jeder Reaktionsgruppe verwalten. Reaktionsgruppenmanager können nur bestimmte Aspekte verwalten und dies auch nur für die Reaktionsgruppen, deren Eigentümer sie sind. Dank der neuen Managerrolle können Verwaltungskosten verringert werden, da begrenzte Zuständigkeiten für bestimmte Reaktionsgruppen an beliebige Benutzer übertragen werden können, die für Enterprise-VoIP aktiviert sind.

Zur Berücksichtung der Rolle "Manager" wird in der Reaktionsgruppenanwendung in Lync Server 2013 ein **Workflowtyp** eingeführt, der entweder "Verwaltet" oder "Nicht verwaltet" sein kann. In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

### Verwaltete und nicht verwaltete Reaktionsgruppen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Reaktionsgruppentyp</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nicht verwaltet</p></td>
<td><ul>
<li><p>Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Nur der Reaktionsgruppenadministrator kann diese Reaktionsgruppen konfigurieren.</p></li>
<li><p>Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden.</p></li>
<li><p>Wenn Sie Reaktionsgruppen von einer früheren Version zu Lync Server 2013 migrieren, haben diese als Typ &quot;Nicht verwaltet&quot;.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Verwaltet</p></td>
<td><ul>
<li><p>Reaktionsgruppenadministratoren können sämtliche Aspekte verwalteter Reaktionsgruppen konfigurieren.</p></li>
<li><p>Reaktionsgruppenmanager können keine Reaktionsgruppen anzeigen oder ändern, die ihnen nicht explizit zugewiesen sind.</p></li>
<li><p>Reaktionsgruppenmanager können nur einige Einstellungen der Reaktionsgruppen konfigurieren, die ihnen explizit zugewiesen wurden.</p></li>
<li><p>Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppenmanager für die ihnen zugewiesenen Reaktionsgrupen durchführen können bzw. nicht durchführen können.

### Funktionen der Reaktionsgruppenmanager

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfiguration von:</th>
<th>Erstellen, Löschen, Konfigurieren von:</th>
<th>Nicht möglich:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agents</p></li>
<li><p>Willkommensnachrichten</p></li>
<li><p>Reaktionsgruppename</p></li>
<li><p>Beschreibung</p></li>
<li><p>Anzeigenummer</p></li>
<li><p>Geschäftszeiten</p></li>
<li><p>Wartemusik</p></li>
<li><p>Status (aktiv/inaktiv)</p></li>
<li><p>Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Agentgruppen</p></li>
<li><p>Warteschleifen</p></li>
<li><p>Feiertagssätze</p></li>
</ul></td>
<td><ul>
<li><p>Erstellen oder Löschen beliebiger Workflowtypen</p></li>
<li><p>Ändern grundlegender Reaktionsgruppeneinstellungen, wie: <strong>SIP-URI</strong> , <strong>Telefonnummer</strong> oder <strong>Workflowtyp</strong> .</p></li>
</ul></td>
</tr>
</tbody>
</table>


Reaktionsgruppenmanager können die folgenden Tools verwenden, um die ihnen zugewiesenen Reaktionsgruppen zu verwalten.

  - Lync Server-Systemsteuerung
    

    > [!NOTE]
    > Reaktionsgruppenmanager können nur Reaktionsgruppeneinstellungen mit diesem Tool verwalten. Andere Lync Server-Einstellungen sind für die Manager nicht verfügbar.



  - Konfigurationstool für Reaktionsgruppen

  - Lync Server-Verwaltungsshell

Reaktionsgruppen eignen sich für Abteilungs- und Arbeitsgruppenumgebungen (ausführliche Informationen finden Sie unter [Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) und können in völlig neuen Telefonieinstallationen bereitgestellt werden. Sie bieten Unterstützung für eingehende Anrufe aus der Enterprise-VoIP-Bereitstellung und aus dem örtlichen Telefonnetz. Agents können Anrufe, die an sie weitergeleitet werden, mit Lync 2013, Lync 2010, Lync 2010-Vermittlung oder Lync Phone Edition entgegennehmen.

Die Reaktionsgruppenanwendung ist eine Enterprise-VoIP-Komponente. Bei der Bereitstellung von Enterprise-VoIP wird die Reaktionsgruppenanwendung automatisch installiert und aktiviert.

