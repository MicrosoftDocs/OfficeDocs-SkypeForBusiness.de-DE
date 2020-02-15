---
title: 'Lync Server 2013: Bericht über Server Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e60757721a9244a55e7ce341be6834934108858a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="8ee81-102">Bericht über die Server Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ee81-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee81-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8ee81-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8ee81-104">Der Bericht über die Server Leistung enthält eine Liste von Microsoft lync Server 2013 Servern, die den höchsten Prozentsatz armer Anrufe erfahren haben.</span><span class="sxs-lookup"><span data-stu-id="8ee81-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="8ee81-105">Der Bericht führt die Server nach Servertyp auf und bietet separate Statistiken für folgende Typen:</span><span class="sxs-lookup"><span data-stu-id="8ee81-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="8ee81-106">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-106">Mediation Server</span></span>

  - <span data-ttu-id="8ee81-107">A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="8ee81-108">A/V-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-108">A/V Edge Server</span></span>

  - <span data-ttu-id="8ee81-109">Gateway (Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="8ee81-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="8ee81-110">Gateway (Vermittlungsserverumgehung)</span><span class="sxs-lookup"><span data-stu-id="8ee81-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="8ee81-111">Video (einschließlich Videometriken für A/V-Konferenzserver und A/V-Edgeserver)</span><span class="sxs-lookup"><span data-stu-id="8ee81-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="8ee81-112">Anwendungsfreigabe (einschließlich Anwendungsfreigabemetriken für A/V-Konferenzserver und A/V-Edgeserver)</span><span class="sxs-lookup"><span data-stu-id="8ee81-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="8ee81-p102">Es ist wichtig zu beachten, dass es sich bei den in diesem Bericht enthaltenen Rangordnungen um relative Rangordnungen handelt. Wenn Ihr Server mit der schlechtesten Leistung z. B. einen Anruf schlechter Qualität unter 1.000 Anrufen hatte, dann ist das ein sehr akzeptabler Prozentsatz von 0,1 %. Wenn dieser Server jedoch der Server mit der schlechtesten Leistung ist (d. h., alle anderen Server haben einen Prozentsatz an Anrufen schlechter Qualität unter 0,1 %), dann wird der Server weiterhin im Bericht über Serverleistung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="8ee81-117">Zugriff auf den Bericht über Serverleistung</span><span class="sxs-lookup"><span data-stu-id="8ee81-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="8ee81-118">Der Zugriff auf den Bericht über Serverleistung erfolgt auf der Startseite für Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="8ee81-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="8ee81-119">Sie können einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="8ee81-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8ee81-120">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="8ee81-120">Call volume</span></span>

  - <span data-ttu-id="8ee81-121">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="8ee81-121">Poor call percentage</span></span>

<span data-ttu-id="8ee81-122">Außerdem können Sie den Trendbericht über Medienqualität des Servers anzeigen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="8ee81-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="8ee81-123">Trend</span><span class="sxs-lookup"><span data-stu-id="8ee81-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="8ee81-124">Optimale Verwendung des Berichts über Serverleistung</span><span class="sxs-lookup"><span data-stu-id="8ee81-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="8ee81-p104">Der Bericht über Serverleistung bietet verschiedene Möglichkeit, die Daten zu filtern. Sie können z. B. nach Netzwerktyp filtern (Anrufe über eine Kabelverbindung im Vergleich zu Anrufen über eine kabellose Verbindung) und nach Zugriffstyp (Anrufe, die von innerhalb der Firewall getätigt wurden im Vergleich zu Anrufen von außerhalb der Firewall). Es ist sinnvoll, diese Filter bei der Auswertung des Berichts über Serverleistung zu nutzen. Beispiel: Angenommen, Sie haben einen Vermittlungsserver, der einen Prozentsatz an Anrufen schlechter Qualität von 3,24 % hat. Wenn Sie sich nur die Funkanrufe ansehen, dann hat derselbe Server einen Prozentsatz an Anrufen schlechter Qualität von fast 20 %. Dies bedeutet, dass der Server Probleme mit Funkanrufen hat, was teilweise dadurch verschleiert wurde, dass der Server keine Probleme mit Kabelanrufen hat.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8ee81-130">Filter</span><span class="sxs-lookup"><span data-stu-id="8ee81-130">Filters</span></span>

<span data-ttu-id="8ee81-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Bericht über Serverleistung die zurückgegebenen Daten nach Kriterien wie etwa Servertyp oder Netzwerktyp (d. h. Kabel oder Funk) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Daten nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8ee81-135">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Serverleistung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8ee81-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="8ee81-136">Filter im Bericht über Serverleistung</span><span class="sxs-lookup"><span data-stu-id="8ee81-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee81-137">Name</span><span class="sxs-lookup"><span data-stu-id="8ee81-137">Name</span></span></th>
<th><span data-ttu-id="8ee81-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ee81-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8ee81-142">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="8ee81-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8ee81-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8ee81-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8ee81-145">7/7/2012</span></span></p>
<p><span data-ttu-id="8ee81-146">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="8ee81-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8ee81-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8ee81-147">7/3/2012</span></span></p>
<p><span data-ttu-id="8ee81-148">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="8ee81-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-149"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8ee81-152">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="8ee81-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8ee81-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8ee81-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8ee81-155">7/7/2012</span></span></p>
<p><span data-ttu-id="8ee81-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="8ee81-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8ee81-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8ee81-157">7/3/2012</span></span></p>
<p><span data-ttu-id="8ee81-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="8ee81-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-159"><strong>Servertyp</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p110">Gibt den Typ des Servers an, über dessen Leistung ein Bericht erstellt werden soll. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8ee81-162">Alle</span><span class="sxs-lookup"><span data-stu-id="8ee81-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="8ee81-163">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="8ee81-164">A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8ee81-165">A/V-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8ee81-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-166"><strong>Top N</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p111">Gibt die Anzahl der Server an (basierend auf dem Prozentsatz der Anrufe schlechter Qualität), die in den einzelnen Kategorien angezeigt werden sollen. Wenn Sie z. B. <strong>5</strong> auswählen, werden die fünf Server mit der schlechtesten Leistung angezeigt. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8ee81-170">Alle</span><span class="sxs-lookup"><span data-stu-id="8ee81-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="8ee81-171">5 </span><span class="sxs-lookup"><span data-stu-id="8ee81-171">5</span></span></p></li>
<li><p><span data-ttu-id="8ee81-172">10 </span><span class="sxs-lookup"><span data-stu-id="8ee81-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-173"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p112">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8ee81-176">Alle</span><span class="sxs-lookup"><span data-stu-id="8ee81-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="8ee81-177">Intern</span><span class="sxs-lookup"><span data-stu-id="8ee81-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="8ee81-178">Extern</span><span class="sxs-lookup"><span data-stu-id="8ee81-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-179"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p113">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8ee81-182">Alle</span><span class="sxs-lookup"><span data-stu-id="8ee81-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="8ee81-183">Wired</span><span class="sxs-lookup"><span data-stu-id="8ee81-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="8ee81-184">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="8ee81-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-p114">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8ee81-188">Alle</span><span class="sxs-lookup"><span data-stu-id="8ee81-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="8ee81-189">VPN</span><span class="sxs-lookup"><span data-stu-id="8ee81-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="8ee81-190">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="8ee81-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8ee81-191">Metriken</span><span class="sxs-lookup"><span data-stu-id="8ee81-191">Metrics</span></span>

<span data-ttu-id="8ee81-192">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Serverleistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8ee81-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="8ee81-193">Metriken im Bericht über Serverleistung: Zusammenfassung der Audioanrufe</span><span class="sxs-lookup"><span data-stu-id="8ee81-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee81-194">Name</span><span class="sxs-lookup"><span data-stu-id="8ee81-194">Name</span></span></th>
<th><span data-ttu-id="8ee81-195">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="8ee81-195">Can Sort On</span></span></th>
<th><span data-ttu-id="8ee81-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ee81-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-197"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-198">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-198">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-199">Name/IP-Adresse des Servers.</span><span class="sxs-lookup"><span data-stu-id="8ee81-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-200"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-201">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-201">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-202">Gesamtzahl der ausgeführten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="8ee81-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-203"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-204">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-204">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p115">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="8ee81-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-207"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-208">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p116">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8ee81-p117">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-213"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-214">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-215">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="8ee81-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="8ee81-216">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="8ee81-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="8ee81-217">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="8ee81-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="8ee81-218">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="8ee81-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="8ee81-219">In lync Server verwendet der Monitoring Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="8ee81-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="8ee81-p119">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-222"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-223">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p120">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-227"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-228">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-229">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8ee81-230">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="8ee81-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-231"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-232">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p122">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-235"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-236">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p123">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-239"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-240">Ja</span><span class="sxs-lookup"><span data-stu-id="8ee81-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p124">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="8ee81-243">Metriken im Bericht über Serverleistung: Zusammenfassung der Videoanrufe</span><span class="sxs-lookup"><span data-stu-id="8ee81-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee81-244">Name</span><span class="sxs-lookup"><span data-stu-id="8ee81-244">Name</span></span></th>
<th><span data-ttu-id="8ee81-245">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="8ee81-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8ee81-246">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ee81-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-247"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-248">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-248">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p125">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ee81-251">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="8ee81-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="8ee81-252">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="8ee81-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8ee81-253">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="8ee81-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8ee81-254">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="8ee81-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="8ee81-255">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ee81-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="8ee81-256">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ee81-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="8ee81-257">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="8ee81-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-258"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-259">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-259">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-260">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="8ee81-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-261"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-262">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-262">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p126">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="8ee81-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-265"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-266">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-266">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-267">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-268"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-269">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-269">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-270">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-271"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-272">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-272">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-273">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="8ee81-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-274"><strong>Durchschnittliche Bitrate (KBit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-275">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-275">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-276">Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="8ee81-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-277"><strong>Niedrige Bitrate %</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-278">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-278">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-279">Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.</span><span class="sxs-lookup"><span data-stu-id="8ee81-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-280"><strong>Verlust ausgehender Pakete</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-281">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-281">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p127">RTP-Paketverluste (Real-Time Transport Protocol; ein Protokoll für die Übertragung von Audio und Video über das Internet) für ausgehende Pakete. Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-285"><strong>Eingefrorene Frames %</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-286">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-286">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p128">Prozentsatz der "eingefrorenen" Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-289"><strong>Durchschnittliche ausgehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-290">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-290">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-291">Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="8ee81-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-292"><strong>Durchschnittliche eingehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-293">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-293">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-294">Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="8ee81-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-295"><strong>Niedrige eingehende Framerate %</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-296">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-296">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-297">Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.</span><span class="sxs-lookup"><span data-stu-id="8ee81-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-298"><strong>Clientintegrität %</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ee81-299">Zeigt die relative Integrität des Clientgeräts während des Anrufs an.</span><span class="sxs-lookup"><span data-stu-id="8ee81-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="8ee81-300">Metriken im Bericht über Serverleistung: Zusammenfassung der Anwendungsfreigabeanrufe</span><span class="sxs-lookup"><span data-stu-id="8ee81-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee81-301">Name</span><span class="sxs-lookup"><span data-stu-id="8ee81-301">Name</span></span></th>
<th><span data-ttu-id="8ee81-302">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="8ee81-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8ee81-303">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ee81-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-304"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-305">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-305">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p129">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="8ee81-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ee81-308">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="8ee81-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="8ee81-309">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="8ee81-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8ee81-310">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="8ee81-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8ee81-311">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="8ee81-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="8ee81-312">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ee81-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="8ee81-313">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ee81-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="8ee81-314">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="8ee81-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-315"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-316">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-316">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-317">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="8ee81-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-318"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-319">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-319">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p130">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="8ee81-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-322"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-323">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-323">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-324">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-325"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-326">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-326">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-327">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-328"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-329">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-329">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-330">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="8ee81-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-331"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-332">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-332">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-333">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee81-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8ee81-334">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="8ee81-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-335"><strong>Durchschnitt relativ unidirektional</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-336">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-336">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p132">Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee81-339"><strong>Durchschnittliche Latenz der RDP-Kachelverarbeitung</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-340">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-340">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-p133">Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung. Diese Metrik deckt die Netzwerklatenz nicht ab. Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</span><span class="sxs-lookup"><span data-stu-id="8ee81-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee81-345"><strong>Insgesamt schlechte Kacheln %</strong></span><span class="sxs-lookup"><span data-stu-id="8ee81-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="8ee81-346">Nein</span><span class="sxs-lookup"><span data-stu-id="8ee81-346">No</span></span></p></td>
<td><p><span data-ttu-id="8ee81-347">Gesamtprozentsatz schlechter RDP-Kacheln.</span><span class="sxs-lookup"><span data-stu-id="8ee81-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

