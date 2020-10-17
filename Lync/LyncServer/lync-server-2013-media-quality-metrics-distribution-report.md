---
title: 'Lync Server 2013: Verteilungs Bericht über Medien Qualitäts Metriken'
description: 'Lync Server 2013: Verteilungs Bericht über Medienqualität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548151"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="48907-103">Der Verteilungs Bericht zur Medien Qualitätsmetrik in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48907-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48907-104">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="48907-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="48907-105">Der Bericht zur Verteilung von Medienqualität-Metriken ermöglicht Ihnen das Anzeigen eines Diagramms, in dem die Verteilungswerte für eine Metrik für die Qualität der Erfahrung wie Jitter oder Paketverlust angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="48907-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="48907-106">Nehmen Sie beispielsweise an, dass Ihre Benutzer insgesamt 10 Telefonanrufe tätigen; bei diesen 10 aufrufen wird die folgende Roundtrip-Zeit gemeldet:</span><span class="sxs-lookup"><span data-stu-id="48907-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48907-107">Rufnummer</span><span class="sxs-lookup"><span data-stu-id="48907-107">Call Number</span></span></th>
<th><span data-ttu-id="48907-108">Roundtrip-Zeit (Millisekunden)</span><span class="sxs-lookup"><span data-stu-id="48907-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48907-109">1</span><span class="sxs-lookup"><span data-stu-id="48907-109">1</span></span></p></td>
<td><p><span data-ttu-id="48907-110">50</span><span class="sxs-lookup"><span data-stu-id="48907-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-111">2</span><span class="sxs-lookup"><span data-stu-id="48907-111">2</span></span></p></td>
<td><p><span data-ttu-id="48907-112">50</span><span class="sxs-lookup"><span data-stu-id="48907-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-113">3</span><span class="sxs-lookup"><span data-stu-id="48907-113">3</span></span></p></td>
<td><p><span data-ttu-id="48907-114">50</span><span class="sxs-lookup"><span data-stu-id="48907-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-115">4 </span><span class="sxs-lookup"><span data-stu-id="48907-115">4</span></span></p></td>
<td><p><span data-ttu-id="48907-116">50</span><span class="sxs-lookup"><span data-stu-id="48907-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-117">5 </span><span class="sxs-lookup"><span data-stu-id="48907-117">5</span></span></p></td>
<td><p><span data-ttu-id="48907-118">50</span><span class="sxs-lookup"><span data-stu-id="48907-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-119">6 </span><span class="sxs-lookup"><span data-stu-id="48907-119">6</span></span></p></td>
<td><p><span data-ttu-id="48907-120">50</span><span class="sxs-lookup"><span data-stu-id="48907-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-121">7 </span><span class="sxs-lookup"><span data-stu-id="48907-121">7</span></span></p></td>
<td><p><span data-ttu-id="48907-122">50</span><span class="sxs-lookup"><span data-stu-id="48907-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-123">8 </span><span class="sxs-lookup"><span data-stu-id="48907-123">8</span></span></p></td>
<td><p><span data-ttu-id="48907-124">4550</span><span class="sxs-lookup"><span data-stu-id="48907-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-125">9 </span><span class="sxs-lookup"><span data-stu-id="48907-125">9</span></span></p></td>
<td><p><span data-ttu-id="48907-126">50</span><span class="sxs-lookup"><span data-stu-id="48907-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-127">10 </span><span class="sxs-lookup"><span data-stu-id="48907-127">10</span></span></p></td>
<td><p><span data-ttu-id="48907-128">50</span><span class="sxs-lookup"><span data-stu-id="48907-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="48907-129">Der Durchschnitt für diese Roundtrip-Zeiten beträgt 500 Millisekunden (5000 dividiert durch 10).</span><span class="sxs-lookup"><span data-stu-id="48907-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="48907-130">500 Millisekunden ist eine extrem große Roundtrip-Zeit; Daher glauben Sie möglicherweise, dass Sie ein ernstes Problem mit Netzwerküberlastung haben.</span><span class="sxs-lookup"><span data-stu-id="48907-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="48907-131">(Lange Roundtrip-Zeiten sind normalerweise das Ergebnis von überladenen Netzwerken.)</span><span class="sxs-lookup"><span data-stu-id="48907-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="48907-132">In Wirklichkeit hatten natürlich 90% ihrer Anrufe ausgezeichnete roundtripzeiten; Sie haben lediglich einen schlechten Anruf gehabt, der die Gesamtergebnisse verzerrt hat.</span><span class="sxs-lookup"><span data-stu-id="48907-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="48907-133">Wenn Sie nur die durchschnittliche Roundtripzeit betrachten, können Sie zu einer sehr falschen Schlussfolgerung springen.</span><span class="sxs-lookup"><span data-stu-id="48907-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="48907-134">Der Bericht zur Verteilung von Medienqualität-Metriken hilft Ihnen, zu falschen Schlussfolgerungen zu springen, indem eine grafische Verteilung einer bestimmten Metrik angezeigt wird (beispielsweise Roundtrip-Zeit).</span><span class="sxs-lookup"><span data-stu-id="48907-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="48907-135">Diese Diagramme können Ihnen dabei helfen, deutlich zu machen, dass Sie neun sehr gute Anrufe und einen sehr schlechten Anruf hatten.</span><span class="sxs-lookup"><span data-stu-id="48907-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="48907-136">Allerdings möchten Sie möglicherweise weiterhin diesen einen Anruf untersuchen; die Tatsache, dass 9 von 10 anrufen sehr gut waren, deutet jedoch darauf hin, dass es keinen Grund gibt, drastische Änderungen an Ihrem Netzwerk vorzunehmen, zumindest nicht zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="48907-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="48907-137">Filter</span><span class="sxs-lookup"><span data-stu-id="48907-137">Filters</span></span>

<span data-ttu-id="48907-138">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="48907-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="48907-139">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Verteilungs Bericht über Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="48907-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="48907-140">Medien Qualitäts Metriken Verteilungs Berichtsfilter</span><span class="sxs-lookup"><span data-stu-id="48907-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48907-141">Name</span><span class="sxs-lookup"><span data-stu-id="48907-141">Name</span></span></th>
<th><span data-ttu-id="48907-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48907-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48907-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="48907-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="48907-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="48907-146">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="48907-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="48907-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="48907-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="48907-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="48907-149">7/7/2012</span></span></p>
<p><span data-ttu-id="48907-150">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="48907-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="48907-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="48907-151">7/3/2012</span></span></p>
<p><span data-ttu-id="48907-152">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="48907-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-153"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="48907-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="48907-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="48907-156">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="48907-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="48907-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="48907-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="48907-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="48907-159">7/7/2012</span></span></p>
<p><span data-ttu-id="48907-160">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="48907-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="48907-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="48907-161">7/3/2012</span></span></p>
<p><span data-ttu-id="48907-162">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="48907-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-163"><strong>Minimum in x-Achse</strong></span><span class="sxs-lookup"><span data-stu-id="48907-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-164">Der niedrigste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="48907-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-165"><strong>Maximum in x-Achse</strong></span><span class="sxs-lookup"><span data-stu-id="48907-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-166">Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="48907-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-167"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="48907-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-p110">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="48907-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="48907-170">Alle</span><span class="sxs-lookup"><span data-stu-id="48907-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="48907-171">Intern</span><span class="sxs-lookup"><span data-stu-id="48907-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="48907-172">Extern</span><span class="sxs-lookup"><span data-stu-id="48907-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48907-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="48907-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="48907-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="48907-176">Alle</span><span class="sxs-lookup"><span data-stu-id="48907-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="48907-177">VPN</span><span class="sxs-lookup"><span data-stu-id="48907-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="48907-178">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="48907-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48907-179"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="48907-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="48907-p112">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="48907-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="48907-182">Alle</span><span class="sxs-lookup"><span data-stu-id="48907-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="48907-183">Wired</span><span class="sxs-lookup"><span data-stu-id="48907-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="48907-184">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="48907-184">Wireless</span></span></p></li>
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

