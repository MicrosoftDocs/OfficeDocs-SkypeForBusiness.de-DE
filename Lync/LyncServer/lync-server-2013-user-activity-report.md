---
title: 'Lync Server 2013: Bericht über Benutzeraktivität'
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
ms.openlocfilehash: 1ad0297451c98851d156f088497db81345520b88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="c8ffe-102">Benutzer Aktivitätsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ffe-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8ffe-103">_**Letztes Änderungsstand des Themas:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="c8ffe-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="c8ffe-p101">Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-zu-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-zu-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="c8ffe-p102">Der Bericht über Benutzeraktivität wird auch als "Helpdesk"-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdeskpersonal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld Präfix des Benutzer-URI eingeben.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="c8ffe-111">In diesem Fall gibt der Bericht über Benutzeraktivität Informationen für alle Benutzer zurück, deren SIP-URI mit der angegebenen Zeichenfolge beginnt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="c8ffe-112">Wenn Sie beispielsweise " **Ken** " in das Feld "URI" eingeben, wird der Bericht "Benutzeraktivität" nach " **Ken**" suchen. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="c8ffe-113">Sie finden diese Benutzer jedoch auch:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="c8ffe-114">**Ken**Azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c8ffe-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="c8ffe-115">**Ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c8ffe-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="c8ffe-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c8ffe-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="c8ffe-117">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c8ffe-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="c8ffe-118">Um sicherzustellen, dass nur Informationen für Ken Myers zurückgegeben werden, geben Sie entweder seinen vollständigen URI (Ken.Myer@litwareinc.com) in das Suchfeld oder zumindest den Typ von Ken URI ein, um ihn von anderen Benutzern in Ihrer Organisation eindeutig zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="c8ffe-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-119">For example:</span></span>

<span data-ttu-id="c8ffe-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="c8ffe-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="c8ffe-121">So greifen Sie auf den Bericht über Benutzeraktivität zu</span><span class="sxs-lookup"><span data-stu-id="c8ffe-121">To access the user activity report</span></span>

<span data-ttu-id="c8ffe-122">Auf den Bericht über die Benutzeraktivität wird über die Startseite für Überwachungsberichte zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c8ffe-123">Sie können auch den Bericht über Benutzeraktivität erreichen, indem Sie im [Bericht IP-Telefon Inventur in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md)auf die Metrik Benutzer-URI klicken.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="c8ffe-124">Klicken Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz), um zum Konferenz Detail Bericht zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="c8ffe-125">Wenn Sie auf die Detail Metrik eines Peer-to-Peer-Anrufs klicken, gelangen Sie entsprechend zum [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="c8ffe-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="c8ffe-126">Optimale Nutzung des Berichts über Benutzeraktivität</span><span class="sxs-lookup"><span data-stu-id="c8ffe-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="c8ffe-127">Es gibt zwar viele gute Informationen im Bericht über Benutzeraktivität, aber diese Informationen können manchmal schwer zu finden sein.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="c8ffe-128">Beispielsweise sind alle Benutzeraktivitäten, die während eines bestimmten Zeitraums in Ihrer Organisation stattfinden, im Bericht über Benutzeraktivität enthalten; Das bedeutet, begraben, innerhalb des Berichts werden Informationen darüber, welche Benutzer tatsächlich Microsoft lync Server 2013 verwendet, in gewisser Weise.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c8ffe-129">Technisch gesehen ist es möglich, dass einige Benutzeraktivitäten nicht aufgezeichnet werden: während lync Server versucht, Informationen zu allen Telefon anrufen zu speichern, ist es möglich, dass ein Anruf ohne die Informationen zu diesem Anruf getätigt wurde, die in die Datenbank geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="c8ffe-130">Lync Server wurde entwickelt, um eine äußerst genaue, aber nicht unbedingt perfekte Übersicht darüber zu geben, wie lync Server 2013 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="c8ffe-131">(Die Tatsache, dass es keine Garantie dafür gibt, dass 100% aller Anrufe aufgezeichnet werden, erklärt, warum lync Server Überwachung nicht als Abrechnungssystem verwendet werden sollte.)</span><span class="sxs-lookup"><span data-stu-id="c8ffe-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="c8ffe-p108">Zweitens können in einem Überwachungsbericht nur maximal 1.000 Datensätze angezeigt werden. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="c8ffe-134">Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="c8ffe-135">Welcher der Benutzer war in diesem Zeitraum am aktivsten?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="c8ffe-136">Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="c8ffe-137">Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten nach einem Excel-Arbeitsblatt exportieren.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="c8ffe-138">Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="c8ffe-139">Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="c8ffe-140">Zu diesem Zeitpunkt können Sie die Daten aus dem Importieren. CSV-Datei zu Windows PowerShell, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="c8ffe-141">Nachdem die Daten importiert wurden, können Sie mit einfachen Windows PowerShell-Befehlen helfen, Ihre Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="c8ffe-142">Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als "Absenderbenutzer" fungiert haben:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="c8ffe-143">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="c8ffe-144">Mit diesem Befehl werden eindeutige Benutzer aufgelistet (basierend auf der Gesamtanzahl der Sitzungen, an denen sie teilgenommen haben:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="c8ffe-145">Der Befehl gibt ähnliche Daten wie die folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="c8ffe-146">Dieser Befehl beschränkt die gemeldeten Sitzungen auf diejenigen mit Audio als Modalität ein:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="c8ffe-147">Wenn Sie mit der Maus auf eine beliebige Diagnose-ID im Bericht zeigen, erscheint eine QuickInfo mit einer Beschreibung der ID.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c8ffe-148">Filter</span><span class="sxs-lookup"><span data-stu-id="c8ffe-148">Filters</span></span>

<span data-ttu-id="c8ffe-p111">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c8ffe-153">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="c8ffe-154">Bericht über Benutzeraktivität – Filter</span><span class="sxs-lookup"><span data-stu-id="c8ffe-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8ffe-155">Name</span><span class="sxs-lookup"><span data-stu-id="c8ffe-155">Name</span></span></th>
<th><span data-ttu-id="c8ffe-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ffe-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p112">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c8ffe-160">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c8ffe-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c8ffe-p113">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c8ffe-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c8ffe-163">7/17/12012</span></span></p>
<p><span data-ttu-id="c8ffe-164">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c8ffe-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c8ffe-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c8ffe-165">7/13/2012</span></span></p>
<p><span data-ttu-id="c8ffe-166">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-167"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p114">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c8ffe-170">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c8ffe-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c8ffe-p115">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c8ffe-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c8ffe-173">7/17/12012</span></span></p>
<p><span data-ttu-id="c8ffe-174">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c8ffe-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c8ffe-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c8ffe-175">7/13/2012</span></span></p>
<p><span data-ttu-id="c8ffe-176">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-177"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p116">Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8ffe-180">Alle</span><span class="sxs-lookup"><span data-stu-id="c8ffe-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="c8ffe-181">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="c8ffe-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="c8ffe-182">Konferenz</span><span class="sxs-lookup"><span data-stu-id="c8ffe-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-183"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-184">Die verfügbare Modalität variiert je nach Aktivitätstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="c8ffe-185">Wenn es sich bei dem Aktivitätstyp um einen Peer-to-Peer handelt, können Sie Chat auswählen. Dateiübertragung; Anwendungsfreigabe; Stimme oder Video als Modalität.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="c8ffe-186">Wenn es sich bei dem Aktivitätstyp um Konferenz handelt, können Sie Chat Telefonkonferenz auswählen. Webkonferenz; Anwendungsfreigabe; Sprach-Video Konferenz; oder Telefonkonferenz.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-187"><strong>Sitzungskategorie</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p118">Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8ffe-190">Alle</span><span class="sxs-lookup"><span data-stu-id="c8ffe-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="c8ffe-191">Success</span><span class="sxs-lookup"><span data-stu-id="c8ffe-191">Success</span></span></p></li>
<li><p><span data-ttu-id="c8ffe-192">Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="c8ffe-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c8ffe-193">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="c8ffe-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="c8ffe-194">Ein &quot;erwarteter&quot; Fehler ist ein Fehler, der voraussichtlich eintreten wird. Wenn ein Benutzer beispielsweise seinen Status auf "nicht stören" festgelegt hat, wird erwartet, dass ein Aufruf dieses Benutzers fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="c8ffe-195">Ein &quot;unerwarteter Fehler&quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="c8ffe-196">Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="c8ffe-197">In diesem Fall würde der Fehler als "unerwartet" gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-198"><strong>Präfix des Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p120">SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="c8ffe-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c8ffe-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c8ffe-203">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c8ffe-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="c8ffe-204">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c8ffe-205">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c8ffe-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8ffe-206">Name</span><span class="sxs-lookup"><span data-stu-id="c8ffe-206">Name</span></span></th>
<th><span data-ttu-id="c8ffe-207">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8ffe-208">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ffe-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-209"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-210">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-210">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-211">Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Peer-to-Peer-Sitzungsbericht für die ausgewählte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-212"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-213">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-214">SIP-Adresse des Benutzers, der die Peer-zu-Peer-Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-215"><strong>An Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-216">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-217">SIP-Adresse des Benutzers, der der Peer-zu-Peer-Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-218"><strong>Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-219">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p121">In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-222"><strong>Zeitpunkt der Einladung</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-223">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-224">Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-zu-Peer-Sitzungseinladung gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-225"><strong>Antwortzeit</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-226">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-227">Datum und Uhrzeit, zu &quot;&quot; denen der Benutzer die Sitzungseinladung angenommen hat.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-228"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-229">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-230">Datum und Uhrzeit, an dem bzw. zu der die Peer-zu-Peer-Sitzung endete.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-231"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-232">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p122">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c8ffe-235">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="c8ffe-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="c8ffe-236">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c8ffe-237">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="c8ffe-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8ffe-238">Name</span><span class="sxs-lookup"><span data-stu-id="c8ffe-238">Name</span></span></th>
<th><span data-ttu-id="c8ffe-239">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8ffe-240">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ffe-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-241"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-242">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-243">Eindeutige ID für die Konferenz.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-243">Unique conference identifier.</span></span> <span data-ttu-id="c8ffe-244">Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="c8ffe-245">Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="c8ffe-246">Ausführliche Informationen finden Sie im &quot;Abschnitt Metriken für Konferenz&quot; Teilnehmer weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-247"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-248">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-249">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-251">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-252">Name des in der Konferenz verwendeten Edgesservers (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="c8ffe-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-253"><strong>Start time</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-254">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-255">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-256"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-257">Ja</span><span class="sxs-lookup"><span data-stu-id="c8ffe-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-258">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="c8ffe-259">Metriken für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c8ffe-259">Metrics for conference participants</span></span>

<span data-ttu-id="c8ffe-260">In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="c8ffe-261">Metriken für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c8ffe-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8ffe-262">Name</span><span class="sxs-lookup"><span data-stu-id="c8ffe-262">Name</span></span></th>
<th><span data-ttu-id="c8ffe-263">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="c8ffe-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8ffe-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ffe-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-265"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-266">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-266">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-267">Konferenzrolle (z. B. Referent) des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-268"><strong>Teilnehmer</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-269">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-269">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-270">SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="c8ffe-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-271"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-272">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-272">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-273">Typ der Netzwerkverbindung.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-273">Network connection type.</span></span> <span data-ttu-id="c8ffe-274">Beispielsweise &quot;von Internal&quot; für interne Verbindung oder &quot;von PSTN&quot; für Einwahlbenutzer.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-275"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-276">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-276">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-277">Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8ffe-278"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-279">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-279">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-280">Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8ffe-281"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="c8ffe-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c8ffe-282">Nein</span><span class="sxs-lookup"><span data-stu-id="c8ffe-282">No</span></span></p></td>
<td><p><span data-ttu-id="c8ffe-p125">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="c8ffe-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

