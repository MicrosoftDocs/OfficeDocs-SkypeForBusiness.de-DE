---
title: 'Lync Server 2013: Vergleichsbericht über Medienqualität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45f2d238d2ffd8df058e31bfa50a51f26c1caf5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="1184a-102">Vergleichsbericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1184a-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1184a-103">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="1184a-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="1184a-104">Mit dem Bericht über die Medienqualität können Sie Anrufqualitätswerte für verschiedene Arten von Audioanrufen vergleichen (z. B. Anrufe über ein Funknetzwerk und Anrufe über eine Kabelverbindung).</span><span class="sxs-lookup"><span data-stu-id="1184a-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="1184a-105">Zugreifen auf den Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="1184a-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="1184a-106">Auf den Bericht über die Medienqualität greifen Sie auf der Startseite Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="1184a-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1184a-107">Filter</span><span class="sxs-lookup"><span data-stu-id="1184a-107">Filters</span></span>

<span data-ttu-id="1184a-p101">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über die Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1184a-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="1184a-110">Filter im Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="1184a-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1184a-111">Name</span><span class="sxs-lookup"><span data-stu-id="1184a-111">Name</span></span></th>
<th><span data-ttu-id="1184a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1184a-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1184a-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-p102">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="1184a-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1184a-116">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="1184a-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1184a-p103">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="1184a-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1184a-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1184a-119">7/7/2012</span></span></p>
<p><span data-ttu-id="1184a-120">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="1184a-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1184a-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1184a-121">7/3/2012</span></span></p>
<p><span data-ttu-id="1184a-122">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="1184a-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-123"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-p104">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="1184a-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1184a-126">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="1184a-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1184a-p105">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="1184a-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1184a-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1184a-129">7/7/2012</span></span></p>
<p><span data-ttu-id="1184a-130">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="1184a-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1184a-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1184a-131">7/3/2012</span></span></p>
<p><span data-ttu-id="1184a-132">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="1184a-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-133"><strong>Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-p106">Der Anruftyp, der als primäres Vergleichselement verwendet werden soll. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1184a-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1184a-136">Alle</span><span class="sxs-lookup"><span data-stu-id="1184a-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="1184a-137">Extern</span><span class="sxs-lookup"><span data-stu-id="1184a-137">External</span></span></p></li>
<li><p><span data-ttu-id="1184a-138">Intern</span><span class="sxs-lookup"><span data-stu-id="1184a-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="1184a-139">VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-140">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-141">Wired</span><span class="sxs-lookup"><span data-stu-id="1184a-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-142">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="1184a-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="1184a-143">Extern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="1184a-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-144">Extern und Funk</span><span class="sxs-lookup"><span data-stu-id="1184a-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="1184a-145">Extern und VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-146">Extern und Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-147">Intern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="1184a-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-148">Intern und Funk</span><span class="sxs-lookup"><span data-stu-id="1184a-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-149"><strong>Mit Anrufen vergleichen</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-p107">Der Anruftyp, der als sekundäres Vergleichselement verwendet werden soll. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1184a-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1184a-152">Alle</span><span class="sxs-lookup"><span data-stu-id="1184a-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="1184a-153">Extern</span><span class="sxs-lookup"><span data-stu-id="1184a-153">External</span></span></p></li>
<li><p><span data-ttu-id="1184a-154">Intern</span><span class="sxs-lookup"><span data-stu-id="1184a-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="1184a-155">VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-156">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-157">Wired</span><span class="sxs-lookup"><span data-stu-id="1184a-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-158">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="1184a-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="1184a-159">Extern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="1184a-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-160">Extern und Funk</span><span class="sxs-lookup"><span data-stu-id="1184a-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="1184a-161">Extern und VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-162">Extern und Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="1184a-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="1184a-163">Intern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="1184a-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="1184a-164">Intern und Funk</span><span class="sxs-lookup"><span data-stu-id="1184a-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-165"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-p108">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1184a-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1184a-168">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="1184a-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1184a-169">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="1184a-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1184a-170">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="1184a-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1184a-p109">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="1184a-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1184a-173">Metriken</span><span class="sxs-lookup"><span data-stu-id="1184a-173">Metrics</span></span>

<span data-ttu-id="1184a-174">In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht über die Medienqualität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1184a-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="1184a-175">Metriken im Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="1184a-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1184a-176">Name</span><span class="sxs-lookup"><span data-stu-id="1184a-176">Name</span></span></th>
<th><span data-ttu-id="1184a-177">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="1184a-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1184a-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1184a-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1184a-179"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-180">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-180">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-181">Die Gesamtzahl der Anrufe.</span><span class="sxs-lookup"><span data-stu-id="1184a-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-182"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-183">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-183">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-184">Durchschnittliche Menge an MOS (Mean Opinion Score) Verschlechterung während eines Anrufs erlebt.</span><span class="sxs-lookup"><span data-stu-id="1184a-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="1184a-185">Die Werte für die Verschlechterung können zwischen einem Tiefstwert von 0,0 und einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder niedriger stellt eine akzeptable Beeinträchtigung dar.</span><span class="sxs-lookup"><span data-stu-id="1184a-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="1184a-186">Historisch gesehen wurden mittlere Meinungs Ergebnisse berechnet, indem Benutzer die Qualität eines Anrufs auf einer Skala von 1 bis 5 bewerten ließen.</span><span class="sxs-lookup"><span data-stu-id="1184a-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="1184a-187">Lync Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="1184a-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="1184a-p111">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="1184a-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-190"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-191">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-191">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p112">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="1184a-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-194"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-195">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-195">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p113">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="1184a-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1184a-p114">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="1184a-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-200"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-201">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-201">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p115">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="1184a-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-205"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-206">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-206">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-207">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1184a-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1184a-208">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="1184a-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-209"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-210">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-210">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p117">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="1184a-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1184a-213"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-214">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-214">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p118">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="1184a-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1184a-217"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="1184a-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1184a-218">Nein</span><span class="sxs-lookup"><span data-stu-id="1184a-218">No</span></span></p></td>
<td><p><span data-ttu-id="1184a-p119">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="1184a-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

