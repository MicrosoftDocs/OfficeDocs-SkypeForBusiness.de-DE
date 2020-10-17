---
title: 'Lync Server 2013: P2P-zusammenfassender Unterbericht'
description: 'Lync Server 2013: P2P-zusammenfassender Unterbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557381"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="90d86-103">Unterbericht über P2P-Zusammenfassung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d86-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90d86-104">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="90d86-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="90d86-105">Der Unterbericht über P2P-Zusammenfassung bietet eine Übersicht über Ihre fehlgeschlagenen Peer-zu-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="90d86-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="90d86-106">Filter</span><span class="sxs-lookup"><span data-stu-id="90d86-106">Filters</span></span>

<span data-ttu-id="90d86-107">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="90d86-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="90d86-108">In der folgenden Tabelle sind die Filter aufgeführt, die Sie im zusammenfassenden P2P-Unterbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="90d86-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="90d86-109">P2P-Zusammenfassungs-Unterbericht Filter</span><span class="sxs-lookup"><span data-stu-id="90d86-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d86-110">Name</span><span class="sxs-lookup"><span data-stu-id="90d86-110">Name</span></span></th>
<th><span data-ttu-id="90d86-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d86-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d86-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-p102">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="90d86-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="90d86-115">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="90d86-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="90d86-p103">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="90d86-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="90d86-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="90d86-118">7/7/2012</span></span></p>
<p><span data-ttu-id="90d86-119">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="90d86-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="90d86-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="90d86-120">7/3/2012</span></span></p>
<p><span data-ttu-id="90d86-121">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="90d86-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d86-122"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-p104">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="90d86-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="90d86-125">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="90d86-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="90d86-p105">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="90d86-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="90d86-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="90d86-128">7/7/2012</span></span></p>
<p><span data-ttu-id="90d86-129">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="90d86-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="90d86-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="90d86-130">7/3/2012</span></span></p>
<p><span data-ttu-id="90d86-131">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="90d86-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d86-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-p106">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="90d86-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="90d86-136">Metriken</span><span class="sxs-lookup"><span data-stu-id="90d86-136">Metrics</span></span>

<span data-ttu-id="90d86-137">In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden P2P-Unterbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="90d86-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="90d86-138">Metriken für den zusammenfassenden P2P-Unterbericht</span><span class="sxs-lookup"><span data-stu-id="90d86-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d86-139">Name</span><span class="sxs-lookup"><span data-stu-id="90d86-139">Name</span></span></th>
<th><span data-ttu-id="90d86-140">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="90d86-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="90d86-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d86-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d86-142"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-143">Nein</span><span class="sxs-lookup"><span data-stu-id="90d86-143">No</span></span></p></td>
<td><p><span data-ttu-id="90d86-144">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="90d86-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d86-145"><strong>Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-146">Nein</span><span class="sxs-lookup"><span data-stu-id="90d86-146">No</span></span></p></td>
<td><p><span data-ttu-id="90d86-147">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="90d86-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d86-148"><strong>Sitzungen nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-149">Nein</span><span class="sxs-lookup"><span data-stu-id="90d86-149">No</span></span></p></td>
<td><p><span data-ttu-id="90d86-150">Die Gesamtzahl der Sitzungen, die nach Modalität gruppiert sind (beispielsweise Chatnachrichten).</span><span class="sxs-lookup"><span data-stu-id="90d86-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d86-151"><strong>Fehlerrate nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="90d86-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="90d86-152">Nein</span><span class="sxs-lookup"><span data-stu-id="90d86-152">No</span></span></p></td>
<td><p><span data-ttu-id="90d86-153">Gesamtanzahl der fehlgeschlagenen Sitzungen, gruppiert nach Modalität (beispielsweise Chatnachrichten).</span><span class="sxs-lookup"><span data-stu-id="90d86-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

