---
title: Lync Server 2013 Reaktionsgruppen Erfahrung beim Pool Ausfall
description: Lync Server 2013 Reaktionsgruppen Erfahrung beim Pool Ausfall.
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564571"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="b503f-103">Reaktionsgruppen Erfahrung in lync Server 2013 während eines Pool Fehlers</span><span class="sxs-lookup"><span data-stu-id="b503f-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b503f-104">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b503f-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b503f-105">In diesem Abschnitt wird detailliert beschrieben, wie sich die Aktivitäten von Reaktionsgruppen in den folgenden Phasen auswirken:</span><span class="sxs-lookup"><span data-stu-id="b503f-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="b503f-106">Es kommt zu einem Ausfall im primären Pool. Ein Failover wurde jedoch noch nicht initiiert.</span><span class="sxs-lookup"><span data-stu-id="b503f-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="b503f-107">Der Dienst wird in den Sicherungspool verschoben.</span><span class="sxs-lookup"><span data-stu-id="b503f-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="b503f-108">Der Dienst wird wieder in den primären Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="b503f-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="b503f-109">Benutzererfahrung beim Ausfall</span><span class="sxs-lookup"><span data-stu-id="b503f-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="b503f-110">Wenn ein Pool oder ein Standort ausfallen, jedoch noch kein Failover vom Administrator initiiert wurde, werden die Aktivitäten von Reaktionsgruppen wie in der folgenden Tabelle beschrieben verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b503f-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b503f-p101">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden. Verweise auf importierte Reaktionsgruppen in der folgenden Tabelle geben an, dass die Reaktionsgruppen des primären Pools während der Notfallwiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b503f-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="b503f-113">Auftreten eines Ausfalls</span><span class="sxs-lookup"><span data-stu-id="b503f-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b503f-114">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b503f-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="b503f-115">Während des Ausfalls</span><span class="sxs-lookup"><span data-stu-id="b503f-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b503f-116">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="b503f-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-117">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-118">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-119">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="b503f-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="b503f-120">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-121">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="b503f-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-122">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-123">Wenn Reaktionsgruppen importiert wurden, werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="b503f-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-124">Agent-Anrufe für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="b503f-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="b503f-125">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b503f-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-126">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="b503f-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-127">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-128">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-129">Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b503f-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-130">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="b503f-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-131">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-132">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-133">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="b503f-134">Benutzererfahrung beim Failover</span><span class="sxs-lookup"><span data-stu-id="b503f-134">User Experience During Failover</span></span>

<span data-ttu-id="b503f-p102">Wenn ein Administrator ein Failover zu einem Sicherungspool auslöst, werden die Aktivitäten von Reaktionsgruppen während des Failovers sowie im Anschluss daran gemäß den Angaben in der nachstehenden Tabelle verarbeitet. Die erste Spalte gibt an, welche Art von Aktivität stattfinden kann. Die mittlere Spalte gibt an, wie die einzelnen Aktivitäten während des kurzen Vorgangs zum Verschieben in den Sicherungspool verarbeitet werden. Die rechte Spalte gibt schließlich an, wie die Aktivität während des Failover-Vorgangs sowie im Anschluss daran und während der Nutzung des Sicherungspools anstelle des primären Pools verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b503f-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b503f-p103">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b503f-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="b503f-141">Failover wird initiiert</span><span class="sxs-lookup"><span data-stu-id="b503f-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b503f-142">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b503f-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="b503f-143">Während des Failovers</span><span class="sxs-lookup"><span data-stu-id="b503f-143">During Failover</span></span></th>
<th><span data-ttu-id="b503f-144">Nach Abschluss des Failovers</span><span class="sxs-lookup"><span data-stu-id="b503f-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b503f-145">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="b503f-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-146">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-147">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-148">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-149">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten, die den Sicherungspool erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="b503f-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-150">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="b503f-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="b503f-151">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-152">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="b503f-153">Bei importierten Reaktionsgruppen wird die Verbindung von Anrufen erhalten, die den Sicherungspool erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="b503f-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-154">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="b503f-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-155">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-156">Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="b503f-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-157">Wenn keine Reaktionsgruppen importiert wurden, werden die Anrufe getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-158">Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden.</span><span class="sxs-lookup"><span data-stu-id="b503f-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-159">Agent-Anrufe für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="b503f-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="b503f-160">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b503f-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-161">Wenn keine Reaktionsgruppen importiert wurden, tritt bei Anrufen ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="b503f-162">Bei importierten Reaktionsgruppen können die Anrufe erfolgreich getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-163">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="b503f-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-164">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-165">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-166">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="b503f-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-167">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-168">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-169">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="b503f-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-170">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="b503f-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-171">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-172">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-173">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-174">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-175">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-176">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="b503f-177">Benutzererfahrung beim Failback</span><span class="sxs-lookup"><span data-stu-id="b503f-177">User Experience During Failback</span></span>

<span data-ttu-id="b503f-178">Wenn ein Administrator das Failback zum primären Pool initiiert, werden die Aktivitäten von Reaktionsgruppen während des Failbacks sowie im Anschluss daran wie in der folgenden Tabelle verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b503f-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b503f-p104">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b503f-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="b503f-181">Behandlung von Anrufen bei Failbacks</span><span class="sxs-lookup"><span data-stu-id="b503f-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b503f-182">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b503f-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="b503f-183">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="b503f-183">During Failback</span></span></th>
<th><span data-ttu-id="b503f-184">Nach Abschluss des Failbacks</span><span class="sxs-lookup"><span data-stu-id="b503f-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b503f-185">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="b503f-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-186">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-187">Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="b503f-188">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-189">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="b503f-190">Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="b503f-191">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</span><span class="sxs-lookup"><span data-stu-id="b503f-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-192">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="b503f-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-193">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="b503f-194">Die Anrufe von importierten Reaktionsgruppen werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-195">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="b503f-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="b503f-196">Die Anrufe von importierten Reaktionsgruppen werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="b503f-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-197">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="b503f-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="b503f-198">Anrufe werden mit dem primären Pool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="b503f-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="b503f-199">Anrufe werden mit dem primären Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="b503f-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-200">Agent-Anrufe für Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b503f-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="b503f-201">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b503f-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="b503f-202">Die Anrufe können getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b503f-203">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="b503f-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-204">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-205">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-206">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="b503f-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-207">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-208">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="b503f-209">Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b503f-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b503f-210">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="b503f-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b503f-211">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b503f-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-212">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-213">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b503f-214">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-215">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="b503f-216">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b503f-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

