---
title: 'Lync Server 2013: Bericht über Anrufsteuerung'
description: 'Lync Server 2013: Bericht über Anrufsteuerung.'
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
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572361"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="dbf8e-103">Anrufsteuerungsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbf8e-103">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbf8e-104">_**Letztes Änderungsstand des Themas:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="dbf8e-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="dbf8e-105">Der Bericht über Anrufsteuerung bietet Informationen über Peer-zu-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die von der Anrufsteuerung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-105">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="dbf8e-106">Die in Microsoft lync Server 2010 eingeführte Anrufsteuerung bietet Administratoren die Möglichkeit, Kommunikationssitzungen basierend auf Bandbreiteneinschränkungen zuzulassen (oder nicht zuzulassen).</span><span class="sxs-lookup"><span data-stu-id="dbf8e-106">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="dbf8e-107">Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-107">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="dbf8e-108">Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-108">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="dbf8e-109">Öffnen des Berichts über Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-109">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="dbf8e-p102">Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite Monitoring Server-Berichte zu. Von diesem Bericht aus können Sie einen Drilldown zu folgenden weiteren Berichten durchführen:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="dbf8e-112">Konferenzdetailbericht – Zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine Konferenzsitzung.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-112">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="dbf8e-113">Detailbericht über Peer-zu-Peer-Sitzungen – Zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-113">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="dbf8e-114">Optimales Nutzen des Berichts über Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-114">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="dbf8e-p103">Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste Anrufkategorie den Eintrag Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="dbf8e-p104">Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="dbf8e-119">Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-119">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dbf8e-120">Filter</span><span class="sxs-lookup"><span data-stu-id="dbf8e-120">Filters</span></span>

<span data-ttu-id="dbf8e-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="dbf8e-125">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-125">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="dbf8e-126">Anrufsteuerungsbericht – Filter</span><span class="sxs-lookup"><span data-stu-id="dbf8e-126">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf8e-127">Name</span><span class="sxs-lookup"><span data-stu-id="dbf8e-127">Name</span></span></th>
<th><span data-ttu-id="dbf8e-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-129"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dbf8e-132">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="dbf8e-132">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbf8e-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbf8e-135">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbf8e-135">7/17/12012</span></span></p>
<p><span data-ttu-id="dbf8e-136">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="dbf8e-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbf8e-137">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbf8e-137">7/13/2012</span></span></p>
<p><span data-ttu-id="dbf8e-138">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-139"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dbf8e-142">17.7.2012 13:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="dbf8e-142">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbf8e-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbf8e-145">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbf8e-145">7/17/12012</span></span></p>
<p><span data-ttu-id="dbf8e-146">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="dbf8e-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbf8e-147">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbf8e-147">7/13/2012</span></span></p>
<p><span data-ttu-id="dbf8e-148">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-149"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-149"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p110">Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-153"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-153"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p111">Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf8e-156">Alle</span><span class="sxs-lookup"><span data-stu-id="dbf8e-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbf8e-157">Peer-zu-Peer</span><span class="sxs-lookup"><span data-stu-id="dbf8e-157">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="dbf8e-158">Konferenz</span><span class="sxs-lookup"><span data-stu-id="dbf8e-158">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-159"><strong>Anrufkategorie</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-159"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p112">Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf8e-162">Alle</span><span class="sxs-lookup"><span data-stu-id="dbf8e-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbf8e-163">Anruf durch Anrufsteuerung abgelehnt</span><span class="sxs-lookup"><span data-stu-id="dbf8e-163">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="dbf8e-164">Anrufe durch Anrufsteuerung über PSTN umgeleitet</span><span class="sxs-lookup"><span data-stu-id="dbf8e-164">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbf8e-165">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="dbf8e-165">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="dbf8e-166">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-166">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbf8e-167">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="dbf8e-167">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf8e-168">Name</span><span class="sxs-lookup"><span data-stu-id="dbf8e-168">Name</span></span></th>
<th><span data-ttu-id="dbf8e-169">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="dbf8e-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbf8e-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-171"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-171"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-172">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-172">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-173">Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-173">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-174"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-174"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-175">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-176">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-176">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-177"><strong>To user</strong> (An Benutzer)</span><span class="sxs-lookup"><span data-stu-id="dbf8e-177"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-178">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-179">SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-179">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-180"><strong>Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-180"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-181">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-181">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-182">Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-182">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-183"><strong>Zeitpunkt der Einladung</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-183"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-184">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-185">Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-185">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-186"><strong>Antwortzeit</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-186"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-187">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-188">Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-188">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-189"><strong>End time</strong> (Endzeit)</span><span class="sxs-lookup"><span data-stu-id="dbf8e-189"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-190">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-190">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-191">Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-191">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-192"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-192"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-193">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p113">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Headers sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbf8e-196">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="dbf8e-196">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="dbf8e-197">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-197">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbf8e-198">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="dbf8e-198">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf8e-199">Name</span><span class="sxs-lookup"><span data-stu-id="dbf8e-199">Name</span></span></th>
<th><span data-ttu-id="dbf8e-200">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="dbf8e-200">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbf8e-201">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-202"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-202"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-203">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p114">Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-206"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-206"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-207">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-208">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-208">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-209"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-209"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-210">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-211">In der Konferenz verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-211">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-212"><strong>Beginn</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-212"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-213">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-214">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-214">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-215"><strong>End time</strong> (Endzeit)</span><span class="sxs-lookup"><span data-stu-id="dbf8e-215"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-216">Ja</span><span class="sxs-lookup"><span data-stu-id="dbf8e-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-217">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-217">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbf8e-218">Metriken für einzelne Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="dbf8e-218">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="dbf8e-219">In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-219">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbf8e-220">Metriken für einzelne Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="dbf8e-220">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf8e-221">Name</span><span class="sxs-lookup"><span data-stu-id="dbf8e-221">Name</span></span></th>
<th><span data-ttu-id="dbf8e-222">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="dbf8e-222">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbf8e-223">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf8e-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-224"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-224"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-225">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-225">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-226">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-226">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-227"><strong>Teilnehmer</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-227"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-228">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-228">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-229">SIP-Adresse des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-229">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-230"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-230"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-231">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-231">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-232">Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-232">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-233"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-233"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-234">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-234">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-235">Konferenztyp (z. B. A/V-Konferenzen).</span><span class="sxs-lookup"><span data-stu-id="dbf8e-235">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-236"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-236"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-237">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-237">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-238">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-238">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf8e-239"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-239"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-240">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-240">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-241">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-241">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf8e-242"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="dbf8e-242"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf8e-243">Nein</span><span class="sxs-lookup"><span data-stu-id="dbf8e-243">No</span></span></p></td>
<td><p><span data-ttu-id="dbf8e-p115">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="dbf8e-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

