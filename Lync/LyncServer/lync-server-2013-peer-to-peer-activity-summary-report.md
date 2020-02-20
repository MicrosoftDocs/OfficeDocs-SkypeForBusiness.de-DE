---
title: 'Lync Server 2013: zusammenfassender Bericht über Peer-to-Peer-Aktivitäten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="58435-102">Zusammenfassender Bericht über Peer-to-Peer-Aktivitäten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58435-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58435-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="58435-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="58435-104">Der zusammenfassende Bericht über Peer-to-Peer-Aktivitäten bietet eine Gesamtübersicht über Peer-zu-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="58435-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="58435-105">Eine Peer-to-Peer-Sitzung umfasst normalerweise nur zwei Benutzer und erfordert nicht die Verwendung der lync Server Konferenzdienste.</span><span class="sxs-lookup"><span data-stu-id="58435-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="58435-106">Im Vergleich dazu umfasst eine Konferenz normalerweise mehr als zwei Benutzer und erfordert die Verwendung von Microsoft lync Server 2013 Konferenzdiensten.</span><span class="sxs-lookup"><span data-stu-id="58435-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="58435-107">Die Konferenz Aktivität wird im zusammenfassenden Konferenzbericht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="58435-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="58435-108">Der zusammenfassende Bericht über Peer-to-Peer-Aktivität hilft Ihnen bei der Beantwortung von Fragen wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="58435-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="58435-109">Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem typischen Tag?</span><span class="sxs-lookup"><span data-stu-id="58435-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="58435-110">Nutzen meine Benutzer tatsächlich die lync Server Anwendungsfreigabe und Dateiübertragungsfunktionen?</span><span class="sxs-lookup"><span data-stu-id="58435-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="58435-111">Benutzer haben sich beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam erscheint.</span><span class="sxs-lookup"><span data-stu-id="58435-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="58435-112">Wie viele Minuten sind Peer-to-Peer-Audio-und-Videositzungen während dieser Zeiträume gewidmet?</span><span class="sxs-lookup"><span data-stu-id="58435-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="58435-113">Zugriff auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="58435-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="58435-114">Sie greifen auf den Bericht über Peer-to-Peer-Aktivitätszusammenfassung auf der Startseite für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="58435-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="58435-115">Sie öffnen den [Bericht über Peer-zu-Peer-Chatnachrichten in lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="58435-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="58435-116">Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen</span><span class="sxs-lookup"><span data-stu-id="58435-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="58435-117">Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="58435-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="58435-118">Ebenso können Sie den Bericht über Peer-zu-Peer-sprach-und-Video Funktionen öffnen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="58435-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="58435-119">Peer-zu-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="58435-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="58435-120">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="58435-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="58435-121">Peer-zu-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="58435-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="58435-122">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="58435-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="58435-123">Optimale Nutzung des Zusammenfassungsberichts über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="58435-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="58435-124">Am unteren Rand des Zusammenfassungsberichts über Peer-to-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie Peer-to-Peer-Sofortnachrichtensitzungen und Peer-to-Peer-Chatnachrichten insgesamt.</span><span class="sxs-lookup"><span data-stu-id="58435-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="58435-125">Dadurch wird eine kurze Zusammenfassung der detaillierten Informationen im Textkörper des Berichts bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58435-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="58435-126">Filter</span><span class="sxs-lookup"><span data-stu-id="58435-126">Filters</span></span>

<span data-ttu-id="58435-127">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="58435-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="58435-128">Beispielsweise können Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivität auswählen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="58435-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="58435-129">In diesem Fall wird die Aktivität nach Stunde, Tag, Woche oder Monat gruppiert.</span><span class="sxs-lookup"><span data-stu-id="58435-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="58435-130">In der folgenden Tabelle sind die Filter aufgeführt, die Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="58435-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="58435-131">Berichtfilter für Peer-to-Peer-Aktivitätszusammenfassung</span><span class="sxs-lookup"><span data-stu-id="58435-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58435-132">Name</span><span class="sxs-lookup"><span data-stu-id="58435-132">Name</span></span></th>
<th><span data-ttu-id="58435-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58435-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58435-134"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="58435-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="58435-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="58435-137">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="58435-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="58435-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="58435-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="58435-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="58435-140">7/17/12012</span></span></p>
<p><span data-ttu-id="58435-141">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="58435-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="58435-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="58435-142">7/13/2012</span></span></p>
<p><span data-ttu-id="58435-143">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="58435-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-144"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="58435-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="58435-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="58435-147">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="58435-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="58435-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="58435-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="58435-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="58435-150">7/17/12012</span></span></p>
<p><span data-ttu-id="58435-151">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="58435-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="58435-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="58435-152">7/13/2012</span></span></p>
<p><span data-ttu-id="58435-153">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="58435-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-154"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="58435-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-p110">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="58435-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="58435-157">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="58435-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="58435-158">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="58435-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="58435-159">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="58435-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="58435-160">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="58435-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="58435-161">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58435-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="58435-162">Wenn Sie beispielsweise das tägliche Intervall mit dem Startdatum 7/17/12012 und dem Enddatum 2/28/2012 auswählen, werden die Daten für die Tage 8/7/12012 12:00 Uhr bis 9/7/12012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="58435-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="58435-163">Metriken</span><span class="sxs-lookup"><span data-stu-id="58435-163">Metrics</span></span>

<span data-ttu-id="58435-164">In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="58435-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="58435-165">Metriken für den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="58435-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58435-166">Name</span><span class="sxs-lookup"><span data-stu-id="58435-166">Name</span></span></th>
<th><span data-ttu-id="58435-167">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="58435-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="58435-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58435-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58435-169"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="58435-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="58435-170"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="58435-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="58435-171"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="58435-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="58435-172"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="58435-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-173">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-173">No</span></span></p></td>
<td><p><span data-ttu-id="58435-174">Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="58435-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="58435-175">Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen.</span><span class="sxs-lookup"><span data-stu-id="58435-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="58435-176">Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7/17/12012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58435-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-177"><strong>Peer-zu-Peer-Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="58435-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-178">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-178">No</span></span></p></td>
<td><p><span data-ttu-id="58435-179">Die Gesamtzahl der durchgeführten Peer-zu-Peer-Sitzungen, unabhängig vom Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="58435-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-180"><strong>Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="58435-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-181">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-181">No</span></span></p></td>
<td><p><span data-ttu-id="58435-182">Die Gesamtzahl der Peer-zu-Peer-Chatsitzungen (Instant Messaging).</span><span class="sxs-lookup"><span data-stu-id="58435-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="58435-183">Wenn Sie auf dieses Element klicken, zeigt der Bericht den Peer-to-Peer-Chat Bericht für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-184"><strong>Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten</strong></span><span class="sxs-lookup"><span data-stu-id="58435-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-185">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-185">No</span></span></p></td>
<td><p><span data-ttu-id="58435-186">Die Gesamtzahl der in Peer-zu-Peer-Sitzungen gesendeten Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="58435-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="58435-187">Wenn Sie auf dieses Element klicken, zeigt der Bericht den Peer-to-Peer-Chat Bericht für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-188"><strong><c0>Peer-zu-Peer-Audiositzungen insgesamt</c0></strong></span><span class="sxs-lookup"><span data-stu-id="58435-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-189">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-189">No</span></span></p></td>
<td><p><span data-ttu-id="58435-190">Die Gesamtzahl der Peer-zu-Peer-Audioanrufe.</span><span class="sxs-lookup"><span data-stu-id="58435-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="58435-191">Wenn Sie auf dieses Feld klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Daten für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-192"><strong>Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="58435-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-193">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-193">No</span></span></p></td>
<td><p><span data-ttu-id="58435-194">Gesamtzeit Aufwand für Peer-to-Peer-audiositzungen.</span><span class="sxs-lookup"><span data-stu-id="58435-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="58435-195">Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-196"><strong>Durchschnittliche Peer-to-Peer-Audiositzung Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="58435-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-197">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-197">No</span></span></p></td>
<td><p><span data-ttu-id="58435-198">Durchschnittliche Zeitaufwand für Peer-to-Peer-audiositzungen.</span><span class="sxs-lookup"><span data-stu-id="58435-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="58435-199">Wird berechnet, indem die Gesamtdauer der Audiositzung durch die Gesamtzahl der audiositzungen dividiert wird.</span><span class="sxs-lookup"><span data-stu-id="58435-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-200"><strong><c0>Peer-zu-Peer-Videositzungen insgesamt</c0></strong></span><span class="sxs-lookup"><span data-stu-id="58435-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-201">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-201">No</span></span></p></td>
<td><p><span data-ttu-id="58435-202">Die Gesamtzahl der Peer-zu-Peer-Videoanrufe.</span><span class="sxs-lookup"><span data-stu-id="58435-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="58435-203">Beachten Sie, dass Videositzungen auch als audiositzungen gezählt werden: jede Videositzung wird als eine Video-und eine Audiositzung gezählt.</span><span class="sxs-lookup"><span data-stu-id="58435-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="58435-204">Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-205"><strong>Gesamtdauer der Peer-to-Peer-Videositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="58435-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-206">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-206">No</span></span></p></td>
<td><p><span data-ttu-id="58435-207">Gesamtzeit Aufwand für Peer-zu-Peer-Videositzungen.</span><span class="sxs-lookup"><span data-stu-id="58435-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="58435-208">Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="58435-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-209"><strong>Durchschnittliche Peer-to-Peer-Video Sitzungs Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="58435-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-210">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-210">No</span></span></p></td>
<td><p><span data-ttu-id="58435-211">Durchschnittliche Zeitaufwand für Peer-zu-Peer-Videositzungen.</span><span class="sxs-lookup"><span data-stu-id="58435-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="58435-212">Wird berechnet, indem die gesamte Video Sitzungszeit durch die Gesamtzahl der Videositzungen dividiert wird.</span><span class="sxs-lookup"><span data-stu-id="58435-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58435-213"><strong>Peer-zu-Peer-Dateiübertragungssitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="58435-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-214">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-214">No</span></span></p></td>
<td><p><span data-ttu-id="58435-215">Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die Dateiübertragungen umfassten.</span><span class="sxs-lookup"><span data-stu-id="58435-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58435-216"><strong>Peer-zu-Peer-Anwendungsfreigabesitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="58435-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="58435-217">Nein</span><span class="sxs-lookup"><span data-stu-id="58435-217">No</span></span></p></td>
<td><p><span data-ttu-id="58435-218">Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die die Anwendungsfreigabe umfassten.</span><span class="sxs-lookup"><span data-stu-id="58435-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

