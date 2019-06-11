---
title: 'Lync Server 2013: Peer-to-Peer-sprach-und Video Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="92dff-102">Peer-zu-Peer-sprach-und Video Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92dff-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92dff-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="92dff-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="92dff-p101">Der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität bietet eine detaillierte Aufstellung der Sprach- und -Videoanrufe für einen bestimmten Zeitraum (z. B. Anrufe pro Stunde oder Anrufe pro Tag). Darüber hinaus können Sie mit diesem Bericht alle getätigten Sprach- und Videoanrufe oder aber nur die erfolgreichen bzw. fehlgeschlagenen Anrufe anzeigen. In diesem Bericht werden die Anrufinformationen in den folgenden Kategorien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="92dff-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="92dff-107">Anrufe pro Pool</span><span class="sxs-lookup"><span data-stu-id="92dff-107">Calls per pool</span></span>

  - <span data-ttu-id="92dff-108">Anrufe pro Anruftyp (beispielsweise ein lync-zu-lync-Anruf im Vergleich zu einem lync-Anruf an eine Person im PSTN-Netzwerk)</span><span class="sxs-lookup"><span data-stu-id="92dff-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="92dff-109">Anrufe pro Zugriffstyp (beim internen Netzwerk angemeldete Benutzer bzw. beim externen Netzwerk angemeldete Benutzer)</span><span class="sxs-lookup"><span data-stu-id="92dff-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="92dff-110">Anrufe pro Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="92dff-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="92dff-111">So greifen Sie auf den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität zu</span><span class="sxs-lookup"><span data-stu-id="92dff-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="92dff-112">Auf den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität können Sie nur zugreifen, indem Sie den zusammenfassenden Bericht über Peer-to-Peer-Aktivität öffnen und dann auf die folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="92dff-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="92dff-113">Peer-to-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="92dff-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="92dff-114">Gesamtdauer der Peer-to-Peer-Audiositzungen in Minuten</span><span class="sxs-lookup"><span data-stu-id="92dff-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="92dff-115">Peer-to-Peer-Videositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="92dff-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="92dff-116">Gesamtdauer der Peer-to-Peer-Videositzungen in Minuten</span><span class="sxs-lookup"><span data-stu-id="92dff-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="92dff-117">So nutzen Sie den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität optimal</span><span class="sxs-lookup"><span data-stu-id="92dff-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="92dff-p102">Es gibt eine Reihe von Möglichkeiten, um den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität zu filtern. Diese Filteroptionen sind jedoch standardmäßig ausgeblendet. Klicken Sie zum Anzeigen der verfügbaren Filteroptionen auf die Schaltfläche **Parameter ein-/ausblenden** in der oberen rechten Ecke des Berichtfensters.</span><span class="sxs-lookup"><span data-stu-id="92dff-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="92dff-121">Filter</span><span class="sxs-lookup"><span data-stu-id="92dff-121">Filters</span></span>

<span data-ttu-id="92dff-p103">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="92dff-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="92dff-124">Filter im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität</span><span class="sxs-lookup"><span data-stu-id="92dff-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92dff-125">Name</span><span class="sxs-lookup"><span data-stu-id="92dff-125">Name</span></span></th>
<th><span data-ttu-id="92dff-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92dff-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92dff-127"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p104">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="92dff-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="92dff-130">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="92dff-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="92dff-p105">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="92dff-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="92dff-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="92dff-133">7/7/2012</span></span></p>
<p><span data-ttu-id="92dff-134">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="92dff-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="92dff-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="92dff-135">7/3/2012</span></span></p>
<p><span data-ttu-id="92dff-136">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="92dff-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-137"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p106">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="92dff-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="92dff-140">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="92dff-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="92dff-p107">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="92dff-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="92dff-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="92dff-143">7/7/2012</span></span></p>
<p><span data-ttu-id="92dff-144">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="92dff-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="92dff-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="92dff-145">7/3/2012</span></span></p>
<p><span data-ttu-id="92dff-146">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="92dff-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-147"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p108">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="92dff-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-150">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="92dff-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="92dff-151">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="92dff-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="92dff-152">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="92dff-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="92dff-153">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="92dff-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="92dff-154">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92dff-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="92dff-155">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="92dff-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-156"><strong>Medientyp</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p110">Gibt den Typ der in der Sitzung verwendeten Medien an. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="92dff-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-159">Both</span><span class="sxs-lookup"><span data-stu-id="92dff-159">Both</span></span></p></li>
<li><p><span data-ttu-id="92dff-160">Audio</span><span class="sxs-lookup"><span data-stu-id="92dff-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="92dff-161">Video</span><span class="sxs-lookup"><span data-stu-id="92dff-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-162"><strong>Anrufanordnung</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p111">Gibt an, ob die Sitzung erfolgreich oder fehlerhaft war. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="92dff-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-165">[Alle]</span><span class="sxs-lookup"><span data-stu-id="92dff-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="92dff-166">Erfolgreiche Anrufe</span><span class="sxs-lookup"><span data-stu-id="92dff-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="92dff-167">Fehlerhafte Anrufe</span><span class="sxs-lookup"><span data-stu-id="92dff-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-168"><strong>Bericht nach</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-p112">Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="92dff-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-171">Sitzungsanzahl</span><span class="sxs-lookup"><span data-stu-id="92dff-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="92dff-172">Anrufminuten</span><span class="sxs-lookup"><span data-stu-id="92dff-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="92dff-173">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Pool</span><span class="sxs-lookup"><span data-stu-id="92dff-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="92dff-174">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Pool angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92dff-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="92dff-175">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Pool</span><span class="sxs-lookup"><span data-stu-id="92dff-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92dff-176">Name</span><span class="sxs-lookup"><span data-stu-id="92dff-176">Name</span></span></th>
<th><span data-ttu-id="92dff-177">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="92dff-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="92dff-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92dff-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92dff-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-180">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-180">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-181">Name des registrierungspools oder des Edge-Servers, der für den Anruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="92dff-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-182"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-183">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-183">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-184">Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</span><span class="sxs-lookup"><span data-stu-id="92dff-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-185"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-186">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-186">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-187">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="92dff-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="92dff-188">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Anruftyp</span><span class="sxs-lookup"><span data-stu-id="92dff-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="92dff-189">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Anruftyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92dff-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="92dff-190">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Anruftyp</span><span class="sxs-lookup"><span data-stu-id="92dff-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92dff-191">Name</span><span class="sxs-lookup"><span data-stu-id="92dff-191">Name</span></span></th>
<th><span data-ttu-id="92dff-192">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="92dff-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="92dff-193">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92dff-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92dff-194"><strong>Anruftyp</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-195">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-195">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-p113">Gibt den Typ des Anrufs an, der ausgeführt wurde. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="92dff-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-198">UC-zu-UC</span><span class="sxs-lookup"><span data-stu-id="92dff-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="92dff-199">UC-zu-PSTN</span><span class="sxs-lookup"><span data-stu-id="92dff-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="92dff-200">PSTN-zu-UC</span><span class="sxs-lookup"><span data-stu-id="92dff-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="92dff-201">PSTN-zu-PSTN</span><span class="sxs-lookup"><span data-stu-id="92dff-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-202"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-203">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-203">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-204">Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</span><span class="sxs-lookup"><span data-stu-id="92dff-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-205"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-206">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-206">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-207">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="92dff-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="92dff-208">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Zugriffstyp</span><span class="sxs-lookup"><span data-stu-id="92dff-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="92dff-209">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Netzwerkzugriffstyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92dff-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="92dff-210">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Zugriffstyp</span><span class="sxs-lookup"><span data-stu-id="92dff-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92dff-211">Name</span><span class="sxs-lookup"><span data-stu-id="92dff-211">Name</span></span></th>
<th><span data-ttu-id="92dff-212">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="92dff-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="92dff-213">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92dff-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92dff-214"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-215">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-215">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-p114">Gibt an, ob die Clients am internen oder am externen Netzwerk angemeldet wurden, als der Anruf getätigt wurde. Diese Metrik hat normalerweise einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="92dff-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="92dff-218">Intern</span><span class="sxs-lookup"><span data-stu-id="92dff-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="92dff-219">Extern</span><span class="sxs-lookup"><span data-stu-id="92dff-219">External</span></span></p></li>
<li><p><span data-ttu-id="92dff-220">Gemischt</span><span class="sxs-lookup"><span data-stu-id="92dff-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-221"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-222">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-222">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-223">Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</span><span class="sxs-lookup"><span data-stu-id="92dff-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-224"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-225">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-225">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-226">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="92dff-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="92dff-227">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="92dff-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="92dff-228">In der folgenden Tabelle sind die Informationen aufgeführt, die im Peer-to-Peer-sprach-und Video Bericht für jeden Vermittlungs Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="92dff-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="92dff-229">Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="92dff-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92dff-230">Name</span><span class="sxs-lookup"><span data-stu-id="92dff-230">Name</span></span></th>
<th><span data-ttu-id="92dff-231">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="92dff-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="92dff-232">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92dff-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92dff-233"><strong>Vermittlungsserver</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-234">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-234">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-235">Der Name des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="92dff-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92dff-236"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-237">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-237">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-238">Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</span><span class="sxs-lookup"><span data-stu-id="92dff-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92dff-239"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="92dff-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="92dff-240">Nein</span><span class="sxs-lookup"><span data-stu-id="92dff-240">No</span></span></p></td>
<td><p><span data-ttu-id="92dff-241">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="92dff-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

