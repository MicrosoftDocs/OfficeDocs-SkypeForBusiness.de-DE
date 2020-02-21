---
title: 'Lync Server 2013: Trend Bericht über Server Medienqualität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e7e0f3cfe38a7a1c4802eca16c37a62013cecb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="3cf8a-102">Trend Bericht über Server Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cf8a-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf8a-103">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="3cf8a-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="3cf8a-104">Der Trend Bericht über die Server Medienqualität bietet Ihnen die Möglichkeit, bis zu fünf Server mit Metriken für die Qualität der Erfahrung, wie Anrufvolumen, Anruf Prozentsatz, Paketverlust und Jitter, grafisch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="3cf8a-105">Dies erleichtert die Ermittlung von Servern, die schlecht ausgeführt werden, Identifizieren von Servern, die nicht ausgelastet sind, oder identifizieren von Servern, die überlastet sind.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="3cf8a-106">Zugriff auf den Trend Bericht über Medienqualität für Server</span><span class="sxs-lookup"><span data-stu-id="3cf8a-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="3cf8a-107">Auf den Trend Bericht über Server Medienqualität kann über einen der folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="3cf8a-108">[Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Trend Metrik)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="3cf8a-109">[Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) (durch Klicken auf die Metrik A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="3cf8a-110">Wenn es sich bei dem Anrufer oder angerufenen um einen Server handelt, können Sie auch den Medien Trend Bericht über Serverqualität erreichen, indem Sie auf den Endpunktnamen klicken.)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="3cf8a-111">Optimale Verwendung des Trend Berichts über Medienqualität in einem Server</span><span class="sxs-lookup"><span data-stu-id="3cf8a-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="3cf8a-112">Wenn Sie im [Bericht über Serverleistung in lync Server 2013](lync-server-2013-server-performance-report.md) für einen bestimmten Server auf die Trend Metrik klicken, wird der Trendbericht über die Medienqualität von Servern geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="3cf8a-113">Es wird jedoch nur eine leere Instanz dieses Berichts angezeigt. der Server, den Sie im Bericht über Serverleistung ausgewählt haben, wird nicht auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="3cf8a-114">Stattdessen müssen Sie diesen Server aus der Dropdownliste Server auswählen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="3cf8a-115">Beachten Sie auch, dass die Dropdownliste Server eine Option Alle auswählen enthält.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="3cf8a-116">Diese Option ist nicht funktionsfähig, wenn Sie über mehr als 5 Server verfügen. der Trend Bericht "Server Medienqualität" kann nur Daten für maximal 5 Server gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="3cf8a-117">Auf den vom Server Medienqualität-Trend Bericht angezeigten Diagrammen sind die Punkte Anruflautstärke und Prozentsatz armer Anrufe Hotlinks; Wenn Sie auf einen Punkt im Diagramm klicken, wird eine Instanz des [Anruflisten Berichts in lync Server 2013](lync-server-2013-call-list-report.md) angezeigt, in der die Gesamtzahl der Anrufe (oder schlechte Anrufe) für den angegebenen Zeitraum angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3cf8a-118">Filter</span><span class="sxs-lookup"><span data-stu-id="3cf8a-118">Filters</span></span>

<span data-ttu-id="3cf8a-119">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3cf8a-120">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Trend Bericht über Medienqualität für Server verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="3cf8a-121">Trend Berichtsfilter für Server Medienqualität</span><span class="sxs-lookup"><span data-stu-id="3cf8a-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cf8a-122">Name</span><span class="sxs-lookup"><span data-stu-id="3cf8a-122">Name</span></span></th>
<th><span data-ttu-id="3cf8a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cf8a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3cf8a-127">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="3cf8a-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3cf8a-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3cf8a-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3cf8a-130">7/7/2012</span></span></p>
<p><span data-ttu-id="3cf8a-131">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="3cf8a-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3cf8a-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3cf8a-132">7/3/2012</span></span></p>
<p><span data-ttu-id="3cf8a-133">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-134"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3cf8a-137">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="3cf8a-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3cf8a-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3cf8a-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3cf8a-140">7/7/2012</span></span></p>
<p><span data-ttu-id="3cf8a-141">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="3cf8a-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3cf8a-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3cf8a-142">7/3/2012</span></span></p>
<p><span data-ttu-id="3cf8a-143">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-144"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p109">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cf8a-147">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-148">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-149">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="3cf8a-p110">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-152"><strong>Servertyp</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-153">Der Typ des Servers, der an dem Anruf beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-153">Type of server involved in the call.</span></span> <span data-ttu-id="3cf8a-154">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cf8a-155">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="3cf8a-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-156">A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="3cf8a-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-157">A/V-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="3cf8a-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-158">Gateway (Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-159">Gateway (Vermittlungsserver Umgehung)</span><span class="sxs-lookup"><span data-stu-id="3cf8a-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-160">Als Konferenz Server</span><span class="sxs-lookup"><span data-stu-id="3cf8a-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-161"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-162">Name des Servers, der an der Sitzung beteiligt ist; diese Dropdownliste wird basierend auf dem Wert des Servertyp Filters automatisch aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="3cf8a-163">Sie können bis zu fünf verschiedene Server auswählen, wenn Sie einen Bericht kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-164"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-165">Gibt an, ob der Teilnehmer am internen Netzwerk oder über das externe Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="3cf8a-166">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cf8a-167">Alle</span><span class="sxs-lookup"><span data-stu-id="3cf8a-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-168">Intern</span><span class="sxs-lookup"><span data-stu-id="3cf8a-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-169">Extern</span><span class="sxs-lookup"><span data-stu-id="3cf8a-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-170"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-171">Gibt den Typ des Netzwerks an, mit dem der Teilnehmer verbunden war.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="3cf8a-172">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cf8a-173">Alle</span><span class="sxs-lookup"><span data-stu-id="3cf8a-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-174">Wired</span><span class="sxs-lookup"><span data-stu-id="3cf8a-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-175">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="3cf8a-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-177">Gibt an, ob ein externer Teilnehmer während der Sitzung eine VPN-Verbindung (Virtual Private Network) verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="3cf8a-178">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3cf8a-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cf8a-179">Alle</span><span class="sxs-lookup"><span data-stu-id="3cf8a-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-180">VPN</span><span class="sxs-lookup"><span data-stu-id="3cf8a-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="3cf8a-181">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="3cf8a-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3cf8a-182">Metriken</span><span class="sxs-lookup"><span data-stu-id="3cf8a-182">Metrics</span></span>

<span data-ttu-id="3cf8a-183">In der folgenden Tabelle sind die Informationen aufgeführt, die im Trend Bericht über Medienqualität für Server angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="3cf8a-184">Metriken für den Trend Berichts Server Medienqualität</span><span class="sxs-lookup"><span data-stu-id="3cf8a-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cf8a-185">Name</span><span class="sxs-lookup"><span data-stu-id="3cf8a-185">Name</span></span></th>
<th><span data-ttu-id="3cf8a-186">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="3cf8a-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3cf8a-187">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cf8a-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-188"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-189">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-189">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-190">Die Gesamtzahl der Anrufe.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-191"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-192">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-192">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-193">Durchschnittliche Anzahl von MOS-Einbußen (Mittleres Options Ergebnis), die während eines Anrufs erlitten haben.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="3cf8a-194">Die Werte für die Verschlechterung können zwischen einem Tiefstwert von 0,0 und einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder niedriger stellt eine akzeptable Beeinträchtigung dar.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3cf8a-195">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3cf8a-196">Lync Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3cf8a-p117">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-199"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-200">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-200">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p118">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-203"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-204">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-204">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-205">Durchschnittliche Zeit (in Millisekunden), die für ein Transport Protokoll Paket in Echtzeit erforderlich ist, um an einen Endpunkt und dann zurück zu reisen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="3cf8a-206">Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3cf8a-p120">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-209"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-210">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-210">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p121">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-214"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-215">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-215">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-216">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3cf8a-217">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-218"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-219">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-219">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p123">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf8a-222"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-223">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-223">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p124">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf8a-226"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="3cf8a-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3cf8a-227">Nein</span><span class="sxs-lookup"><span data-stu-id="3cf8a-227">No</span></span></p></td>
<td><p><span data-ttu-id="3cf8a-p125">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="3cf8a-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

