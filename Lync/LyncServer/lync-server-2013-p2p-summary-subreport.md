---
title: 'Lync Server 2013: P2P-zusammenfassender Unterbericht'
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
ms.openlocfilehash: ffa28f05ae8059244f53575c01f02551cbaffc95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="7847f-102">Unterbericht über P2P-Zusammenfassung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7847f-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7847f-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7847f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7847f-104">Der Unterbericht über P2P-Zusammenfassung bietet eine Übersicht über Ihre fehlgeschlagenen Peer-zu-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="7847f-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="7847f-105">Filter</span><span class="sxs-lookup"><span data-stu-id="7847f-105">Filters</span></span>

<span data-ttu-id="7847f-106">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7847f-106">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7847f-107">In der folgenden Tabelle sind die Filter aufgeführt, die Sie im zusammenfassenden P2P-Unterbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7847f-107">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="7847f-108">P2P-Zusammenfassungs-Unterbericht Filter</span><span class="sxs-lookup"><span data-stu-id="7847f-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7847f-109">Name</span><span class="sxs-lookup"><span data-stu-id="7847f-109">Name</span></span></th>
<th><span data-ttu-id="7847f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7847f-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7847f-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-p102">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7847f-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7847f-114">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7847f-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7847f-p103">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7847f-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7847f-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7847f-117">7/7/2012</span></span></p>
<p><span data-ttu-id="7847f-118">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7847f-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7847f-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7847f-119">7/3/2012</span></span></p>
<p><span data-ttu-id="7847f-120">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7847f-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7847f-121"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-p104">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7847f-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7847f-124">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7847f-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7847f-p105">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7847f-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7847f-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7847f-127">7/7/2012</span></span></p>
<p><span data-ttu-id="7847f-128">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7847f-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7847f-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7847f-129">7/3/2012</span></span></p>
<p><span data-ttu-id="7847f-130">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7847f-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7847f-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-p106">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7847f-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7847f-135">Metriken</span><span class="sxs-lookup"><span data-stu-id="7847f-135">Metrics</span></span>

<span data-ttu-id="7847f-136">In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden P2P-Unterbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7847f-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="7847f-137">Metriken für den zusammenfassenden P2P-Unterbericht</span><span class="sxs-lookup"><span data-stu-id="7847f-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7847f-138">Name</span><span class="sxs-lookup"><span data-stu-id="7847f-138">Name</span></span></th>
<th><span data-ttu-id="7847f-139">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="7847f-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7847f-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7847f-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7847f-141"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-142">Nein</span><span class="sxs-lookup"><span data-stu-id="7847f-142">No</span></span></p></td>
<td><p><span data-ttu-id="7847f-143">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7847f-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7847f-144"><strong>Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-145">Nein</span><span class="sxs-lookup"><span data-stu-id="7847f-145">No</span></span></p></td>
<td><p><span data-ttu-id="7847f-146">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7847f-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7847f-147"><strong>Sitzungen nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-148">Nein</span><span class="sxs-lookup"><span data-stu-id="7847f-148">No</span></span></p></td>
<td><p><span data-ttu-id="7847f-149">Die Gesamtzahl der Sitzungen, die nach Modalität gruppiert sind (beispielsweise Chatnachrichten).</span><span class="sxs-lookup"><span data-stu-id="7847f-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7847f-150"><strong>Fehlerrate nach Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="7847f-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7847f-151">Nein</span><span class="sxs-lookup"><span data-stu-id="7847f-151">No</span></span></p></td>
<td><p><span data-ttu-id="7847f-152">Gesamtanzahl der fehlgeschlagenen Sitzungen, gruppiert nach Modalität (beispielsweise Chatnachrichten).</span><span class="sxs-lookup"><span data-stu-id="7847f-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

