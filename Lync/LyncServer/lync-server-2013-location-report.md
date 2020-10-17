---
title: 'Lync Server 2013: Standortbericht'
description: 'Lync Server 2013: Standortbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b819bcffeee0795cd39d3dde3e38fbd9e4a1b7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569471"
---
# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="2d369-103">Standortbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d369-103">Location Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d369-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2d369-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2d369-105">Der Standortbericht enthält Informationen zu Metriken für die Anrufqualität, gruppiert nach dem Netzwerkspeicherort (im Netzwerk-Subnetz).</span><span class="sxs-lookup"><span data-stu-id="2d369-105">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="2d369-106">Wenn Ihre Benutzer Probleme mit ihren anrufen haben, kann dieser Bericht Ihnen helfen zu ermitteln, ob diese Probleme weit verbreitet sind oder ob Sie weitgehend auf ein bestimmtes Netzwerksegment beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="2d369-106">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="2d369-107">Zugreifen auf den Standortbericht</span><span class="sxs-lookup"><span data-stu-id="2d369-107">Accessing the Location Report</span></span>

<span data-ttu-id="2d369-108">Auf den Standortbericht kann über die Startseite für Überwachungsberichte zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2d369-108">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2d369-109">Sie können den Call List Report anzeigen lassen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="2d369-109">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2d369-110">Anrufvolumen</span><span class="sxs-lookup"><span data-stu-id="2d369-110">Call volume</span></span>

  - <span data-ttu-id="2d369-111">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="2d369-111">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2d369-112">Filter</span><span class="sxs-lookup"><span data-stu-id="2d369-112">Filters</span></span>

<span data-ttu-id="2d369-113">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d369-113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2d369-114">Beispielsweise können Sie mit dem Standortbericht nach Dingen suchen, die den Standort haben, an dem ein Anruf entstanden ist, oder ob der Anruf über eine drahtlose oder eine kabelgebundene Verbindung stattfand.</span><span class="sxs-lookup"><span data-stu-id="2d369-114">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="2d369-115">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d369-115">You can also choose how data should be grouped.</span></span> <span data-ttu-id="2d369-116">In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2d369-116">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2d369-117">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Standortbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2d369-117">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="2d369-118">Standort Berichtsfilter</span><span class="sxs-lookup"><span data-stu-id="2d369-118">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d369-119">Name</span><span class="sxs-lookup"><span data-stu-id="2d369-119">Name</span></span></th>
<th><span data-ttu-id="2d369-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d369-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d369-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-p104">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="2d369-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2d369-124">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="2d369-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d369-p105">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="2d369-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d369-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d369-127">7/7/2012</span></span></p>
<p><span data-ttu-id="2d369-128">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="2d369-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d369-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d369-129">7/3/2012</span></span></p>
<p><span data-ttu-id="2d369-130">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="2d369-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-131"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-p106">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="2d369-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2d369-134">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="2d369-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d369-p107">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="2d369-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d369-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d369-137">7/7/2012</span></span></p>
<p><span data-ttu-id="2d369-138">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="2d369-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d369-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d369-139">7/3/2012</span></span></p>
<p><span data-ttu-id="2d369-140">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="2d369-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-141"><strong>Speicherort des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-141"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-142">IP-Subnetz des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="2d369-142">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="2d369-143">Sie können nur <strong>[alle]</strong> auswählen, um alle Subnetze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d369-143">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-144"><strong>Speicherort des angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-144"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-145">IP-Subnetz des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="2d369-145">IP subnet of the user who received the call.</span></span> <span data-ttu-id="2d369-146">Sie können nur <strong>[alle]</strong> auswählen, um alle Subnetze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d369-146">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-147"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-147"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-p110">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="2d369-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="2d369-150">Alle</span><span class="sxs-lookup"><span data-stu-id="2d369-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="2d369-151">Wired</span><span class="sxs-lookup"><span data-stu-id="2d369-151">Wired</span></span></p></li>
<li><p><span data-ttu-id="2d369-152">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="2d369-152">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-153"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-153"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="2d369-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="2d369-156">Alle</span><span class="sxs-lookup"><span data-stu-id="2d369-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="2d369-157">VPN</span><span class="sxs-lookup"><span data-stu-id="2d369-157">VPN</span></span></p></li>
<li><p><span data-ttu-id="2d369-158">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="2d369-158">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2d369-159">Metriken</span><span class="sxs-lookup"><span data-stu-id="2d369-159">Metrics</span></span>

<span data-ttu-id="2d369-160">In der folgenden Tabelle sind die Informationen aufgeführt, die im Standortbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d369-160">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="2d369-161">Metriken für den Standortbericht</span><span class="sxs-lookup"><span data-stu-id="2d369-161">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d369-162">Name</span><span class="sxs-lookup"><span data-stu-id="2d369-162">Name</span></span></th>
<th><span data-ttu-id="2d369-163">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="2d369-163">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d369-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d369-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d369-165"><strong>Subnetz des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-165"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-166">Nein</span><span class="sxs-lookup"><span data-stu-id="2d369-166">No</span></span></p></td>
<td><p><span data-ttu-id="2d369-167">IP-Subnetz des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="2d369-167">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-168"><strong>Subnetz des angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-168"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-169">Nein</span><span class="sxs-lookup"><span data-stu-id="2d369-169">No</span></span></p></td>
<td><p><span data-ttu-id="2d369-170">IP-Subnetz des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="2d369-170">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-171"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-171"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-172">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-172">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-173">Die Gesamtzahl der getätigten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="2d369-173">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-174"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-174"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-175">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-176">Prozentsatz der Anrufe, die als schlechte Anrufe klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="2d369-176">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="2d369-177">Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="2d369-177">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-178"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-178"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-179">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-p113">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="2d369-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2d369-p114">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="2d369-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-184"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-184"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-185">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-185">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-186">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="2d369-186">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2d369-187">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="2d369-187">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2d369-188">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="2d369-188">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2d369-189">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="2d369-189">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2d369-190">In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="2d369-190">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2d369-p116">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2d369-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-193"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-193"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-194">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-194">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-p117">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2d369-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-198"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-198"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-199">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-200">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d369-200">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2d369-201">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="2d369-201">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-202"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-202"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-203">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-p119">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2d369-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d369-206"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-206"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-207">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-p120">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="2d369-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d369-210"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2d369-210"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d369-211">Ja</span><span class="sxs-lookup"><span data-stu-id="2d369-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d369-p121">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="2d369-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

