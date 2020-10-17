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
# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="1f28b-103">Übersicht über die Reaktionsgruppenanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f28b-103">Overview of the Response Group application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f28b-104">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1f28b-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1f28b-105">Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1f28b-105">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="1f28b-106">Der Reaktionsgruppenanwendung verwendet standardmäßige Reaktionsgruppen-Routingmethoden, um den Anruf an den nächsten verfügbaren Agent weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1f28b-106">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="1f28b-107">Die Methoden zur Anrufweiterleitung umfassen serielles, Longest-Idle-, paralleles, Roundrobin- sowie das neue Routing über die Telefonzentrale (hier werden bei einem eingehenden Anruf alle Agents gleichzeitig angerufen) unabhängig von ihrem aktuellen Anwesenheitsstatus.</span><span class="sxs-lookup"><span data-stu-id="1f28b-107">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="1f28b-108">Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1f28b-108">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="1f28b-109">Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="1f28b-109">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="1f28b-110">Ist die Warteschleife belegt oder wenn für einen Anruf ein Timeout auftritt, während er sich in der Warteschleife befindet, kann für den Anrufer eine Nachricht wiedergegeben werden, und anschließend wird der Anrufer entweder getrennt oder an ein anderes Ziel übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f28b-110">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="1f28b-111">Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-111">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="1f28b-112">Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="1f28b-112">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f28b-p102">Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1f28b-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1f28b-115">Der Reaktionsgruppenanwendung verwendet einen internen Dienst, der als Übereinstimmungs Erstellung bezeichnet wird, um Anrufe in die Warteschlange aufzunehmen und verfügbare Agents zu finden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-115">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="1f28b-116">Jeder Computer, auf dem der Reaktionsgruppenanwendung ausgeführt wird, führt den Übereinstimmungs Dienst aus, aber nur ein Übereinstimmungs Dienst pro lync Server Pool ist gleichzeitig aktiv – die anderen sind passiv.</span><span class="sxs-lookup"><span data-stu-id="1f28b-116">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="1f28b-117">Wenn der aktive Übereinstimmungs Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Übereinstimmungs Dienste aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f28b-117">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="1f28b-118">Die Reaktionsgruppenanwendung tut ihr Bestes, um sicherzustellen, dass das Anrufrouting und die Warteschlange unterbrechungsfrei fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-118">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="1f28b-119">Wenn jedoch ein überein Stimmungs Dienst Übergang erfolgt, gehen alle Anrufe, die zu diesem Zeitpunkt übertragen werden, verloren.</span><span class="sxs-lookup"><span data-stu-id="1f28b-119">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="1f28b-120">Wenn beispielsweise der Übergang auf die Front-End-Server nach unten zurückzuführen ist, gehen alle Anrufe, die derzeit von dem aktiven Übereinstimmungs Dienst auf dieser Front-End-Server verarbeitet werden, ebenfalls verloren.</span><span class="sxs-lookup"><span data-stu-id="1f28b-120">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="1f28b-121">In lync Server 2013 stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Reaktionsgruppen-Manager und Reaktionsgruppen Administrator.</span><span class="sxs-lookup"><span data-stu-id="1f28b-121">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="1f28b-122">Reaktionsgruppen Administratoren können alle Aspekte jeder Reaktionsgruppe verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f28b-122">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="1f28b-123">Manager für Reaktionsgruppen können nur bestimmte Aspekte verwalten und nur für die Reaktionsgruppen, die diese besitzen.</span><span class="sxs-lookup"><span data-stu-id="1f28b-123">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="1f28b-124">Die neue Manager-Rolle kann dazu beitragen, die Verwaltungskosten zu reduzieren, da Sie eingeschränkte Zuständigkeiten für bestimmte Reaktionsgruppen an alle Benutzer delegieren können, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1f28b-124">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="1f28b-125">Um der neuen Manager Rolle gerecht zu werden, stellt lync Server 2013 Reaktionsgruppenanwendung einen **Workflowtyp** verwalteter oder nicht verwalteter Typen vor.</span><span class="sxs-lookup"><span data-stu-id="1f28b-125">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="1f28b-126">In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f28b-126">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="1f28b-127">Verwaltete und nicht verwaltete Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="1f28b-127">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f28b-128">Reaktionsgruppentyp</span><span class="sxs-lookup"><span data-stu-id="1f28b-128">Response group type</span></span></th>
<th><span data-ttu-id="1f28b-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f28b-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f28b-130">Unverwalteten</span><span class="sxs-lookup"><span data-stu-id="1f28b-130">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1f28b-131">Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1f28b-131">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="1f28b-132">Nur der Reaktionsgruppen Administrator kann diese Reaktionsgruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f28b-132">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="1f28b-133">Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-133">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="1f28b-134">Wenn Sie Reaktionsgruppen von einer früheren Version zu lync Server 2013 migrieren, wird der Typ auf "nicht verwaltet" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f28b-134">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f28b-135">Verwaltet</span><span class="sxs-lookup"><span data-stu-id="1f28b-135">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1f28b-136">Reaktionsgruppen Administratoren können alle Aspekte verwalteter Reaktionsgruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f28b-136">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="1f28b-137">Reaktionsgruppen-Manager können keine explizit zugewiesenen Reaktionsgruppen anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="1f28b-137">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="1f28b-138">Manager für Reaktionsgruppen können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die Ihnen explizit zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1f28b-138">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="1f28b-139">Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-139">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f28b-140">In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppen-Manager für die Ihnen zugewiesenen Reaktionsgruppen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1f28b-140">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="1f28b-141">Funktionen der Reaktionsgruppenmanager</span><span class="sxs-lookup"><span data-stu-id="1f28b-141">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f28b-142">Konfiguration von:</span><span class="sxs-lookup"><span data-stu-id="1f28b-142">Can configure:</span></span></th>
<th><span data-ttu-id="1f28b-143">Erstellen, Löschen, Konfigurieren von:</span><span class="sxs-lookup"><span data-stu-id="1f28b-143">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="1f28b-144">Nicht</span><span class="sxs-lookup"><span data-stu-id="1f28b-144">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="1f28b-145">Agents</span><span class="sxs-lookup"><span data-stu-id="1f28b-145">Agents</span></span></p></li>
<li><p><span data-ttu-id="1f28b-146">Willkommensnachrichten</span><span class="sxs-lookup"><span data-stu-id="1f28b-146">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="1f28b-147">Name der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1f28b-147">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="1f28b-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f28b-148">Description</span></span></p></li>
<li><p><span data-ttu-id="1f28b-149">Anzeigenummer</span><span class="sxs-lookup"><span data-stu-id="1f28b-149">Display number</span></span></p></li>
<li><p><span data-ttu-id="1f28b-150">Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="1f28b-150">Business hours</span></span></p></li>
<li><p><span data-ttu-id="1f28b-151">Wartemusik</span><span class="sxs-lookup"><span data-stu-id="1f28b-151">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="1f28b-152">Status (aktiv/inaktiv)</span><span class="sxs-lookup"><span data-stu-id="1f28b-152">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="1f28b-153">Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR)</span><span class="sxs-lookup"><span data-stu-id="1f28b-153">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1f28b-154">Agentgruppen</span><span class="sxs-lookup"><span data-stu-id="1f28b-154">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="1f28b-155">Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="1f28b-155">Queues</span></span></p></li>
<li><p><span data-ttu-id="1f28b-156">Feiertagssätze</span><span class="sxs-lookup"><span data-stu-id="1f28b-156">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1f28b-157">Erstellen oder Löschen beliebiger Workflowtypen</span><span class="sxs-lookup"><span data-stu-id="1f28b-157">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="1f28b-158">Ändern grundlegender Reaktionsgruppeneinstellungen, wie: <strong>SIP-URI</strong>, <strong>Telefonnummer</strong> oder <strong>Workflowtyp</strong>.</span><span class="sxs-lookup"><span data-stu-id="1f28b-158">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f28b-159">Manager für Reaktionsgruppen können die folgenden Tools verwenden, um Ihre benannten Reaktionsgruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f28b-159">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="1f28b-160">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="1f28b-160">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f28b-161">Manager für Reaktionsgruppen können nur Reaktionsgruppeneinstellungen mit diesem Tool verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f28b-161">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="1f28b-162">Andere lync Server Einstellungen stehen Managern nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1f28b-162">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="1f28b-163">Reaktionsgruppen-Konfigurations Tool</span><span class="sxs-lookup"><span data-stu-id="1f28b-163">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="1f28b-164">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="1f28b-164">Lync Server Management Shell</span></span>

<span data-ttu-id="1f28b-165">Die Reaktionsgruppe eignet sich gut für Abteilungen oder Arbeitsgruppenumgebungen (Ausführliche Informationen finden Sie unter [Kapazitätsplanung für Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) und kann in völlig neuen Telefonie-Installationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1f28b-165">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="1f28b-166">Er unterstützt eingehende Anrufe von der Enterprise-VoIP-Bereitstellung und aus dem lokalen Carrier-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="1f28b-166">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="1f28b-167">Agents können lync 2013, lync 2010, lync 2010 Attendant oder lync Phone Edition verwenden, um die an Sie weitergeleiteten Anrufe zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="1f28b-167">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="1f28b-168">Die Reaktionsgruppenanwendung ist eine Komponente von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="1f28b-168">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="1f28b-169">Wenn Sie Enterprise-VoIP bereitstellen, wird das Reaktionsgruppenanwendung automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f28b-169">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

