---
title: 'Lync Server 2013: Konferenz Zusammenfassungs Unterbericht'
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
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="c4264-102">Konferenz Zusammenfassung Unterbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4264-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4264-103">_**Letztes Änderungsdatum des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="c4264-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="c4264-p101">Der zusammenfassende Konferenzunterbericht stellt eine Gesamtübersicht zu gescheiterten Konferenzsitzungen bereit, bei denen Fehler aufgetreten sind. Diese gescheiterten Sitzungen sind weiter nach Sitzungstyp unterteilt: Konferenzzustandsobjekt-Sitzungen und MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4264-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="c4264-106">Filter</span><span class="sxs-lookup"><span data-stu-id="c4264-106">Filters</span></span>

<span data-ttu-id="c4264-p102">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Konferenzunterbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c4264-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="c4264-109">Filter im zusammenfassenden Konferenzunterbericht</span><span class="sxs-lookup"><span data-stu-id="c4264-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4264-110">Name</span><span class="sxs-lookup"><span data-stu-id="c4264-110">Name</span></span></th>
<th><span data-ttu-id="c4264-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4264-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4264-112"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-p103">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c4264-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c4264-115">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c4264-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4264-p104">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c4264-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4264-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c4264-118">7/7/2012</span></span></p>
<p><span data-ttu-id="c4264-119">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c4264-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4264-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c4264-120">7/3/2012</span></span></p>
<p><span data-ttu-id="c4264-121">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c4264-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4264-122"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-p105">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c4264-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c4264-125">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c4264-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4264-p106">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c4264-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4264-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c4264-128">7/7/2012</span></span></p>
<p><span data-ttu-id="c4264-129">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c4264-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4264-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c4264-130">7/3/2012</span></span></p>
<p><span data-ttu-id="c4264-131">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c4264-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4264-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-p107">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="c4264-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c4264-136">Metriken</span><span class="sxs-lookup"><span data-stu-id="c4264-136">Metrics</span></span>

<span data-ttu-id="c4264-137">In der folgenden Tabelle sind die Metriken aufgelistet, die im zusammenfassenden Konferenzunterbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4264-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="c4264-138">Metriken im zusammenfassenden Konferenzunterbericht</span><span class="sxs-lookup"><span data-stu-id="c4264-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4264-139">Name</span><span class="sxs-lookup"><span data-stu-id="c4264-139">Name</span></span></th>
<th><span data-ttu-id="c4264-140">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="c4264-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c4264-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4264-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4264-142"><strong>Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-143">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-143">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-144">Gesamtzahl der Konferenzen, die durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c4264-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4264-145"><strong>Konferenzsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-146">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-146">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-p108">Gesamtzahl der Konferenzsitzungen. Eine einzelne Konferenz kann mehrere Sitzungen haben. Beispielsweise kann eine Konferenz sowohl eine Konferenzzustandsobjekt-Sitzung als auch eine MCU-Sitzung umfassen.</span><span class="sxs-lookup"><span data-stu-id="c4264-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4264-149"><strong>Sitzungsfehlerrate insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-150">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-150">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-151">Prozentsatz aller gescheiterten Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="c4264-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4264-152"><strong>Konferenzzustandsobjekt-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-153">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-153">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-154">Gesamtanzahl der Konferenzzustandsobjekt-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4264-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4264-155"><strong>Fehlerrate für Konferenzzustandsobjekt</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-156">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-156">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-157">Prozentsatz der gescheiterten Konferenzzustandsobjekt-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4264-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4264-158">MCU-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c4264-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="c4264-159">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-159">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-160">Gesamtanzahl der MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4264-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4264-161"><strong>MCU-Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-162">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-162">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-163">Prozentsatz der gescheiterten MCU-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4264-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4264-164"><strong>MCU-Sitzungen nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-165">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-165">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-166">Gesamtanzahl der MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</span><span class="sxs-lookup"><span data-stu-id="c4264-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4264-167"><strong>Fehlerrate nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="c4264-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c4264-168">Nein</span><span class="sxs-lookup"><span data-stu-id="c4264-168">No</span></span></p></td>
<td><p><span data-ttu-id="c4264-169">Prozentsatz der gescheiterten MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</span><span class="sxs-lookup"><span data-stu-id="c4264-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

