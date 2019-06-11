---
title: 'Lync Server 2013: Abläufe für Reaktionsgruppen während des Ausfalls eines Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Abläufe für Reaktionsgruppen während des Ausfalls eines Pools in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In diesem Abschnitt wird ausführlich beschrieben, wie Reaktionsgruppen Aktivitäten in den folgenden Phasen betroffen sind:

  - Im primären Pool tritt ein Ausfall auf, aber noch kein Failover initiiert.

  - Der Dienst ist für den Sicherungspool nicht mehr möglich.

  - Der Dienst ist nicht mehr im primären Pool zurück.

<div>

## <a name="user-experience-when-outage-occurs"></a>Benutzererfahrung bei einem Ausfall

Wenn ein Pool-oder Website Ausfall auftritt, der Administrator aber noch kein Failover initiiert hat, wird die Aktivität der Reaktionsgruppe wie in der folgenden Tabelle beschrieben behandelt.

<div>


> [!NOTE]  
> Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden. In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.



</div>

### <a name="outage-occurs"></a>Ausfall eintritt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Art des Anrufs oder der Benutzeraktion</th>
<th>Bei einem Ausfall</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agenten verbunden sind</p></td>
<td><ul>
<li><p>Reguläre Anrufe bleiben verbunden.</p></li>
<li><p>Anonyme Anrufe werden getrennt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</p></td>
<td><p>Anrufe werden getrennt.</p></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><ul>
<li><p>Anrufe werden getrennt.</p></li>
<li><p>Wenn Reaktionsgruppen importiert wurden, werden die Verbindungen mit dem Sicherungspool verbunden, aber im primären Pool verwaltete Agents sind nicht erreichbar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Agenten Anrufe im Namen der Reaktionsgruppe</p></td>
<td><p>Das Feature ist in dieser Phase deaktiviert.</p></td>
</tr>
<tr class="odd">
<td><p>Informationen zu Anmelde-und Agent-Agents</p></td>
<td><ul>
<li><p>Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</p></li>
<li><p>Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Importierte Agentengruppen werden auf der Agentenkonsole nicht angezeigt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Reaktionsgruppen Konfiguration</p></td>
<td><ul>
<li><p>Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</p></li>
<li><p>Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während eines Failovers

Wenn ein Administrator ein Failover zu einem Sicherungspool aufruft, werden die Reaktionsgruppen Aktivitäten während und nach dem Failover verarbeitet, wie in der folgenden Tabelle beschrieben. Die erste Spalte beschreibt die Art der Aktivität, die möglicherweise stattfindet. In der mittleren Spalte wird beschrieben, wie die einzelnen Aktivitäten während der kurzen Zeit behandelt werden, die für ein Failover zum Sicherungspool erforderlich ist. In der letzten Spalte wird beschrieben, wie die Aktivität für die Dauer verarbeitet wird, nachdem der Failoverprozess abgeschlossen ist und der Sicherungspool für den primären Pool bereit steht.

<div>


> [!NOTE]  
> Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden. In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.



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
<th>Art des Anrufs oder der Benutzeraktion</th>
<th>Während des Failovers</th>
<th>Nach Abschluss des Failovers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agenten verbunden sind</p></td>
<td><ul>
<li><p>Reguläre Anrufe bleiben verbunden.</p></li>
<li><p>Anonyme Anrufe werden getrennt.</p></li>
</ul></td>
<td><ul>
<li><p>Reguläre Anrufe bleiben verbunden.</p></li>
<li><p>Bei importierten Antwortgruppen bleiben anonyme Anrufe, die den Sicherungspool erreicht haben, verbunden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</p></td>
<td><p>Anrufe werden getrennt.</p></td>
<td><ul>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</p></li>
<li><p>Bei importierten Antwortgruppen bleiben Anrufe, die den Sicherungspool erreicht haben, verbunden.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><ul>
<li><p>Anrufe werden getrennt.</p></li>
<li><p>Bei importierten Antwortgruppen wird die Verbindung mit dem Sicherungspool hergestellt, aber im primären Pool verwaltete Agents sind nicht erreichbar.</p></li>
</ul></td>
<td><ul>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, werden Anrufe getrennt.</p></li>
<li><p>Bei importierten Antwortgruppen werden Anrufe mit dem Sicherungspool verbunden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Agenten Anrufe im Namen der Reaktionsgruppe</p></td>
<td><p>Feature ist in dieser Phase deaktiviert</p></td>
<td><ul>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, schlagen Aufrufe fehl.</p></li>
<li><p>Bei importierten Antwortgruppen werden Aufrufe erfolgreich ausgeführt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Informationen zu Anmelde-und Agent-Agents</p></td>
<td><ul>
<li><p>Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</p></li>
<li><p>Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</p></li>
</ul></td>
<td><ul>
<li><p>Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</p></li>
<li><p>Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Reaktionsgruppen Konfiguration</p></td>
<td><ul>
<li><p>Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</p></li>
<li><p>Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Antwortgruppen, die dem primären Pool gehören, können abhängig von der Verfügbarkeit der Back-End-Datenbank angezeigt, aber nicht geändert werden.</p></li>
<li><p>Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Benutzerfreundlichkeit während des Failback

Wenn ein Administrator Failback für den primären Pool aufruft, werden die Reaktionsgruppen Aktivitäten während und nach dem Failback verarbeitet, wie in der folgenden Tabelle beschrieben.

<div>


> [!NOTE]  
> Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden. In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.



</div>

### <a name="call-handling-in-failback"></a>Anrufbehandlung in Failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Art des Anrufs oder der Benutzeraktion</th>
<th>Während des Failback</th>
<th>Nach Abschluss des Failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufe, die mit einem Agenten verbunden sind</p></td>
<td><ul>
<li><p>Reguläre Anrufe bleiben verbunden.</p></li>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine anonymen Anrufe.</p></li>
<li><p>Bei importierten Antwortgruppen bleiben anonyme Anrufe verbunden.</p></li>
</ul></td>
<td><ul>
<li><p>Reguläre Anrufe bleiben verbunden.</p></li>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine anonymen Anrufe.</p></li>
<li><p>Bei importierten Antwortgruppen bleiben anonyme Anrufe verbunden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</p></td>
<td><ul>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</p></li>
<li><p>Bei importierten Antwortgruppen werden Anrufe getrennt.</p></li>
</ul></td>
<td><ul>
<li><p>Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</p></li>
<li><p>Bei importierten Antwortgruppen werden Anrufe getrennt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Neue Anrufe</p></td>
<td><p>Anrufe stellen eine Verbindung mit dem primären Pool her, aber die im primären Pool verwalteten Agents sind nicht erreichbar.</p></td>
<td><p>Anrufe stellen eine Verbindung mit dem primären Pool her.</p></td>
</tr>
<tr class="even">
<td><p>Agenten Anrufe im Namen der Reaktionsgruppe</p></td>
<td><p>Das Feature ist in dieser Phase deaktiviert.</p></td>
<td><p>Anrufe erfolgreich.</p></td>
</tr>
<tr class="odd">
<td><p>Informationen zu Anmelde-und Agent-Agents</p></td>
<td><ul>
<li><p>Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</p></li>
<li><p>Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</p></li>
</ul></td>
<td><ul>
<li><p>Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</p></li>
<li><p>Importierte Agentengruppen werden auf der Agentenkonsole nicht angezeigt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Reaktionsgruppen Konfiguration</p></td>
<td><ul>
<li><p>Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</p></li>
<li><p>Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
</ul></td>
<td><ul>
<li><p>Antwortgruppen, die im Besitz des primären Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</p></li>
<li><p>Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</p></li>
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

