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

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="1ee40-102">Abläufe für Reaktionsgruppen während des Ausfalls eines Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee40-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee40-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="1ee40-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="1ee40-104">In diesem Abschnitt wird ausführlich beschrieben, wie Reaktionsgruppen Aktivitäten in den folgenden Phasen betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="1ee40-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="1ee40-105">Im primären Pool tritt ein Ausfall auf, aber noch kein Failover initiiert.</span><span class="sxs-lookup"><span data-stu-id="1ee40-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="1ee40-106">Der Dienst ist für den Sicherungspool nicht mehr möglich.</span><span class="sxs-lookup"><span data-stu-id="1ee40-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="1ee40-107">Der Dienst ist nicht mehr im primären Pool zurück.</span><span class="sxs-lookup"><span data-stu-id="1ee40-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="1ee40-108">Benutzererfahrung bei einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="1ee40-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="1ee40-109">Wenn ein Pool-oder Website Ausfall auftritt, der Administrator aber noch kein Failover initiiert hat, wird die Aktivität der Reaktionsgruppe wie in der folgenden Tabelle beschrieben behandelt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ee40-110">Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="1ee40-111">In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="1ee40-112">Ausfall eintritt</span><span class="sxs-lookup"><span data-stu-id="1ee40-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee40-113">Art des Anrufs oder der Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1ee40-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="1ee40-114">Bei einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="1ee40-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-115">Anrufe, die mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-116">Reguläre Anrufe bleiben verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-117">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-118">In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="1ee40-119">Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-120">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="1ee40-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-121">Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-122">Wenn Reaktionsgruppen importiert wurden, werden die Verbindungen mit dem Sicherungspool verbunden, aber im primären Pool verwaltete Agents sind nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="1ee40-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-123">Agenten Anrufe im Namen der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1ee40-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1ee40-124">Das Feature ist in dieser Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ee40-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-125">Informationen zu Anmelde-und Agent-Agents</span><span class="sxs-lookup"><span data-stu-id="1ee40-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-126">Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-127">Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-128">Importierte Agentengruppen werden auf der Agentenkonsole nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-129">Reaktionsgruppen Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1ee40-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-130">Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-131">Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-132">Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="1ee40-133">Benutzerfreundlichkeit während eines Failovers</span><span class="sxs-lookup"><span data-stu-id="1ee40-133">User Experience During Failover</span></span>

<span data-ttu-id="1ee40-134">Wenn ein Administrator ein Failover zu einem Sicherungspool aufruft, werden die Reaktionsgruppen Aktivitäten während und nach dem Failover verarbeitet, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ee40-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="1ee40-135">Die erste Spalte beschreibt die Art der Aktivität, die möglicherweise stattfindet.</span><span class="sxs-lookup"><span data-stu-id="1ee40-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="1ee40-136">In der mittleren Spalte wird beschrieben, wie die einzelnen Aktivitäten während der kurzen Zeit behandelt werden, die für ein Failover zum Sicherungspool erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1ee40-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="1ee40-137">In der letzten Spalte wird beschrieben, wie die Aktivität für die Dauer verarbeitet wird, nachdem der Failoverprozess abgeschlossen ist und der Sicherungspool für den primären Pool bereit steht.</span><span class="sxs-lookup"><span data-stu-id="1ee40-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ee40-138">Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="1ee40-139">In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="1ee40-140">Failover wird initiiert</span><span class="sxs-lookup"><span data-stu-id="1ee40-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee40-141">Art des Anrufs oder der Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1ee40-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="1ee40-142">Während des Failovers</span><span class="sxs-lookup"><span data-stu-id="1ee40-142">During Failover</span></span></th>
<th><span data-ttu-id="1ee40-143">Nach Abschluss des Failovers</span><span class="sxs-lookup"><span data-stu-id="1ee40-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-144">Anrufe, die mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-145">Reguläre Anrufe bleiben verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-146">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-147">Reguläre Anrufe bleiben verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-148">Bei importierten Antwortgruppen bleiben anonyme Anrufe, die den Sicherungspool erreicht haben, verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-149">In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="1ee40-150">Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-151">Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1ee40-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-152">Bei importierten Antwortgruppen bleiben Anrufe, die den Sicherungspool erreicht haben, verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-153">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="1ee40-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-154">Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-155">Bei importierten Antwortgruppen wird die Verbindung mit dem Sicherungspool hergestellt, aber im primären Pool verwaltete Agents sind nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="1ee40-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-156">Wenn Reaktionsgruppen nicht importiert wurden, werden Anrufe getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-157">Bei importierten Antwortgruppen werden Anrufe mit dem Sicherungspool verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-158">Agenten Anrufe im Namen der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1ee40-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1ee40-159">Feature ist in dieser Phase deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1ee40-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-160">Wenn Reaktionsgruppen nicht importiert wurden, schlagen Aufrufe fehl.</span><span class="sxs-lookup"><span data-stu-id="1ee40-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-161">Bei importierten Antwortgruppen werden Aufrufe erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-162">Informationen zu Anmelde-und Agent-Agents</span><span class="sxs-lookup"><span data-stu-id="1ee40-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-163">Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-164">Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-165">Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-166">Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-167">Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-168">Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-169">Reaktionsgruppen Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1ee40-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-170">Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-171">Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-172">Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-173">Antwortgruppen, die dem primären Pool gehören, können abhängig von der Verfügbarkeit der Back-End-Datenbank angezeigt, aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-174">Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-175">Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="1ee40-176">Benutzerfreundlichkeit während des Failback</span><span class="sxs-lookup"><span data-stu-id="1ee40-176">User Experience During Failback</span></span>

<span data-ttu-id="1ee40-177">Wenn ein Administrator Failback für den primären Pool aufruft, werden die Reaktionsgruppen Aktivitäten während und nach dem Failback verarbeitet, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ee40-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ee40-178">Während der Disaster Recovery Verhalten sich Anrufe anders, je nachdem, ob die primären Pool Antwortgruppen während der Wiederherstellung in den Backup-Pool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="1ee40-179">In der folgenden Tabelle sind Verweise auf importierte Antwortgruppen darauf hinweisen, dass primäre Pool Antwortgruppen während des Disaster Recovery-Modus in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="1ee40-180">Anrufbehandlung in Failback</span><span class="sxs-lookup"><span data-stu-id="1ee40-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee40-181">Art des Anrufs oder der Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1ee40-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="1ee40-182">Während des Failback</span><span class="sxs-lookup"><span data-stu-id="1ee40-182">During Failback</span></span></th>
<th><span data-ttu-id="1ee40-183">Nach Abschluss des Failback</span><span class="sxs-lookup"><span data-stu-id="1ee40-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-184">Anrufe, die mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-185">Reguläre Anrufe bleiben verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-186">Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine anonymen Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1ee40-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-187">Bei importierten Antwortgruppen bleiben anonyme Anrufe verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-188">Reguläre Anrufe bleiben verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-189">Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine anonymen Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1ee40-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-190">Bei importierten Antwortgruppen bleiben anonyme Anrufe verbunden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-191">In Bearbeitung befindliche Anrufe, die noch nicht mit einem Agenten verbunden sind</span><span class="sxs-lookup"><span data-stu-id="1ee40-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-192">Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1ee40-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-193">Bei importierten Antwortgruppen werden Anrufe getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-194">Wenn Reaktionsgruppen nicht importiert wurden, befinden sich in diesem Status keine Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1ee40-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-195">Bei importierten Antwortgruppen werden Anrufe getrennt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-196">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="1ee40-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="1ee40-197">Anrufe stellen eine Verbindung mit dem primären Pool her, aber die im primären Pool verwalteten Agents sind nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="1ee40-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="1ee40-198">Anrufe stellen eine Verbindung mit dem primären Pool her.</span><span class="sxs-lookup"><span data-stu-id="1ee40-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-199">Agenten Anrufe im Namen der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1ee40-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1ee40-200">Das Feature ist in dieser Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ee40-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="1ee40-201">Anrufe erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1ee40-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee40-202">Informationen zu Anmelde-und Agent-Agents</span><span class="sxs-lookup"><span data-stu-id="1ee40-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-203">Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, aber die Agents können sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-204">Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-205">Importierte Agentengruppen werden auf der Agentenkonsole angezeigt, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-206">Agentengruppen, die im Besitz des primären Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-207">Agentengruppen, die im Besitz des Sicherungs Pools sind, können auf der Agentenkonsole angezeigt werden, und die Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-208">Importierte Agentengruppen werden auf der Agentenkonsole nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ee40-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee40-209">Reaktionsgruppen Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1ee40-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-210">Antwortgruppen, die im Besitz des primären Pools sind, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt, aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-211">Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-212">Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1ee40-213">Antwortgruppen, die im Besitz des primären Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-214">Antwortgruppen, die im Besitz des Sicherungs Pools sind, können angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1ee40-215">Importierte Antwortgruppen können nicht mit der lync Server-Systemsteuerung oder dem Reaktionsgruppen-Konfigurations Tool angezeigt werden, können aber mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee40-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

