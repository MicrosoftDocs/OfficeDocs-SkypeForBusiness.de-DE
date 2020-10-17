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
ms.openlocfilehash: 05b157be6cc94f0b01dbefadfd89041118b944e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500662"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="25e24-102">Vergleichsbericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25e24-102">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e24-103">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="25e24-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="25e24-104">Mit dem Bericht über die Medienqualität können Sie Anrufqualitätswerte für verschiedene Arten von Audioanrufen vergleichen (z. B. Anrufe über ein Funknetzwerk und Anrufe über eine Kabelverbindung).</span><span class="sxs-lookup"><span data-stu-id="25e24-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="25e24-105">Zugreifen auf den Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="25e24-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="25e24-106">Auf den Bericht über die Medienqualität greifen Sie auf der Startseite Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="25e24-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="25e24-107">Filter</span><span class="sxs-lookup"><span data-stu-id="25e24-107">Filters</span></span>

<span data-ttu-id="25e24-p101">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über die Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="25e24-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="25e24-110">Filter im Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="25e24-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25e24-111">Name</span><span class="sxs-lookup"><span data-stu-id="25e24-111">Name</span></span></th>
<th><span data-ttu-id="25e24-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25e24-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25e24-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-p102">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="25e24-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="25e24-116">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="25e24-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="25e24-p103">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="25e24-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="25e24-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="25e24-119">7/7/2012</span></span></p>
<p><span data-ttu-id="25e24-120">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="25e24-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="25e24-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="25e24-121">7/3/2012</span></span></p>
<p><span data-ttu-id="25e24-122">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="25e24-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-123"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-p104">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="25e24-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="25e24-126">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="25e24-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="25e24-p105">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="25e24-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="25e24-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="25e24-129">7/7/2012</span></span></p>
<p><span data-ttu-id="25e24-130">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="25e24-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="25e24-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="25e24-131">7/3/2012</span></span></p>
<p><span data-ttu-id="25e24-132">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="25e24-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-133"><strong>Aufrufe</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-p106">Der Anruftyp, der als primäres Vergleichselement verwendet werden soll. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="25e24-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="25e24-136">Alle</span><span class="sxs-lookup"><span data-stu-id="25e24-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="25e24-137">Extern</span><span class="sxs-lookup"><span data-stu-id="25e24-137">External</span></span></p></li>
<li><p><span data-ttu-id="25e24-138">Intern</span><span class="sxs-lookup"><span data-stu-id="25e24-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="25e24-139">VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-140">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-141">Wired</span><span class="sxs-lookup"><span data-stu-id="25e24-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-142">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="25e24-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="25e24-143">Extern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="25e24-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-144">Extern und Funk</span><span class="sxs-lookup"><span data-stu-id="25e24-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="25e24-145">Extern und VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-146">Extern und Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-147">Intern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="25e24-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-148">Intern und Funk</span><span class="sxs-lookup"><span data-stu-id="25e24-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-149"><strong>Mit Anrufen vergleichen</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-p107">Der Anruftyp, der als sekundäres Vergleichselement verwendet werden soll. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="25e24-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="25e24-152">Alle</span><span class="sxs-lookup"><span data-stu-id="25e24-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="25e24-153">Extern</span><span class="sxs-lookup"><span data-stu-id="25e24-153">External</span></span></p></li>
<li><p><span data-ttu-id="25e24-154">Intern</span><span class="sxs-lookup"><span data-stu-id="25e24-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="25e24-155">VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-156">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-157">Wired</span><span class="sxs-lookup"><span data-stu-id="25e24-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-158">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="25e24-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="25e24-159">Extern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="25e24-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-160">Extern und Funk</span><span class="sxs-lookup"><span data-stu-id="25e24-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="25e24-161">Extern und VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-162">Extern und Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="25e24-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="25e24-163">Intern und verkabelt</span><span class="sxs-lookup"><span data-stu-id="25e24-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="25e24-164">Intern und Funk</span><span class="sxs-lookup"><span data-stu-id="25e24-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-165"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-p108">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="25e24-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="25e24-168">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="25e24-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="25e24-169">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="25e24-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="25e24-170">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="25e24-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="25e24-p109">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="25e24-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="25e24-173">Metriken</span><span class="sxs-lookup"><span data-stu-id="25e24-173">Metrics</span></span>

<span data-ttu-id="25e24-174">In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht über die Medienqualität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25e24-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="25e24-175">Metriken im Bericht über die Medienqualität</span><span class="sxs-lookup"><span data-stu-id="25e24-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25e24-176">Name</span><span class="sxs-lookup"><span data-stu-id="25e24-176">Name</span></span></th>
<th><span data-ttu-id="25e24-177">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="25e24-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="25e24-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25e24-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25e24-179"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-180">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-180">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-181">Die Gesamtzahl der Anrufe.</span><span class="sxs-lookup"><span data-stu-id="25e24-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-182"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-183">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-183">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-184">Durchschnittliche Menge an MOS (Mean Opinion Score) Verschlechterung während eines Anrufs erlebt.</span><span class="sxs-lookup"><span data-stu-id="25e24-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="25e24-185">Die Werte für die Verschlechterung können zwischen einem Tiefstwert von 0,0 und einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder niedriger stellt eine akzeptable Beeinträchtigung dar.</span><span class="sxs-lookup"><span data-stu-id="25e24-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="25e24-186">Historisch gesehen wurden mittlere Meinungs Ergebnisse berechnet, indem Benutzer die Qualität eines Anrufs auf einer Skala von 1 bis 5 bewerten ließen.</span><span class="sxs-lookup"><span data-stu-id="25e24-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="25e24-187">Lync Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="25e24-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="25e24-p111">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="25e24-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-190"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-191">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-191">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p112">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="25e24-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-194"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-195">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-195">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p113">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="25e24-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="25e24-p114">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="25e24-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-200"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-201">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-201">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p115">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="25e24-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-205"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-206">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-206">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-207">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="25e24-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="25e24-208">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="25e24-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-209"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-210">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-210">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p117">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="25e24-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25e24-213"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-214">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-214">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p118">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="25e24-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25e24-217"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="25e24-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="25e24-218">Nein</span><span class="sxs-lookup"><span data-stu-id="25e24-218">No</span></span></p></td>
<td><p><span data-ttu-id="25e24-p119">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="25e24-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

