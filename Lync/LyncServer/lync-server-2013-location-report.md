---
title: 'Lync Server 2013: Standortbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac5ab1d077acb8f96849b4ac44911a4c90786fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="deaa5-102">Standortbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deaa5-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deaa5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="deaa5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="deaa5-p101">Der Standortbericht enthält nach dem Netzwerkstandort (also nach dem Netzwerksubnetz) gruppierte Informationen zu Metriken für die Anrufqualität. Falls bei Ihren Benutzern Probleme im Zusammenhang mit Anrufen auftreten, können Sie mithilfe dieses Berichts bestimmen, ob diese Probleme weitverbreitet sind oder ob sie weitgehend auf ein bestimmtes Netzwerksegment beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="deaa5-106">Zugriff auf den Standortbericht</span><span class="sxs-lookup"><span data-stu-id="deaa5-106">Accessing the Location Report</span></span>

<span data-ttu-id="deaa5-p102">Auf den Standortbericht greifen Sie auf der Startseite „Überwachungsberichte“ zu. Sie können einen Drilldown für den Anruflistenbericht ausführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="deaa5-109">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="deaa5-109">Call volume</span></span>

  - <span data-ttu-id="deaa5-110">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="deaa5-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="deaa5-111">Filter</span><span class="sxs-lookup"><span data-stu-id="deaa5-111">Filters</span></span>

<span data-ttu-id="deaa5-112">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="deaa5-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="deaa5-113">Beispielsweise können Sie die Daten im Standortbericht nach Kriterien wie dem Standort, von dem der Anruf stammt, oder der Art der Verbindung (Funk oder Kabel) filtern.</span><span class="sxs-lookup"><span data-stu-id="deaa5-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="deaa5-114">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="deaa5-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="deaa5-115">In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="deaa5-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="deaa5-116">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Standortbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="deaa5-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="deaa5-117">Filter im Standortbericht</span><span class="sxs-lookup"><span data-stu-id="deaa5-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="deaa5-118">Name</span><span class="sxs-lookup"><span data-stu-id="deaa5-118">Name</span></span></th>
<th><span data-ttu-id="deaa5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deaa5-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-120"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p104">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="deaa5-123">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="deaa5-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="deaa5-p105">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="deaa5-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="deaa5-126">7/7/2012</span></span></p>
<p><span data-ttu-id="deaa5-127">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="deaa5-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="deaa5-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="deaa5-128">7/3/2012</span></span></p>
<p><span data-ttu-id="deaa5-129">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="deaa5-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-130"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p106">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="deaa5-133">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="deaa5-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="deaa5-p107">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="deaa5-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="deaa5-136">7/7/2012</span></span></p>
<p><span data-ttu-id="deaa5-137">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="deaa5-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="deaa5-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="deaa5-138">7/3/2012</span></span></p>
<p><span data-ttu-id="deaa5-139">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="deaa5-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-140"><strong>Standort des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p108">Das IP-Subnetz des Benutzers, der den Anruf ausgeführt hat. Sie können nur <strong>[Alle]</strong> auswählen, um alle Subnetze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-143"><strong>Standort des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p109">Das IP-Subnetz des Benutzers, der den Anruf empfangen hat. Sie können nur <strong>[Alle]</strong> auswählen, um alle Subnetze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-146"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p110">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="deaa5-149">[Alle]</span><span class="sxs-lookup"><span data-stu-id="deaa5-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="deaa5-150">Verkabelt</span><span class="sxs-lookup"><span data-stu-id="deaa5-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="deaa5-151">Funk</span><span class="sxs-lookup"><span data-stu-id="deaa5-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="deaa5-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="deaa5-155">[Alle]</span><span class="sxs-lookup"><span data-stu-id="deaa5-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="deaa5-156">VPN</span><span class="sxs-lookup"><span data-stu-id="deaa5-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="deaa5-157">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="deaa5-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="deaa5-158">Metriken</span><span class="sxs-lookup"><span data-stu-id="deaa5-158">Metrics</span></span>

<span data-ttu-id="deaa5-159">In der folgenden Tabelle werden die Metriken aufgelistet, die im Standortbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="deaa5-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="deaa5-160">Metriken im Standortbericht</span><span class="sxs-lookup"><span data-stu-id="deaa5-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="deaa5-161">Name</span><span class="sxs-lookup"><span data-stu-id="deaa5-161">Name</span></span></th>
<th><span data-ttu-id="deaa5-162">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="deaa5-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="deaa5-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deaa5-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-164"><strong>Subnetz des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-165">Nein</span><span class="sxs-lookup"><span data-stu-id="deaa5-165">No</span></span></p></td>
<td><p><span data-ttu-id="deaa5-166">Das IP-Subnetz des Benutzers, der den Anruf ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="deaa5-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-167"><strong>Subnetz des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-168">Nein</span><span class="sxs-lookup"><span data-stu-id="deaa5-168">No</span></span></p></td>
<td><p><span data-ttu-id="deaa5-169">Das IP-Subnetz des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="deaa5-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-170"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-171">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-172">Die Gesamtzahl der getätigten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="deaa5-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-173"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-174">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p112">Der Prozentsatz der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="deaa5-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-177"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-178">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p113">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="deaa5-p114">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-183"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-184">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-185">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="deaa5-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="deaa5-186">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="deaa5-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="deaa5-187">Ein Wert von 0,5 oder weniger gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="deaa5-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="deaa5-188">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="deaa5-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="deaa5-189">In lync Server verwendet lync Server einen Satz von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="deaa5-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="deaa5-p116">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-192"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-193">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p117">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-197"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-198">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-199">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="deaa5-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="deaa5-200">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.</span><span class="sxs-lookup"><span data-stu-id="deaa5-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-201"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-202">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p119">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deaa5-205"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-206">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p120">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deaa5-209"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="deaa5-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="deaa5-210">Ja</span><span class="sxs-lookup"><span data-stu-id="deaa5-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="deaa5-p121">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="deaa5-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

