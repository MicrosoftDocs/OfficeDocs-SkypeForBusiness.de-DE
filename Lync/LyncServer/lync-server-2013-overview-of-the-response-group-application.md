---
title: 'Lync Server 2013: Übersicht über die Reaktionsgruppenanwendung'
description: 'Lync Server 2013: Übersicht über die Reaktionsgruppenanwendung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763a64adcf0eaf43e8f98a49cd850882ca9c91c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552381"
---
# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Übersicht über die Reaktionsgruppenanwendung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Der Reaktionsgruppenanwendung verwendet standardmäßige Reaktionsgruppen-Routingmethoden, um den Anruf an den nächsten verfügbaren Agent weiterzuleiten. Die Methoden zur Anrufweiterleitung umfassen serielles, Longest-Idle-, paralleles, Roundrobin- sowie das neue Routing über die Telefonzentrale (hier werden bei einem eingehenden Anruf alle Agents gleichzeitig angerufen) unabhängig von ihrem aktuellen Anwesenheitsstatus. Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Ist die Warteschleife belegt oder wenn für einen Anruf ein Timeout auftritt, während er sich in der Warteschleife befindet, kann für den Anrufer eine Nachricht wiedergegeben werden, und anschließend wird der Anrufer entweder getrennt oder an ein anderes Ziel übergeben. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

<div>


> [!NOTE]  
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.



</div>

<div>


> [!NOTE]  
> Der Reaktionsgruppenanwendung verwendet einen internen Dienst, der als Übereinstimmungs Erstellung bezeichnet wird, um Anrufe in die Warteschlange aufzunehmen und verfügbare Agents zu finden. Jeder Computer, auf dem der Reaktionsgruppenanwendung ausgeführt wird, führt den Übereinstimmungs Dienst aus, aber nur ein Übereinstimmungs Dienst pro lync Server Pool ist gleichzeitig aktiv – die anderen sind passiv. Wenn der aktive Übereinstimmungs Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Übereinstimmungs Dienste aktiviert. Die Reaktionsgruppenanwendung tut ihr Bestes, um sicherzustellen, dass das Anrufrouting und die Warteschlange unterbrechungsfrei fortgesetzt werden. Wenn jedoch ein überein Stimmungs Dienst Übergang erfolgt, gehen alle Anrufe, die zu diesem Zeitpunkt übertragen werden, verloren. Wenn beispielsweise der Übergang auf die Front-End-Server nach unten zurückzuführen ist, gehen alle Anrufe, die derzeit von dem aktiven Übereinstimmungs Dienst auf dieser Front-End-Server verarbeitet werden, ebenfalls verloren.



</div>

In lync Server 2013 stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Reaktionsgruppen-Manager und Reaktionsgruppen Administrator. Reaktionsgruppen Administratoren können alle Aspekte jeder Reaktionsgruppe verwalten. Manager für Reaktionsgruppen können nur bestimmte Aspekte verwalten und nur für die Reaktionsgruppen, die diese besitzen. Die neue Manager-Rolle kann dazu beitragen, die Verwaltungskosten zu reduzieren, da Sie eingeschränkte Zuständigkeiten für bestimmte Reaktionsgruppen an alle Benutzer delegieren können, die für Enterprise-VoIP aktiviert sind.

Um der neuen Manager Rolle gerecht zu werden, stellt lync Server 2013 Reaktionsgruppenanwendung einen **Workflowtyp** verwalteter oder nicht verwalteter Typen vor. In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

### <a name="managed-and-unmanaged-response-groups"></a>Verwaltete und nicht verwaltete Reaktionsgruppen

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
<td><p>Unverwalteten</p></td>
<td><ul>
<li><p>Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Nur der Reaktionsgruppen Administrator kann diese Reaktionsgruppen konfigurieren.</p></li>
<li><p>Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden.</p></li>
<li><p>Wenn Sie Reaktionsgruppen von einer früheren Version zu lync Server 2013 migrieren, wird der Typ auf "nicht verwaltet" festgelegt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Verwaltet</p></td>
<td><ul>
<li><p>Reaktionsgruppen Administratoren können alle Aspekte verwalteter Reaktionsgruppen konfigurieren.</p></li>
<li><p>Reaktionsgruppen-Manager können keine explizit zugewiesenen Reaktionsgruppen anzeigen oder ändern.</p></li>
<li><p>Manager für Reaktionsgruppen können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die Ihnen explizit zugewiesen sind.</p></li>
<li><p>Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppen-Manager für die Ihnen zugewiesenen Reaktionsgruppen ausführen können.

### <a name="response-group-manager-capabilities"></a>Funktionen der Reaktionsgruppenmanager

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
<th>Nicht</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agents</p></li>
<li><p>Willkommensnachrichten</p></li>
<li><p>Name der Reaktionsgruppe</p></li>
<li><p>Beschreibung</p></li>
<li><p>Anzeigenummer</p></li>
<li><p>Geschäftszeiten</p></li>
<li><p>Wartemusik</p></li>
<li><p>Status (aktiv/inaktiv)</p></li>
<li><p>Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Agentgruppen</p></li>
<li><p>Warteschlangen</p></li>
<li><p>Feiertagssätze</p></li>
</ul></td>
<td><ul>
<li><p>Erstellen oder Löschen beliebiger Workflowtypen</p></li>
<li><p>Ändern grundlegender Reaktionsgruppeneinstellungen, wie: <strong>SIP-URI</strong>, <strong>Telefonnummer</strong> oder <strong>Workflowtyp</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Manager für Reaktionsgruppen können die folgenden Tools verwenden, um Ihre benannten Reaktionsgruppen zu verwalten.

  - Lync Server-Systemsteuerung
    
    <div>
    

    > [!NOTE]  
    > Manager für Reaktionsgruppen können nur Reaktionsgruppeneinstellungen mit diesem Tool verwalten. Andere lync Server Einstellungen stehen Managern nicht zur Verfügung.

    
    </div>

  - Reaktionsgruppen-Konfigurations Tool

  - Lync Server-Verwaltungsshell

Die Reaktionsgruppe eignet sich gut für Abteilungen oder Arbeitsgruppenumgebungen (Ausführliche Informationen finden Sie unter [Kapazitätsplanung für Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) und kann in völlig neuen Telefonie-Installationen bereitgestellt werden. Er unterstützt eingehende Anrufe von der Enterprise-VoIP-Bereitstellung und aus dem lokalen Carrier-Netzwerk. Agents können lync 2013, lync 2010, lync 2010 Attendant oder lync Phone Edition verwenden, um die an Sie weitergeleiteten Anrufe zu übernehmen.

Die Reaktionsgruppenanwendung ist eine Komponente von Enterprise-VoIP. Wenn Sie Enterprise-VoIP bereitstellen, wird das Reaktionsgruppenanwendung automatisch installiert und aktiviert.

</div>

<span> </span>

</div>

</div>

</div>

