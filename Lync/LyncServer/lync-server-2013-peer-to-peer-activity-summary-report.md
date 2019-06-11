---
title: 'Lync Server 2013: Zusammenfassungsbericht für Peer-zu-Peer-Aktivitäten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="0e034-102">Zusammenfassungsbericht zur Peer-zu-Peer-Aktivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e034-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e034-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0e034-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0e034-104">Der zusammenfassende Bericht über Peer-to-Peer-Aktivität bietet eine Übersicht über Peer-to-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="0e034-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="0e034-105">Eine Peer-to-Peer-Sitzung umfasst in der Regel nur zwei Benutzer und erfordert keine Verwendung der lync Server-Konferenzdienste.</span><span class="sxs-lookup"><span data-stu-id="0e034-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="0e034-106">Im Vergleich dazu umfasst eine Konferenz in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Microsoft lync Server 2013-Konferenzdiensten.</span><span class="sxs-lookup"><span data-stu-id="0e034-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="0e034-107">Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="0e034-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="0e034-108">Der zusammenfassende Bericht über Peer-to-Peer-Aktivität hilft Ihnen bei der Beantwortung der folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="0e034-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="0e034-109">Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem normalen Tag?</span><span class="sxs-lookup"><span data-stu-id="0e034-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="0e034-110">Nutzen alle meine Benutzer tatsächlich die Vorteile der lync Server-Anwendungsfreigabe und der Dateiübertragungsfunktionen?</span><span class="sxs-lookup"><span data-stu-id="0e034-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="0e034-p102">Die Benutzer haben sich darüber beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam ist. Wie viele Minuten werden in diesen Zeiten für Peer-to-Peer-Audio-/Videositzungen aufgewendet?</span><span class="sxs-lookup"><span data-stu-id="0e034-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="0e034-113">Zugriff auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0e034-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="0e034-114">Auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität greifen Sie über die Startseite für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="0e034-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="0e034-115">Sie öffnen den [Peer-zu-Peer-Chat Bericht in lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="0e034-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0e034-116">Peer-to-Peer-Chatsitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="0e034-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="0e034-117">Peer-to-Peer-Chatnachrichten insgesamt</span><span class="sxs-lookup"><span data-stu-id="0e034-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="0e034-118">Entsprechend können Sie den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität öffnen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="0e034-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="0e034-119">Peer-to-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="0e034-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="0e034-120">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="0e034-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="0e034-121">Peer-to-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="0e034-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="0e034-122">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="0e034-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="0e034-123">Optimale Nutzung des zusammenfassenden Berichts über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0e034-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="0e034-p104">Im unteren Bereich des zusammenfassenden Berichts über Peer-to-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie z. B. „Peer-to-Peer-Chatsitzungen insgesamt“ und „Peer-to-Peer-Chatnachrichten insgesamt“. Dies ermöglicht einen schnellen Überblick über die detaillierten Informationen im eigentlichen Bericht.</span><span class="sxs-lookup"><span data-stu-id="0e034-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0e034-126">Filter</span><span class="sxs-lookup"><span data-stu-id="0e034-126">Filters</span></span>

<span data-ttu-id="0e034-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem zusammenfassenden Bericht über Peer-to-Peer-Aktivität können Sie beispielsweise wählen, wie Daten gruppiert werden sollen. In diesem Fall werden die Aktivitäten nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="0e034-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0e034-130">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0e034-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="0e034-131">Filter im zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0e034-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e034-132">Name</span><span class="sxs-lookup"><span data-stu-id="0e034-132">Name</span></span></th>
<th><span data-ttu-id="0e034-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e034-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e034-134"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="0e034-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0e034-137">7/17/12012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="0e034-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0e034-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="0e034-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0e034-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0e034-140">7/17/12012</span></span></p>
<p><span data-ttu-id="0e034-141">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="0e034-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0e034-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0e034-142">7/13/2012</span></span></p>
<p><span data-ttu-id="0e034-143">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="0e034-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-144"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="0e034-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0e034-147">7/17/12012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="0e034-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0e034-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="0e034-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0e034-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0e034-150">7/17/12012</span></span></p>
<p><span data-ttu-id="0e034-151">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="0e034-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0e034-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0e034-152">7/13/2012</span></span></p>
<p><span data-ttu-id="0e034-153">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="0e034-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-154"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-p110">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="0e034-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e034-157">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="0e034-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0e034-158">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="0e034-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0e034-159">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="0e034-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0e034-160">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="0e034-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0e034-161">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="0e034-162">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/17/12012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/12012 12:00 Uhr bis 9/7/12012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="0e034-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0e034-163">Metriken</span><span class="sxs-lookup"><span data-stu-id="0e034-163">Metrics</span></span>

<span data-ttu-id="0e034-164">In der folgenden Tabelle werden Metriken aufgelistet, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e034-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="0e034-165">Metriken im zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0e034-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e034-166">Name</span><span class="sxs-lookup"><span data-stu-id="0e034-166">Name</span></span></th>
<th><span data-ttu-id="0e034-167">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="0e034-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0e034-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e034-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e034-169"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="0e034-170"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="0e034-171"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="0e034-172"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-173">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-173">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-174">Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an.</span><span class="sxs-lookup"><span data-stu-id="0e034-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="0e034-175">Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e034-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="0e034-176">Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/17/12012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-177"><strong>Peer-to-Peer-Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-178">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-178">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-179">Gesamtanzahl der abgehaltenen Peer-to-Peer-Sitzungen, unabhängig vom Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="0e034-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-180"><strong>Peer-to-Peer-Chatsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-181">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-181">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p113">Gesamtanzahl der Peer-to-Peer-Chatnachrichtensitzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-184"><strong>Peer-to-Peer-Chatnachrichten insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-185">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-185">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p114">Gesamtanzahl der in Peer-to-Peer-Sitzungen gesendeten Chatnachrichten. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-188"><strong>Peer-to-Peer-Audiositzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-189">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-189">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p115">Gesamtanzahl der Peer-to-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-192"><strong>Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-193">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-193">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-194">Gesamtdauer der Peer-to-Peer-Audiositzungen.</span><span class="sxs-lookup"><span data-stu-id="0e034-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="0e034-195">Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-196"><strong>Durchschnittliche Dauer der Peer-to-Peer-Audiositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-197">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-197">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p117">Durchschnittliche Dauer einer Peer-to-Peer-Audiositzung. Wird errechnet, indem die Gesamtdauer der Audiositzungen durch die Gesamtanzahl der Audiositzungen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="0e034-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-200"><strong>Peer-to-Peer-Videositzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-201">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-201">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p118">Gesamtanzahl der Peer-to-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen zählen; jede Videositzung zählt als eine Videositzung und eine Audiositzung. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-205"><strong>Gesamtdauer der Peer-to-Peer-Videositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-206">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-206">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p119">Gesamtdauer der Peer-to-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e034-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-209"><strong>Durchschnittliche Dauer der Peer-to-Peer-Videositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-210">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-210">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-p120">Durchschnittliche Dauer einer Peer-to-Peer-Videositzung. Wird errechnet, indem die Gesamtdauer der Videositzungen durch die Gesamtanzahl der Videositzungen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="0e034-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e034-213"><strong>Peer-to-Peer-Dateiübertragungssitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-214">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-214">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-215">Gesamtanzahl der Peer-to-Peer-Sitzungen mit Dateiübertragungen.</span><span class="sxs-lookup"><span data-stu-id="0e034-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e034-216"><strong>Peer-to-Peer-Anwendungsfreigabesitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="0e034-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0e034-217">Nein</span><span class="sxs-lookup"><span data-stu-id="0e034-217">No</span></span></p></td>
<td><p><span data-ttu-id="0e034-218">Gesamtanzahl der Peer-to-Peer-Sitzungen mit Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="0e034-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

