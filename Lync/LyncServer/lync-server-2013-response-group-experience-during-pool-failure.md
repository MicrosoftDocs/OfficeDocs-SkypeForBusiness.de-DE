---
title: Lync Server 2013 Reaktionsgruppen Erfahrung beim Pool Ausfall
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
ms.openlocfilehash: 0e7867af15eb5e8824562eb03244280cfbc84f7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="beb40-102">Reaktionsgruppen Erfahrung in lync Server 2013 während eines Pool Fehlers</span><span class="sxs-lookup"><span data-stu-id="beb40-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beb40-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="beb40-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="beb40-104">In diesem Abschnitt wird detailliert beschrieben, wie sich die Aktivitäten von Reaktionsgruppen in den folgenden Phasen auswirken:</span><span class="sxs-lookup"><span data-stu-id="beb40-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="beb40-105">Es kommt zu einem Ausfall im primären Pool. Ein Failover wurde jedoch noch nicht initiiert.</span><span class="sxs-lookup"><span data-stu-id="beb40-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="beb40-106">Der Dienst wird in den Sicherungspool verschoben.</span><span class="sxs-lookup"><span data-stu-id="beb40-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="beb40-107">Der Dienst wird wieder in den primären Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="beb40-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="beb40-108">Benutzererfahrung beim Ausfall</span><span class="sxs-lookup"><span data-stu-id="beb40-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="beb40-109">Wenn ein Pool oder ein Standort ausfallen, jedoch noch kein Failover vom Administrator initiiert wurde, werden die Aktivitäten von Reaktionsgruppen wie in der folgenden Tabelle beschrieben verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="beb40-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beb40-p101">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden. Verweise auf importierte Reaktionsgruppen in der folgenden Tabelle geben an, dass die Reaktionsgruppen des primären Pools während der Notfallwiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="beb40-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="beb40-112">Auftreten eines Ausfalls</span><span class="sxs-lookup"><span data-stu-id="beb40-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beb40-113">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="beb40-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="beb40-114">Während des Ausfalls</span><span class="sxs-lookup"><span data-stu-id="beb40-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beb40-115">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="beb40-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-116">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-117">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-118">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="beb40-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="beb40-119">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-120">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="beb40-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-121">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-122">Wenn Reaktionsgruppen importiert wurden, werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="beb40-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-123">Agent-Anrufe für Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="beb40-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="beb40-124">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="beb40-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-125">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="beb40-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-126">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-127">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-128">Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beb40-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-129">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="beb40-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-130">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-131">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-132">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="beb40-133">Benutzererfahrung beim Failover</span><span class="sxs-lookup"><span data-stu-id="beb40-133">User Experience During Failover</span></span>

<span data-ttu-id="beb40-p102">Wenn ein Administrator ein Failover zu einem Sicherungspool auslöst, werden die Aktivitäten von Reaktionsgruppen während des Failovers sowie im Anschluss daran gemäß den Angaben in der nachstehenden Tabelle verarbeitet. Die erste Spalte gibt an, welche Art von Aktivität stattfinden kann. Die mittlere Spalte gibt an, wie die einzelnen Aktivitäten während des kurzen Vorgangs zum Verschieben in den Sicherungspool verarbeitet werden. Die rechte Spalte gibt schließlich an, wie die Aktivität während des Failover-Vorgangs sowie im Anschluss daran und während der Nutzung des Sicherungspools anstelle des primären Pools verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="beb40-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beb40-p103">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="beb40-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="beb40-140">Failover wird initiiert</span><span class="sxs-lookup"><span data-stu-id="beb40-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beb40-141">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="beb40-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="beb40-142">Während des Failovers</span><span class="sxs-lookup"><span data-stu-id="beb40-142">During Failover</span></span></th>
<th><span data-ttu-id="beb40-143">Nach Abschluss des Failovers</span><span class="sxs-lookup"><span data-stu-id="beb40-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beb40-144">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="beb40-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-145">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-146">Anonyme Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-147">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-148">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten, die den Sicherungspool erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="beb40-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-149">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="beb40-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="beb40-150">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-151">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="beb40-152">Bei importierten Reaktionsgruppen wird die Verbindung von Anrufen erhalten, die den Sicherungspool erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="beb40-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-153">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="beb40-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-154">Die Anrufe werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-155">Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="beb40-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-156">Wenn keine Reaktionsgruppen importiert wurden, werden die Anrufe getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-157">Bei importierten Reaktionsgruppen werden die Anrufe mit dem Sicherungspool verbunden.</span><span class="sxs-lookup"><span data-stu-id="beb40-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-158">Agent-Anrufe für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="beb40-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="beb40-159">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="beb40-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-160">Wenn keine Reaktionsgruppen importiert wurden, tritt bei Anrufen ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="beb40-161">Bei importierten Reaktionsgruppen können die Anrufe erfolgreich getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-162">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="beb40-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-163">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-164">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-165">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="beb40-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-166">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-167">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-168">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="beb40-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-169">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="beb40-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-170">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-171">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-172">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-173">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-174">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-175">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="beb40-176">Benutzererfahrung beim Failback</span><span class="sxs-lookup"><span data-stu-id="beb40-176">User Experience During Failback</span></span>

<span data-ttu-id="beb40-177">Wenn ein Administrator das Failback zum primären Pool initiiert, werden die Aktivitäten von Reaktionsgruppen während des Failbacks sowie im Anschluss daran wie in der folgenden Tabelle verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="beb40-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beb40-p104">Das Verhalten von Anrufen während einer Notfallwiederherstellung ist abhängig davon, ob die Reaktionsgruppen des primären Pools während der Wiederherstellung in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="beb40-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="beb40-180">Behandlung von Anrufen bei Failbacks</span><span class="sxs-lookup"><span data-stu-id="beb40-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beb40-181">Art der Anruf- oder Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="beb40-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="beb40-182">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="beb40-182">During Failback</span></span></th>
<th><span data-ttu-id="beb40-183">Nach Abschluss des Failbacks</span><span class="sxs-lookup"><span data-stu-id="beb40-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beb40-184">Anrufe, die mit einem Agent verbunden sind</span><span class="sxs-lookup"><span data-stu-id="beb40-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-185">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-186">Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="beb40-187">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-188">Bei regulären Anrufen bleibt die Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="beb40-189">Wenn keine Reaktionsgruppen importiert wurden, weist kein anonymer Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="beb40-190">Bei importierten Reaktionsgruppen wird die Verbindung von anonymen Anrufen erhalten.</span><span class="sxs-lookup"><span data-stu-id="beb40-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-191">Aktive Anrufe, die noch nicht mit einem Agent verbunden wurden</span><span class="sxs-lookup"><span data-stu-id="beb40-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-192">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="beb40-193">Die Anrufe von importierten Reaktionsgruppen werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-194">Wenn keine Reaktionsgruppen importiert wurden, weist kein Anruf diesen Status auf.</span><span class="sxs-lookup"><span data-stu-id="beb40-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="beb40-195">Die Anrufe von importierten Reaktionsgruppen werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="beb40-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-196">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="beb40-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="beb40-197">Anrufe werden mit dem primären Pool verbunden. Agents, die im primären Pool verwaltet werden, sind jedoch nicht erreichbar.</span><span class="sxs-lookup"><span data-stu-id="beb40-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="beb40-198">Anrufe werden mit dem primären Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="beb40-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-199">Agent-Anrufe für Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="beb40-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="beb40-200">Diese Funktion ist in der aktuellen Phase deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="beb40-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="beb40-201">Die Anrufe können getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb40-202">Agent-Anmeldungen und Agent-Informationen</span><span class="sxs-lookup"><span data-stu-id="beb40-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-203">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-204">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-205">Importierte Agent-Gruppen werden in der Agent-Konsole angezeigt, und Agents können sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="beb40-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-206">Agent-Gruppen, die sich im Besitz des primären Pools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-207">Agent-Gruppen, die sich im Besitz des Sicherungspools befinden, können in der Agent-Konsole angezeigt werden. Die Anmeldung von Agents ist möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="beb40-208">Importierte Agent-Gruppen werden nicht in der Agent-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beb40-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb40-209">Konfiguration von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="beb40-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beb40-210">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können je nach Verfügbarkeit der Back-End-Datenbank des primären Pools angezeigt werden. Eine Bearbeitung ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="beb40-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-211">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-212">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="beb40-213">Reaktionsgruppen, die sich im Besitz des primären Pools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-214">Reaktionsgruppen, die sich im Besitz des Sicherungspools befinden, können angezeigt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="beb40-215">Importierte Reaktionsgruppen können nicht mit lync Server-Systemsteuerung oder dem Konfigurations Tool für Reaktionsgruppen angezeigt werden, können jedoch mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="beb40-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

