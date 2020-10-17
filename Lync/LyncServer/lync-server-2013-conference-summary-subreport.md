---
title: 'Lync Server 2013: zusammenfassender Konferenz-Unterbericht'
description: 'Lync Server 2013: zusammenfassender Konferenz-Unterbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550691"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="4760b-103">Konferenz Zusammenfassung Unterbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4760b-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4760b-104">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="4760b-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="4760b-p101">Der zusammenfassende Konferenzunterbericht stellt eine Gesamtübersicht zu gescheiterten Konferenzsitzungen bereit, bei denen Fehler aufgetreten sind. Diese gescheiterten Sitzungen sind weiter nach Sitzungstyp unterteilt: Konferenzzustandsobjekt-Sitzungen und MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4760b-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="4760b-107">Filter</span><span class="sxs-lookup"><span data-stu-id="4760b-107">Filters</span></span>

<span data-ttu-id="4760b-p102">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Konferenzunterbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4760b-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="4760b-110">Filter im zusammenfassenden Konferenzunterbericht</span><span class="sxs-lookup"><span data-stu-id="4760b-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4760b-111">Name</span><span class="sxs-lookup"><span data-stu-id="4760b-111">Name</span></span></th>
<th><span data-ttu-id="4760b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4760b-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4760b-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-p103">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4760b-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4760b-116">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4760b-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4760b-p104">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4760b-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4760b-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4760b-119">7/7/2012</span></span></p>
<p><span data-ttu-id="4760b-120">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4760b-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4760b-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4760b-121">7/3/2012</span></span></p>
<p><span data-ttu-id="4760b-122">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4760b-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4760b-123"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-p105">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4760b-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4760b-126">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4760b-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4760b-p106">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4760b-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4760b-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4760b-129">7/7/2012</span></span></p>
<p><span data-ttu-id="4760b-130">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4760b-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4760b-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4760b-131">7/3/2012</span></span></p>
<p><span data-ttu-id="4760b-132">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4760b-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4760b-133"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-p107">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4760b-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4760b-137">Metriken</span><span class="sxs-lookup"><span data-stu-id="4760b-137">Metrics</span></span>

<span data-ttu-id="4760b-138">In der folgenden Tabelle sind die Metriken aufgelistet, die im zusammenfassenden Konferenzunterbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4760b-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="4760b-139">Metriken im zusammenfassenden Konferenzunterbericht</span><span class="sxs-lookup"><span data-stu-id="4760b-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4760b-140">Name</span><span class="sxs-lookup"><span data-stu-id="4760b-140">Name</span></span></th>
<th><span data-ttu-id="4760b-141">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="4760b-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4760b-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4760b-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4760b-143"><strong>Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-144">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-144">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-145">Gesamtzahl der Konferenzen, die durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="4760b-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4760b-146"><strong>Konferenzsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-147">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-147">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-p108">Gesamtzahl der Konferenzsitzungen. Eine einzelne Konferenz kann mehrere Sitzungen haben. Beispielsweise kann eine Konferenz sowohl eine Konferenzzustandsobjekt-Sitzung als auch eine MCU-Sitzung umfassen.</span><span class="sxs-lookup"><span data-stu-id="4760b-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4760b-150"><strong>Sitzungsfehlerrate insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-151">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-151">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-152">Prozentsatz aller gescheiterten Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="4760b-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4760b-153"><strong>Konferenzzustandsobjekt-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-154">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-154">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-155">Gesamtanzahl der Konferenzzustandsobjekt-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4760b-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4760b-156"><strong>Fehlerrate für Konferenzzustandsobjekt</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-157">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-157">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-158">Prozentsatz der gescheiterten Konferenzzustandsobjekt-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4760b-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4760b-159">MCU-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4760b-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="4760b-160">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-160">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-161">Gesamtanzahl der MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4760b-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4760b-162"><strong>MCU-Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-163">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-163">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-164">Prozentsatz der gescheiterten MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4760b-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4760b-165"><strong>MCU-Sitzungen nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-166">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-166">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-167">Gesamtanzahl der MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</span><span class="sxs-lookup"><span data-stu-id="4760b-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4760b-168"><strong>Fehlerrate nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="4760b-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="4760b-169">Nein</span><span class="sxs-lookup"><span data-stu-id="4760b-169">No</span></span></p></td>
<td><p><span data-ttu-id="4760b-170">Prozentsatz der gescheiterten MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</span><span class="sxs-lookup"><span data-stu-id="4760b-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

