---
title: 'Lync Server 2013: Bericht über Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d61e01574945fe090d3fd9425133f9569bd111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="0ace6-102">Anrufsteuerungsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ace6-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ace6-103">_**Letztes Änderungsstand des Themas:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="0ace6-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="0ace6-104">Der Bericht über Anrufsteuerung bietet Informationen über Peer-zu-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die von der Anrufsteuerung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ace6-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="0ace6-105">Die in Microsoft lync Server 2010 eingeführte Anrufsteuerung bietet Administratoren die Möglichkeit, Kommunikationssitzungen basierend auf Bandbreiteneinschränkungen zuzulassen (oder nicht zuzulassen).</span><span class="sxs-lookup"><span data-stu-id="0ace6-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="0ace6-106">Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken.</span><span class="sxs-lookup"><span data-stu-id="0ace6-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="0ace6-107">Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.</span><span class="sxs-lookup"><span data-stu-id="0ace6-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="0ace6-108">Öffnen des Berichts über Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="0ace6-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="0ace6-p102">Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite Monitoring Server-Berichte zu. Von diesem Bericht aus können Sie einen Drilldown zu folgenden weiteren Berichten durchführen:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="0ace6-111">Konferenzdetailbericht – Zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="0ace6-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="0ace6-112">Detailbericht über Peer-zu-Peer-Sitzungen – Zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0ace6-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="0ace6-113">Optimales Nutzen des Berichts über Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="0ace6-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="0ace6-p103">Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste Anrufkategorie den Eintrag Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="0ace6-p104">Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="0ace6-118">Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="0ace6-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0ace6-119">Filter</span><span class="sxs-lookup"><span data-stu-id="0ace6-119">Filters</span></span>

<span data-ttu-id="0ace6-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0ace6-124">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0ace6-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="0ace6-125">Anrufsteuerungsbericht – Filter</span><span class="sxs-lookup"><span data-stu-id="0ace6-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ace6-126">Name</span><span class="sxs-lookup"><span data-stu-id="0ace6-126">Name</span></span></th>
<th><span data-ttu-id="0ace6-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ace6-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0ace6-131">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="0ace6-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ace6-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ace6-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0ace6-134">7/17/12012</span></span></p>
<p><span data-ttu-id="0ace6-135">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="0ace6-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ace6-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0ace6-136">7/13/2012</span></span></p>
<p><span data-ttu-id="0ace6-137">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="0ace6-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-138"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0ace6-141">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="0ace6-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ace6-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ace6-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0ace6-144">7/17/12012</span></span></p>
<p><span data-ttu-id="0ace6-145">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="0ace6-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ace6-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0ace6-146">7/13/2012</span></span></p>
<p><span data-ttu-id="0ace6-147">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="0ace6-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-p110">Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-152"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-p111">Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="0ace6-155">Alle</span><span class="sxs-lookup"><span data-stu-id="0ace6-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="0ace6-156">Peer-zu-Peer</span><span class="sxs-lookup"><span data-stu-id="0ace6-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="0ace6-157">Konferenz</span><span class="sxs-lookup"><span data-stu-id="0ace6-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-158"><strong>Anrufkategorie</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-p112">Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="0ace6-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0ace6-161">Alle</span><span class="sxs-lookup"><span data-stu-id="0ace6-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="0ace6-162">Anruf durch Anrufsteuerung abgelehnt</span><span class="sxs-lookup"><span data-stu-id="0ace6-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="0ace6-163">Anrufe durch Anrufsteuerung über PSTN umgeleitet</span><span class="sxs-lookup"><span data-stu-id="0ace6-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0ace6-164">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="0ace6-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="0ace6-165">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ace6-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0ace6-166">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="0ace6-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ace6-167">Name</span><span class="sxs-lookup"><span data-stu-id="0ace6-167">Name</span></span></th>
<th><span data-ttu-id="0ace6-168">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="0ace6-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0ace6-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ace6-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-170"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-171">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-171">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-172">Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="0ace6-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-173"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-174">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-175">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0ace6-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-176"><strong>To user</strong> (An Benutzer)</span><span class="sxs-lookup"><span data-stu-id="0ace6-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-177">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-178">SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ace6-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-179"><strong>Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-180">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-181">Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0ace6-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-182"><strong>Zeitpunkt der Einladung</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-183">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-184">Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0ace6-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-185"><strong>Antwortzeit</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-186">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-187">Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ace6-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-188"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-189">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-190">Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</span><span class="sxs-lookup"><span data-stu-id="0ace6-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-191"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-192">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-p113">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0ace6-195">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="0ace6-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="0ace6-196">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ace6-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0ace6-197">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="0ace6-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ace6-198">Name</span><span class="sxs-lookup"><span data-stu-id="0ace6-198">Name</span></span></th>
<th><span data-ttu-id="0ace6-199">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="0ace6-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0ace6-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ace6-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-201"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-202">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-p114">Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-205"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-206">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-207">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="0ace6-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-209">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-210">In der Konferenz verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="0ace6-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-211"><strong>Beginn</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-212">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-213">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="0ace6-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-214"><strong>End time</strong> (Endzeit)</span><span class="sxs-lookup"><span data-stu-id="0ace6-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-215">Ja</span><span class="sxs-lookup"><span data-stu-id="0ace6-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ace6-216">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="0ace6-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0ace6-217">Metriken für einzelne Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0ace6-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="0ace6-218">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ace6-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0ace6-219">Metriken für einzelne Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0ace6-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ace6-220">Name</span><span class="sxs-lookup"><span data-stu-id="0ace6-220">Name</span></span></th>
<th><span data-ttu-id="0ace6-221">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="0ace6-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0ace6-222">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ace6-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-223"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-224">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-224">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-225">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="0ace6-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-226"><strong>Teilnehmer</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-227">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-227">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-228">SIP-Adresse des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="0ace6-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-229"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-230">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-230">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-231">Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="0ace6-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-232"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-233">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-233">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-234">Konferenztyp (z. B. A/V-Konferenzen).</span><span class="sxs-lookup"><span data-stu-id="0ace6-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-235"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-236">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-236">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-237">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0ace6-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ace6-238"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-239">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-239">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-240">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="0ace6-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ace6-241"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="0ace6-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0ace6-242">Nein</span><span class="sxs-lookup"><span data-stu-id="0ace6-242">No</span></span></p></td>
<td><p><span data-ttu-id="0ace6-p115">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="0ace6-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

