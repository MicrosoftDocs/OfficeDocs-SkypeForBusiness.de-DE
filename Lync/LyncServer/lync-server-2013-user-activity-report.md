---
title: 'Lync Server 2013: Bericht über Benutzeraktivität'
description: 'Lync Server 2013: Bericht über Benutzeraktivität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569831"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="fc50c-103">Benutzer Aktivitätsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc50c-103">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc50c-104">_**Letztes Änderungsstand des Themas:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="fc50c-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="fc50c-p101">Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-zu-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-zu-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="fc50c-p102">Der Bericht über Benutzeraktivität wird auch als "Helpdesk"-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdeskpersonal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld Präfix des Benutzer-URI eingeben.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="fc50c-112">In diesem Fall gibt der Bericht über Benutzeraktivität Informationen für alle Benutzer zurück, deren SIP-URI mit der angegebenen Zeichenfolge beginnt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-112">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="fc50c-113">Wenn Sie beispielsweise " **Ken** " in das Feld "URI" eingeben, wird der Bericht "Benutzeraktivität" nach " **Ken**" suchen. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fc50c-113">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="fc50c-114">Sie finden diese Benutzer jedoch auch:</span><span class="sxs-lookup"><span data-stu-id="fc50c-114">However, it will also locate these users:</span></span>

  - <span data-ttu-id="fc50c-115">**Ken**Azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc50c-115">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="fc50c-116">**Ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc50c-116">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="fc50c-117">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc50c-117">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="fc50c-118">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc50c-118">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="fc50c-119">Um sicherzustellen, dass nur Informationen für Ken Myers zurückgegeben werden, geben Sie entweder seinen vollständigen URI (Ken.Myer@litwareinc.com) in das Suchfeld oder zumindest den Typ von Ken URI ein, um ihn von anderen Benutzern in Ihrer Organisation eindeutig zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fc50c-119">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="fc50c-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fc50c-120">For example:</span></span>

<span data-ttu-id="fc50c-121">Ken.my</span><span class="sxs-lookup"><span data-stu-id="fc50c-121">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="fc50c-122">So greifen Sie auf den Bericht über Benutzeraktivität zu</span><span class="sxs-lookup"><span data-stu-id="fc50c-122">To access the user activity report</span></span>

<span data-ttu-id="fc50c-123">Auf den Bericht über die Benutzeraktivität wird über die Startseite für Überwachungsberichte zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="fc50c-123">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="fc50c-124">Sie können auch den Bericht über Benutzeraktivität erreichen, indem Sie im [Bericht IP-Telefon Inventur in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md)auf die Metrik Benutzer-URI klicken.</span><span class="sxs-lookup"><span data-stu-id="fc50c-124">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="fc50c-125">Klicken Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz), um zum Konferenz Detail Bericht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="fc50c-125">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="fc50c-126">Wenn Sie auf die Detail Metrik eines Peer-to-Peer-Anrufs klicken, gelangen Sie entsprechend zum [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="fc50c-126">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="fc50c-127">Optimale Nutzung des Berichts über Benutzeraktivität</span><span class="sxs-lookup"><span data-stu-id="fc50c-127">Making the best use of the user activity report</span></span>

<span data-ttu-id="fc50c-128">Es gibt zwar viele gute Informationen im Bericht über Benutzeraktivität, aber diese Informationen können manchmal schwer zu finden sein.</span><span class="sxs-lookup"><span data-stu-id="fc50c-128">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="fc50c-129">Beispielsweise sind alle Benutzeraktivitäten, die während eines bestimmten Zeitraums in Ihrer Organisation stattfinden, im Bericht über Benutzeraktivität enthalten; Das bedeutet, begraben, innerhalb des Berichts werden Informationen darüber, welche Benutzer tatsächlich Microsoft lync Server 2013 verwendet, in gewisser Weise.</span><span class="sxs-lookup"><span data-stu-id="fc50c-129">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fc50c-130">Technisch gesehen ist es möglich, dass einige Benutzeraktivitäten nicht aufgezeichnet werden: während lync Server versucht, Informationen zu allen Telefon anrufen zu speichern, ist es möglich, dass ein Anruf ohne die Informationen zu diesem Anruf getätigt wurde, die in die Datenbank geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fc50c-130">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="fc50c-131">Lync Server wurde entwickelt, um eine äußerst genaue, aber nicht unbedingt perfekte Übersicht darüber zu geben, wie lync Server 2013 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc50c-131">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="fc50c-132">(Die Tatsache, dass es keine Garantie dafür gibt, dass 100% aller Anrufe aufgezeichnet werden, erklärt, warum lync Server Überwachung nicht als Abrechnungssystem verwendet werden sollte.)</span><span class="sxs-lookup"><span data-stu-id="fc50c-132">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="fc50c-p108">Zweitens können in einem Überwachungsbericht nur maximal 1.000 Datensätze angezeigt werden. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="fc50c-135">Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?</span><span class="sxs-lookup"><span data-stu-id="fc50c-135">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="fc50c-136">Welcher der Benutzer war in diesem Zeitraum am aktivsten?</span><span class="sxs-lookup"><span data-stu-id="fc50c-136">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="fc50c-137">Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="fc50c-137">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="fc50c-138">Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten nach einem Excel-Arbeitsblatt exportieren.</span><span class="sxs-lookup"><span data-stu-id="fc50c-138">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="fc50c-139">Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="fc50c-139">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="fc50c-140">Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="fc50c-140">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="fc50c-141">Zu diesem Zeitpunkt können Sie die Daten aus dem Importieren. CSV-Datei zu Windows PowerShell, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="fc50c-141">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="fc50c-142">Nachdem die Daten importiert wurden, können Sie mit einfachen Windows PowerShell-Befehlen helfen, Ihre Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="fc50c-142">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="fc50c-143">Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als "Absenderbenutzer" fungiert haben:</span><span class="sxs-lookup"><span data-stu-id="fc50c-143">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="fc50c-144">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="fc50c-144">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="fc50c-145">Mit diesem Befehl werden eindeutige Benutzer aufgelistet (basierend auf der Gesamtanzahl der Sitzungen, an denen sie teilgenommen haben:</span><span class="sxs-lookup"><span data-stu-id="fc50c-145">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="fc50c-146">Der Befehl gibt ähnliche Daten wie die folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="fc50c-146">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="fc50c-147">Dieser Befehl beschränkt die gemeldeten Sitzungen auf diejenigen mit Audio als Modalität ein:</span><span class="sxs-lookup"><span data-stu-id="fc50c-147">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="fc50c-148">Wenn Sie mit der Maus auf eine beliebige Diagnose-ID im Bericht zeigen, erscheint eine QuickInfo mit einer Beschreibung der ID.</span><span class="sxs-lookup"><span data-stu-id="fc50c-148">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fc50c-149">Filter</span><span class="sxs-lookup"><span data-stu-id="fc50c-149">Filters</span></span>

<span data-ttu-id="fc50c-p111">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="fc50c-154">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fc50c-154">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="fc50c-155">Bericht über Benutzeraktivität – Filter</span><span class="sxs-lookup"><span data-stu-id="fc50c-155">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc50c-156">Name</span><span class="sxs-lookup"><span data-stu-id="fc50c-156">Name</span></span></th>
<th><span data-ttu-id="fc50c-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc50c-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-158"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-158"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-p112">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fc50c-161">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="fc50c-161">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="fc50c-p113">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fc50c-164">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="fc50c-164">7/17/12012</span></span></p>
<p><span data-ttu-id="fc50c-165">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="fc50c-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fc50c-166">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="fc50c-166">7/13/2012</span></span></p>
<p><span data-ttu-id="fc50c-167">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="fc50c-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-168"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-168"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-p114">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fc50c-171">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="fc50c-171">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="fc50c-p115">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fc50c-174">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="fc50c-174">7/17/12012</span></span></p>
<p><span data-ttu-id="fc50c-175">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="fc50c-175">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fc50c-176">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="fc50c-176">7/13/2012</span></span></p>
<p><span data-ttu-id="fc50c-177">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="fc50c-177">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-178"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-178"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-p116">Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fc50c-181">Alle</span><span class="sxs-lookup"><span data-stu-id="fc50c-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="fc50c-182">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="fc50c-182">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="fc50c-183">Konferenz</span><span class="sxs-lookup"><span data-stu-id="fc50c-183">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-184"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-184"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-185">Die verfügbare Modalität variiert je nach Aktivitätstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="fc50c-185">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="fc50c-186">Wenn es sich bei dem Aktivitätstyp um einen Peer-to-Peer handelt, können Sie Chat auswählen. Dateiübertragung; Anwendungsfreigabe; Stimme oder Video als Modalität.</span><span class="sxs-lookup"><span data-stu-id="fc50c-186">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="fc50c-187">Wenn es sich bei dem Aktivitätstyp um Konferenz handelt, können Sie Chat Telefonkonferenz auswählen. Webkonferenz; Anwendungsfreigabe; Sprach-Video Konferenz; oder Telefonkonferenz.</span><span class="sxs-lookup"><span data-stu-id="fc50c-187">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-188"><strong>Sitzungskategorie</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-188"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-p118">Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fc50c-191">Alle</span><span class="sxs-lookup"><span data-stu-id="fc50c-191">[All]</span></span></p></li>
<li><p><span data-ttu-id="fc50c-192">Erfolg</span><span class="sxs-lookup"><span data-stu-id="fc50c-192">Success</span></span></p></li>
<li><p><span data-ttu-id="fc50c-193">Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="fc50c-193">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="fc50c-194">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="fc50c-194">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="fc50c-195">Ein &quot; Erwarteter Fehler &quot; ist ein Fehler, der erwartet wird; wenn beispielsweise ein Benutzer seinen Status auf "nicht stören" festgelegt hat, wird erwartet, dass ein Aufruf dieses Benutzers fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-195">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="fc50c-196">Ein &quot; unerwarteter Fehler &quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-196">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="fc50c-197">Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet.</span><span class="sxs-lookup"><span data-stu-id="fc50c-197">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="fc50c-198">In diesem Fall würde der Fehler als "unerwartet" gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="fc50c-198">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-199"><strong>Präfix des Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-199"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-p120">SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="fc50c-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="fc50c-203">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc50c-203">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="fc50c-204">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="fc50c-204">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="fc50c-205">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-205">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="fc50c-206">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="fc50c-206">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc50c-207">Name</span><span class="sxs-lookup"><span data-stu-id="fc50c-207">Name</span></span></th>
<th><span data-ttu-id="fc50c-208">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="fc50c-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fc50c-209">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc50c-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-210"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-210"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-211">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-211">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-212">Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Peer-to-Peer-Sitzungsbericht für die ausgewählte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="fc50c-212">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-213"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-213"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-214">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-215">SIP-Adresse des Benutzers, der die Peer-zu-Peer-Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="fc50c-215">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-216"><strong>An Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-216"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-217">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-218">SIP-Adresse des Benutzers, der der Peer-zu-Peer-Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fc50c-218">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-219"><strong>Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-219"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-220">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-p121">In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-223"><strong>Zeitpunkt der Einladung</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-223"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-224">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-225">Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-zu-Peer-Sitzungseinladung gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fc50c-225">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-226"><strong>Antwortzeit</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-226"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-227">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-228">Datum und Uhrzeit, zu denen der &quot; &quot; Benutzer die Sitzungseinladung angenommen hat.</span><span class="sxs-lookup"><span data-stu-id="fc50c-228">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-229"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-229"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-230">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-231">Datum und Uhrzeit, an dem bzw. zu der die Peer-zu-Peer-Sitzung endete.</span><span class="sxs-lookup"><span data-stu-id="fc50c-231">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-232"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-232"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-233">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-p122">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="fc50c-236">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="fc50c-236">Metrics for conferencing sessions</span></span>

<span data-ttu-id="fc50c-237">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-237">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="fc50c-238">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="fc50c-238">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc50c-239">Name</span><span class="sxs-lookup"><span data-stu-id="fc50c-239">Name</span></span></th>
<th><span data-ttu-id="fc50c-240">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="fc50c-240">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fc50c-241">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc50c-241">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-242"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-242"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-243">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-243">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-244">Eindeutige ID für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fc50c-244">Unique conference identifier.</span></span> <span data-ttu-id="fc50c-245">Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="fc50c-245">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="fc50c-246">Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-246">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="fc50c-247">Ausführliche Informationen finden Sie im &quot; Abschnitt Metriken für Konferenzteilnehmer &quot; weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="fc50c-247">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-248"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-248"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-249">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-249">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-250">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="fc50c-250">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-251"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-251"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-252">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-252">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-253">Name des in der Konferenz verwendeten Edgesservers (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="fc50c-253">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-254"><strong>Start time</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-254"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-255">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-255">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-256">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="fc50c-256">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-257"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-257"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-258">Ja</span><span class="sxs-lookup"><span data-stu-id="fc50c-258">Yes</span></span></p></td>
<td><p><span data-ttu-id="fc50c-259">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="fc50c-259">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="fc50c-260">Metriken für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="fc50c-260">Metrics for conference participants</span></span>

<span data-ttu-id="fc50c-261">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc50c-261">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="fc50c-262">Metriken für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="fc50c-262">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc50c-263">Name</span><span class="sxs-lookup"><span data-stu-id="fc50c-263">Name</span></span></th>
<th><span data-ttu-id="fc50c-264">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="fc50c-264">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fc50c-265">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc50c-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-266"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-266"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-267">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-267">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-268">Konferenzrolle (z. B. Referent) des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="fc50c-268">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-269"><strong>Teilnehmer</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-269"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-270">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-270">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-271">SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="fc50c-271">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-272"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-272"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-273">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-273">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-274">Typ der Netzwerkverbindung.</span><span class="sxs-lookup"><span data-stu-id="fc50c-274">Network connection type.</span></span> <span data-ttu-id="fc50c-275">Beispielsweise &quot; von Internal &quot; für interne Verbindung oder &quot; von PSTN &quot; für Einwahlbenutzer.</span><span class="sxs-lookup"><span data-stu-id="fc50c-275">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-276"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-276"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-277">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-277">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-278">Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fc50c-278">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc50c-279"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-279"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-280">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-280">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-281">Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="fc50c-281">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc50c-282"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="fc50c-282"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fc50c-283">Nein</span><span class="sxs-lookup"><span data-stu-id="fc50c-283">No</span></span></p></td>
<td><p><span data-ttu-id="fc50c-p125">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="fc50c-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

