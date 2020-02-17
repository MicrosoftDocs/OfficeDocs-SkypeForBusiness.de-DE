---
title: 'Lync Server 2013: Verteilungs Bericht über Medien Qualitäts Metriken'
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
ms.openlocfilehash: 38adc41aaffcccbb27d4c9105f0fecabcae3c21c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="3545f-102">Der Verteilungs Bericht zur Medien Qualitätsmetrik in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3545f-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3545f-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="3545f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="3545f-104">Der Bericht zur Verteilung von Medienqualität-Metriken ermöglicht Ihnen das Anzeigen eines Diagramms, in dem die Verteilungswerte für eine Metrik für die Qualität der Erfahrung wie Jitter oder Paketverlust angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3545f-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="3545f-105">Nehmen Sie beispielsweise an, dass Ihre Benutzer insgesamt 10 Telefonanrufe tätigen; bei diesen 10 aufrufen wird die folgende Roundtrip-Zeit gemeldet:</span><span class="sxs-lookup"><span data-stu-id="3545f-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3545f-106">Rufnummer</span><span class="sxs-lookup"><span data-stu-id="3545f-106">Call Number</span></span></th>
<th><span data-ttu-id="3545f-107">Roundtrip-Zeit (Millisekunden)</span><span class="sxs-lookup"><span data-stu-id="3545f-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3545f-108">1</span><span class="sxs-lookup"><span data-stu-id="3545f-108">1</span></span></p></td>
<td><p><span data-ttu-id="3545f-109">50</span><span class="sxs-lookup"><span data-stu-id="3545f-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-110">2</span><span class="sxs-lookup"><span data-stu-id="3545f-110">2</span></span></p></td>
<td><p><span data-ttu-id="3545f-111">50</span><span class="sxs-lookup"><span data-stu-id="3545f-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-112">3</span><span class="sxs-lookup"><span data-stu-id="3545f-112">3</span></span></p></td>
<td><p><span data-ttu-id="3545f-113">50</span><span class="sxs-lookup"><span data-stu-id="3545f-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-114">4 </span><span class="sxs-lookup"><span data-stu-id="3545f-114">4</span></span></p></td>
<td><p><span data-ttu-id="3545f-115">50</span><span class="sxs-lookup"><span data-stu-id="3545f-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-116">5 </span><span class="sxs-lookup"><span data-stu-id="3545f-116">5</span></span></p></td>
<td><p><span data-ttu-id="3545f-117">50</span><span class="sxs-lookup"><span data-stu-id="3545f-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-118">6 </span><span class="sxs-lookup"><span data-stu-id="3545f-118">6</span></span></p></td>
<td><p><span data-ttu-id="3545f-119">50</span><span class="sxs-lookup"><span data-stu-id="3545f-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-120">7 </span><span class="sxs-lookup"><span data-stu-id="3545f-120">7</span></span></p></td>
<td><p><span data-ttu-id="3545f-121">50</span><span class="sxs-lookup"><span data-stu-id="3545f-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-122">8 </span><span class="sxs-lookup"><span data-stu-id="3545f-122">8</span></span></p></td>
<td><p><span data-ttu-id="3545f-123">4550</span><span class="sxs-lookup"><span data-stu-id="3545f-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-124">9 </span><span class="sxs-lookup"><span data-stu-id="3545f-124">9</span></span></p></td>
<td><p><span data-ttu-id="3545f-125">50</span><span class="sxs-lookup"><span data-stu-id="3545f-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-126">10 </span><span class="sxs-lookup"><span data-stu-id="3545f-126">10</span></span></p></td>
<td><p><span data-ttu-id="3545f-127">50</span><span class="sxs-lookup"><span data-stu-id="3545f-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3545f-128">Der Durchschnitt für diese Roundtrip-Zeiten beträgt 500 Millisekunden (5000 dividiert durch 10).</span><span class="sxs-lookup"><span data-stu-id="3545f-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="3545f-129">500 Millisekunden ist eine extrem große Roundtrip-Zeit; Daher glauben Sie möglicherweise, dass Sie ein ernstes Problem mit Netzwerküberlastung haben.</span><span class="sxs-lookup"><span data-stu-id="3545f-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="3545f-130">(Lange Roundtrip-Zeiten sind normalerweise das Ergebnis von überladenen Netzwerken.)</span><span class="sxs-lookup"><span data-stu-id="3545f-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="3545f-131">In Wirklichkeit hatten natürlich 90% ihrer Anrufe ausgezeichnete roundtripzeiten; Sie haben lediglich einen schlechten Anruf gehabt, der die Gesamtergebnisse verzerrt hat.</span><span class="sxs-lookup"><span data-stu-id="3545f-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="3545f-132">Wenn Sie nur die durchschnittliche Roundtripzeit betrachten, können Sie zu einer sehr falschen Schlussfolgerung springen.</span><span class="sxs-lookup"><span data-stu-id="3545f-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="3545f-133">Der Bericht zur Verteilung von Medienqualität-Metriken hilft Ihnen, zu falschen Schlussfolgerungen zu springen, indem eine grafische Verteilung einer bestimmten Metrik angezeigt wird (beispielsweise Roundtrip-Zeit).</span><span class="sxs-lookup"><span data-stu-id="3545f-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="3545f-134">Diese Diagramme können Ihnen dabei helfen, deutlich zu machen, dass Sie neun sehr gute Anrufe und einen sehr schlechten Anruf hatten.</span><span class="sxs-lookup"><span data-stu-id="3545f-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="3545f-135">Allerdings möchten Sie möglicherweise weiterhin diesen einen Anruf untersuchen; die Tatsache, dass 9 von 10 anrufen sehr gut waren, deutet jedoch darauf hin, dass es keinen Grund gibt, drastische Änderungen an Ihrem Netzwerk vorzunehmen, zumindest nicht zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="3545f-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="3545f-136">Filter</span><span class="sxs-lookup"><span data-stu-id="3545f-136">Filters</span></span>

<span data-ttu-id="3545f-137">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3545f-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3545f-138">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Verteilungs Bericht über Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3545f-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="3545f-139">Medien Qualitäts Metriken Verteilungs Berichtsfilter</span><span class="sxs-lookup"><span data-stu-id="3545f-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3545f-140">Name</span><span class="sxs-lookup"><span data-stu-id="3545f-140">Name</span></span></th>
<th><span data-ttu-id="3545f-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3545f-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3545f-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3545f-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3545f-145">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="3545f-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3545f-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="3545f-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3545f-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3545f-148">7/7/2012</span></span></p>
<p><span data-ttu-id="3545f-149">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="3545f-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3545f-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3545f-150">7/3/2012</span></span></p>
<p><span data-ttu-id="3545f-151">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="3545f-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-152"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3545f-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3545f-155">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="3545f-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3545f-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="3545f-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3545f-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3545f-158">7/7/2012</span></span></p>
<p><span data-ttu-id="3545f-159">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="3545f-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3545f-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3545f-160">7/3/2012</span></span></p>
<p><span data-ttu-id="3545f-161">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="3545f-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-162"><strong>Minimum in x-Achse</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-163">Der niedrigste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3545f-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-164"><strong>Maximum in x-Achse</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-165">Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3545f-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-166"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-p110">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3545f-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3545f-169">Alle</span><span class="sxs-lookup"><span data-stu-id="3545f-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="3545f-170">Intern</span><span class="sxs-lookup"><span data-stu-id="3545f-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="3545f-171">Extern</span><span class="sxs-lookup"><span data-stu-id="3545f-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3545f-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3545f-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3545f-175">Alle</span><span class="sxs-lookup"><span data-stu-id="3545f-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="3545f-176">VPN</span><span class="sxs-lookup"><span data-stu-id="3545f-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="3545f-177">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="3545f-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3545f-178"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="3545f-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3545f-p112">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3545f-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3545f-181">Alle</span><span class="sxs-lookup"><span data-stu-id="3545f-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="3545f-182">Wired</span><span class="sxs-lookup"><span data-stu-id="3545f-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="3545f-183">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="3545f-183">Wireless</span></span></p></li>
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

