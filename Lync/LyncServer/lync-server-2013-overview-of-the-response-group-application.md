---
title: 'Lync Server 2013: Übersicht über die reaktionsgruppenanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Übersicht über die reaktionsgruppenanwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die reaktionsgruppenanwendung verwendet standardmäßige Reaktionsgruppen-Routingmethoden, um den Anruf an den nächsten verfügbaren Agenten weiterzuleiten. Zu den Anruf Weiterleitungs Methoden gehören Serial-, Long-Idle-, parallel-, Round Robin-und Attendant-Routing (das heißt, alle Agents werden zur gleichen Zeit für jeden eingehenden Anruf aufgerufen, unabhängig von deren derzeitigem vorhanden sein). Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Wenn es sich um eine vollständige Warteschlange handelt oder wenn der Anruf in der Warteschlange abläuft, hört der Anrufer möglicherweise eine Nachricht und wird dann entweder getrennt oder an ein anderes Ziel übertragen. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

<div>


> [!NOTE]  
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von lokal in Online verschoben wird, werden keine Antwortgruppen Aufrufe an diesen Agenten weitergeleitet.



</div>

<div>


> [!NOTE]  
> Die Antwortgruppen Anwendung verwendet einen internen Dienst, der als Übereinstimmungs Erstellung bezeichnet wird, um Anrufe in die Warteschlange zu stellen und verfügbare Agents zu finden. Jeder Computer, auf dem die reaktionsgruppenanwendung ausgeführt wird, führt den Übereinstimmungs Dienst aus, aber es ist jeweils nur ein Übereinstimmungs Dienst pro lync-Server Pool aktiv – die anderen sind passiv. Wenn der aktive Übereinstimmungs Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Übereinstimmungs Dienste aktiviert. Die Response Group-Anwendung tut ihr Bestes, um sicherzustellen, dass Anrufweiterleitung und-Warteschlangen unterbrechungsfrei fortgesetzt werden. Wenn jedoch eine Übereinstimmung zum Dienst Übergang eintritt, gehen alle Anrufe, die zu diesem Zeitpunkt übertragen werden, verloren. Wenn der Übergang beispielsweise auf den Ausfall des Front-End-Servers zurückzuführen ist, gehen alle Anrufe, die derzeit vom aktiven Übereinstimmungs Dienst auf dem Front-End-Server abgewickelt werden, ebenfalls verloren.



</div>

In lync Server 2013 stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Antwortgruppen-Manager und Antwortgruppen Administrator. Reaktionsgruppen Administratoren können alle Aspekte jeder Reaktionsgruppe verwalten. Antwortgruppen-Manager können nur bestimmte Aspekte verwalten, und zwar nur für die Antwortgruppen, die Sie besitzen. Die neue Manager-Rolle kann dazu beitragen, die Verwaltungskosten zu senken, da Sie für bestimmte Antwortgruppen begrenzte Zuständigkeiten an alle Benutzer delegieren können, die für Enterprise-VoIP aktiviert sind.

Um der neuen Manager-Rolle gerecht zu werden, führt die lync Server 2013 Response Group-Anwendung einen Workflowtyp verwalteter oder nicht verwalteter **Ressourcen** ein. In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

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
<td><p>Nicht verwaltet</p></td>
<td><ul>
<li><p>Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Diese Reaktionsgruppen können nur vom Administrator der Reaktionsgruppe konfiguriert werden.</p></li>
<li><p>Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden.</p></li>
<li><p>Wenn Sie Antwortgruppen von einer früheren Version zu lync Server 2013 migrieren, wird der Typ auf "nicht verwaltet" gesetzt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Verwaltet</p></td>
<td><ul>
<li><p>Reaktionsgruppen Administratoren können alle Aspekte von verwalteten Reaktionsgruppen konfigurieren.</p></li>
<li><p>Reaktionsgruppen-Manager können keine Antwortgruppen anzeigen oder ändern, die Ihnen nicht explizit zugewiesen sind.</p></li>
<li><p>Reaktionsgruppen-Manager können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die Ihnen explizit zugewiesen sind.</p></li>
<li><p>Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden.</p></li>
</ul></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Aktionen beschrieben, die von Reaktionsgruppen-Managern für die Ihnen zugewiesenen Antwortgruppen ausgeführt werden können.

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
<th>Nicht möglich:</th>
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
<li><p>Warteschleifen</p></li>
<li><p>Feiertagssätze</p></li>
</ul></td>
<td><ul>
<li><p>Erstellen oder Löschen beliebiger Workflowtypen</p></li>
<li><p>Ändern grundlegender Reaktionsgruppeneinstellungen wie <strong>SIP-URI</strong>, <strong>Telefonnummer</strong> oder <strong>Workflowtyp</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Antwortgruppen-Manager können die folgenden Tools verwenden, um Ihre vorgesehenen Antwortgruppen zu verwalten.

  - Lync Server-Systemsteuerung
    
    <div>
    

    > [!NOTE]  
    > Antwortgruppen-Manager können mit diesem Tool nur Einstellungen für die Reaktionsgruppe verwalten. Andere lync-Server Einstellungen stehen Managern nicht zur Verfügung.

    
    </div>

  - Konfigurationstool für Reaktionsgruppen

  - Lync Server-Verwaltungsshell

Die Reaktionsgruppe eignet sich gut für Abteilungs-oder Arbeitsgruppenumgebungen (Details finden Sie unter [Kapazitätsplanung für die Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) und kann in völlig neuen Telefonieanlagen bereitgestellt werden. Sie unterstützt eingehende Anrufe von der Enterprise-VoIP-Bereitstellung und vom lokalen Netzbetreiber Netzwerk. Agents können lync 2013, lync 2010, lync 2010 Attendant oder lync Phone Edition verwenden, um die an Sie weitergeleiteten Anrufe zu übernehmen.

Die Response Group-Anwendung ist eine Komponente von Enterprise-VoIP. Wenn Sie Enterprise-VoIP bereitstellen, wird die reaktionsgruppenanwendung automatisch installiert und aktiviert.

</div>

<span> </span>

</div>

</div>

</div>

