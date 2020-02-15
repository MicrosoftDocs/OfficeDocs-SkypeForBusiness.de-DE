---
title: 'Lync Server 2013: zusammenfassender PSTN-Konferenzbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="67f5b-102">Zusammenfassender PSTN-Konferenzbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67f5b-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f5b-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="67f5b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="67f5b-104">In Microsoft lync Server 2013 handelt es sich bei einer PSTN-Konferenz um eine Konferenz, bei der sich mindestens ein Teilnehmer über ein PSTN-Telefon (Public Switched Telephone Network) an den Audioteil anwählt.</span><span class="sxs-lookup"><span data-stu-id="67f5b-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="67f5b-105">(Ein PSTN-Telefon ist ein "Festnetz", ein Mobiltelefon oder ein beliebiges anderes Telefon, das nicht von Voice over IP Gebrauch macht.) Obwohl Sie in den Überwachungsberichten als PSTN-Konferenzen bezeichnet werden, werden diese Konferenzen möglicherweise häufiger als Einwahlkonferenzen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="67f5b-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="67f5b-p102">Der "Zusammenfassende Bericht über PSTN-Konferenzen" liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).</span><span class="sxs-lookup"><span data-stu-id="67f5b-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="67f5b-108">Zugreifen auf den "Zusammenfassenden Bericht über PSTN-Konferenzen"</span><span class="sxs-lookup"><span data-stu-id="67f5b-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="67f5b-p103">Auf der Startseite "Überwachungsberichte" können Sie auf den "Zusammenfassenden Bericht über PSTN-Konferenzen" zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="67f5b-113">Optimale Nutzung des "Zusammenfassenden Berichts über PSTN-Konferenzen"</span><span class="sxs-lookup"><span data-stu-id="67f5b-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="67f5b-114">Um den Prozentsatz aller ihrer Konferenzen zu ermitteln, die Einwahlbenutzer einschließen, vergleichen Sie den Wert der Gesamt Metrik für PSTN-Konferenzen mit der Metrik "Gesamt Konferenzen" [im zusammenfassenden Konferenzbericht in lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="67f5b-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="67f5b-p104">Wenn nicht die von Ihnen erwartete Anzahl an PSTN-Konferenzen angezeigt wird, müssen Sie beachten, dass die Funktion zum Organisieren einer Konferenz, die Einwahlbenutzer zulässt, von der Konferenzrichtlinie abhängt, die einem Benutzern zugewiesen ist. Wenn eine geringe Anzahl Ihrer Benutzer berechtigt ist, PSTN-Konferenzen durchzuführen, werden nur wenige PSTN-Konferenzen angezeigt. Sie können schnell überprüfen, mit welcher Konferenzrichtlinie (falls vorhanden) die Benutzer PSTN-Konferenzen planen können, indem Sie den folgenden Befehl über die Lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="67f5b-117">Dadurch werden Daten zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="67f5b-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="67f5b-118">Es werden Daten nach dem folgenden Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="67f5b-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="67f5b-119">Filter</span><span class="sxs-lookup"><span data-stu-id="67f5b-119">Filters</span></span>

<span data-ttu-id="67f5b-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="67f5b-123">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="67f5b-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="67f5b-124">Filter im Zusammenfassenden Bericht über PSTN-Konferenz</span><span class="sxs-lookup"><span data-stu-id="67f5b-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f5b-125">Name</span><span class="sxs-lookup"><span data-stu-id="67f5b-125">Name</span></span></th>
<th><span data-ttu-id="67f5b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67f5b-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="67f5b-130">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="67f5b-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="67f5b-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="67f5b-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="67f5b-133">7/7/2012</span></span></p>
<p><span data-ttu-id="67f5b-134">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="67f5b-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="67f5b-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="67f5b-135">7/3/2012</span></span></p>
<p><span data-ttu-id="67f5b-136">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="67f5b-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f5b-137"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="67f5b-140">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="67f5b-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="67f5b-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="67f5b-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="67f5b-143">7/7/2012</span></span></p>
<p><span data-ttu-id="67f5b-144">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="67f5b-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="67f5b-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="67f5b-145">7/3/2012</span></span></p>
<p><span data-ttu-id="67f5b-146">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="67f5b-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-147"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-p110">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="67f5b-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="67f5b-150">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="67f5b-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67f5b-151">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="67f5b-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67f5b-152">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="67f5b-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67f5b-153">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="67f5b-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="67f5b-p111">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="67f5b-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="67f5b-156">Metriken</span><span class="sxs-lookup"><span data-stu-id="67f5b-156">Metrics</span></span>

<span data-ttu-id="67f5b-157">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="67f5b-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="67f5b-158">Metriken im Zusammenfassenden Bericht über PSTN-Konferenz</span><span class="sxs-lookup"><span data-stu-id="67f5b-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f5b-159">Name</span><span class="sxs-lookup"><span data-stu-id="67f5b-159">Name</span></span></th>
<th><span data-ttu-id="67f5b-160">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="67f5b-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="67f5b-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67f5b-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-162"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="67f5b-163"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="67f5b-164"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="67f5b-165"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-166">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-166">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-p112">Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf 07.07.2012 klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f5b-170"><strong>PSTN-Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-171">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-171">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-172">Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-173"><strong>Teilnehmer insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-174">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-174">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-175">Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.</span><span class="sxs-lookup"><span data-stu-id="67f5b-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f5b-176"><strong>Gesamtdauer der A/V-Konferenzen in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-177">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-177">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-178">Die Gesamtdauer von Konferenzen mit Audio oder Video.</span><span class="sxs-lookup"><span data-stu-id="67f5b-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-179"><strong>Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-180">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-180">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-p113">Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f5b-183"><strong>PSTN-Teilnehmer insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-184">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-184">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-185">Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f5b-186"><strong>PSTN-Teilnehmerminuten insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-187">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-187">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-p114">Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f5b-190"><strong>Eindeutige Konferenzorganisatoren</strong></span><span class="sxs-lookup"><span data-stu-id="67f5b-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="67f5b-191">Nein</span><span class="sxs-lookup"><span data-stu-id="67f5b-191">No</span></span></p></td>
<td><p><span data-ttu-id="67f5b-p115">Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.</span><span class="sxs-lookup"><span data-stu-id="67f5b-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

