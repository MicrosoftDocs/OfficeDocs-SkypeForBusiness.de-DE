---
title: 'Lync Server 2013: Peer-zu-Peer-Chat Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 359c3fad7f41d990ffdba3aa533d0d5f10456665
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="649e8-102">Peer-zu-Peer-Chat Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="649e8-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="649e8-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="649e8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="649e8-p101">Der Bericht über Peer-to-Peer-Sofortnachrichten enthält Trendinformationen zu den Peer-to-Peer-Sofortnachrichtensitzungen, aufgeschlüsselt nach Pool und Authentifizierungstyp. Der Bericht kann entweder die Gesamtanzahl der im angegebenen Zeitraum abgehaltenen Sitzungen (z. B. nach Tag oder nach Stunden) oder die Gesamtanzahl der in diesem Zeitraum gesendeten Sofortnachrichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="649e8-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="649e8-106">Zugreifen auf den Bericht über Peer-to-Peer-Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="649e8-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="649e8-107">Sie können nur auf den Chat-Chat Bericht zugreifen, indem Sie den [Bericht Peer-to-Peer-Aktivitätszusammenfassung in lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) öffnen und dann auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="649e8-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="649e8-108">Peer-to-Peer-Chatsitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="649e8-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="649e8-109">Peer-to-Peer-Chatnachrichten insgesamt</span><span class="sxs-lookup"><span data-stu-id="649e8-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="649e8-110">Optimales Verwenden des Berichts über Peer-to-Peer-Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="649e8-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="649e8-p102">Standardmäßig wird im Bericht über Peer-to-Peer-Sofortnachrichten die Anzahl der Nachrichten pro Stunde (oder, abhängig von Ihren Einstellungen, pro Tag) angezeigt. Sie können jedoch auch den Tag nach Sitzungen pro Stunde anzeigen. Klicken Sie dazu rechts oben im Berichtfenster auf die Schaltfläche zum **Ein- und Ausblenden der Parameter** und klicken Sie dann in der Liste **Bericht nach** auf **Sitzungsanzahl**.</span><span class="sxs-lookup"><span data-stu-id="649e8-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="649e8-114">Filter</span><span class="sxs-lookup"><span data-stu-id="649e8-114">Filters</span></span>

<span data-ttu-id="649e8-p103">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-to-Peer-Sofortnachrichten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="649e8-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="649e8-117">Filter im Bericht über Peer-to-Peer-Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="649e8-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649e8-118">Name</span><span class="sxs-lookup"><span data-stu-id="649e8-118">Name</span></span></th>
<th><span data-ttu-id="649e8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="649e8-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e8-120"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-p104">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="649e8-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="649e8-123">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="649e8-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="649e8-p105">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="649e8-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="649e8-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="649e8-126">7/7/2012</span></span></p>
<p><span data-ttu-id="649e8-127">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die Woche oder den Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="649e8-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="649e8-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="649e8-128">7/3/2012</span></span></p>
<p><span data-ttu-id="649e8-129">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="649e8-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e8-130"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-p106">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="649e8-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="649e8-133">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="649e8-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="649e8-p107">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="649e8-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="649e8-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="649e8-136">7/7/2012</span></span></p>
<p><span data-ttu-id="649e8-137">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="649e8-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="649e8-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="649e8-138">7/3/2012</span></span></p>
<p><span data-ttu-id="649e8-139">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="649e8-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649e8-140"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-p108">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="649e8-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="649e8-143">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="649e8-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="649e8-144">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="649e8-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="649e8-145">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="649e8-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="649e8-146">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="649e8-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="649e8-147">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="649e8-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="649e8-148">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="649e8-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e8-149"><strong>Bericht nach</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-p110">Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="649e8-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="649e8-152">Sitzungsanzahl</span><span class="sxs-lookup"><span data-stu-id="649e8-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="649e8-153">Nachrichtenanzahl</span><span class="sxs-lookup"><span data-stu-id="649e8-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="649e8-154">Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Pool</span><span class="sxs-lookup"><span data-stu-id="649e8-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="649e8-155">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sofortnachrichten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="649e8-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="649e8-156">Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Pool</span><span class="sxs-lookup"><span data-stu-id="649e8-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649e8-157">Name</span><span class="sxs-lookup"><span data-stu-id="649e8-157">Name</span></span></th>
<th><span data-ttu-id="649e8-158">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="649e8-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="649e8-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="649e8-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e8-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-161">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-161">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-162">Der Name des registrierungspools oder des Edge-Servers.</span><span class="sxs-lookup"><span data-stu-id="649e8-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e8-163"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-164">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-164">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-165">Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.</span><span class="sxs-lookup"><span data-stu-id="649e8-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649e8-166"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-167">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-167">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-168">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="649e8-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="649e8-169">Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp</span><span class="sxs-lookup"><span data-stu-id="649e8-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="649e8-170">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sofortnachrichten für die einzelnen von den Teilnehmern in einer Peer-to-Peer-Sitzung verwendeten Authentifizierungstypen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="649e8-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="649e8-171">Metriken für den Bericht über Peer-to-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp</span><span class="sxs-lookup"><span data-stu-id="649e8-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649e8-172">Name</span><span class="sxs-lookup"><span data-stu-id="649e8-172">Name</span></span></th>
<th><span data-ttu-id="649e8-173">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="649e8-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="649e8-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="649e8-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e8-175"><strong>Authentifizierungstyp</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-176">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-176">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-p111">Der von den Sitzungsteilnehmern verwendete Authentifizierungstyp. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="649e8-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="649e8-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="649e8-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="649e8-180">Federated</span><span class="sxs-lookup"><span data-stu-id="649e8-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="649e8-181">PIC</span><span class="sxs-lookup"><span data-stu-id="649e8-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e8-182"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-183">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-183">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-184">Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.</span><span class="sxs-lookup"><span data-stu-id="649e8-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649e8-185"><strong>Gesamt</strong></span><span class="sxs-lookup"><span data-stu-id="649e8-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="649e8-186">Nein</span><span class="sxs-lookup"><span data-stu-id="649e8-186">No</span></span></p></td>
<td><p><span data-ttu-id="649e8-187">Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="649e8-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

