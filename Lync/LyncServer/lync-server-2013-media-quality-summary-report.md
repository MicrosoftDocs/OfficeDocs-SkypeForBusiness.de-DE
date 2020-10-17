---
title: 'Lync Server 2013: zusammenfassender Bericht über Medienqualität'
description: 'Lync Server 2013: zusammenfassender Bericht über Medienqualität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2616b7e3cdea9df7b004745a5c407188870903c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558071"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="38111-103">Zusammenfassender Bericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38111-103">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38111-104">_**Letztes Änderungsstand des Themas:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="38111-104">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="38111-105">Der "Zusammenfassende Bericht über Medienqualität" ist möglicherweise die beste Option zum Analysieren der Anrufqualität in Ihrer Organisation: In diesem Bericht werden detailliert die QoE-Anrufmetriken (Quality of Experience, QoE) in den folgenden Kategorien aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="38111-105">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="38111-106">UC-Peer-to-Peer-Anrufe (beispielsweise eine Microsoft lync 2013 für Microsoft lync 2013 Anruf)</span><span class="sxs-lookup"><span data-stu-id="38111-106">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="38111-107">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-107">UC Conference Sessions</span></span>

  - <span data-ttu-id="38111-108">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-108">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="38111-109">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="38111-109">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="38111-110">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-110">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="38111-111">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-111">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="38111-112">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="38111-112">Other Call Types</span></span>

<span data-ttu-id="38111-113">Beim ersten Öffnen des Berichts wird eine Zusammenfassung zu den einzelnen Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38111-113">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="38111-114">Ohne den Bericht zu verlassen, können Sie jede Kategorie erweitern, um Unterkategorien wie Aufrufe von Office Communicator 2007 R2 an lync 2013 zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="38111-114">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="38111-115">Diese Unterkategorien können Sie anschließend erweitern, um Details zu jedem in diesen Unterkategorien getätigten Anruf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="38111-115">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="38111-116">In Microsoft lync Server 2013 im zusammenfassenden Bericht über Medienqualität werden die Daten weiter in drei Anruftypen unterteilt: Audioanrufe, Videoanrufe und Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="38111-116">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="38111-117">Für jeden Anruftyp gibt es im Bericht einen eigenen Bereich und eigenen benutzerdefinierten Satz von Anrufmetriken.</span><span class="sxs-lookup"><span data-stu-id="38111-117">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="38111-118">Im "Zusammenfassenden Bericht über Medienqualität" können Sie Filter anwenden, mit denen Sie die Anrufqualität zwischen verkabelten und drahtlosen Anrufen, internen und externen Anrufen sowie VPN- und Nicht-VPN-Anrufen vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="38111-118">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="38111-119">Zugreifen auf den "Zusammenfassenden Bericht über Medienqualität"</span><span class="sxs-lookup"><span data-stu-id="38111-119">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="38111-120">Auf den "Zusammenfassenden Bericht über Medienqualität" kann auf der Startseite "Überwachungsberichte" zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="38111-120">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="38111-121">Sie können einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="38111-121">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="38111-122">Anrufvolumen</span><span class="sxs-lookup"><span data-stu-id="38111-122">Call volume</span></span>

  - <span data-ttu-id="38111-123">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="38111-123">Poor call percentage</span></span>

<span data-ttu-id="38111-124">Auf den "Zusammenfassenden Bericht über Medienqualität" können Sie auch zugreifen, indem Sie auf eine beliebige der folgenden Audioanrufmetriken klicken:</span><span class="sxs-lookup"><span data-stu-id="38111-124">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="38111-125">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="38111-125">Round trip (ms)</span></span>

  - <span data-ttu-id="38111-126">Beeinträchtigung (MOS)</span><span class="sxs-lookup"><span data-stu-id="38111-126">Degradation (MOS)</span></span>

  - <span data-ttu-id="38111-127">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="38111-127">Packet loss</span></span>

  - <span data-ttu-id="38111-128">Jitter (ms)</span><span class="sxs-lookup"><span data-stu-id="38111-128">Jitter (ms)</span></span>

  - <span data-ttu-id="38111-129">Ausblendungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="38111-129">Healer concealed ratio</span></span>

  - <span data-ttu-id="38111-130">Streckungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="38111-130">Healer stretched ratio</span></span>

  - <span data-ttu-id="38111-131">Komprimierungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="38111-131">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="38111-132">Filter</span><span class="sxs-lookup"><span data-stu-id="38111-132">Filters</span></span>

<span data-ttu-id="38111-p104">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Bespielsweise können Sie im zusammenfassenden Bericht über Medienqualität die zurückgegebenen Daten nach Zugriffstyp (d. h. interner oder externer Zugriff) oder nach Netzwerkverbindung (Kabel- oder Funkverbindung) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="38111-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="38111-137">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="38111-137">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="38111-138">Filter im Zusammenfassenden Bericht über Medienqualität</span><span class="sxs-lookup"><span data-stu-id="38111-138">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38111-139">Name</span><span class="sxs-lookup"><span data-stu-id="38111-139">Name</span></span></th>
<th><span data-ttu-id="38111-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38111-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38111-141"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="38111-141"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="38111-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="38111-144">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="38111-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38111-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="38111-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38111-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38111-147">7/7/2012</span></span></p>
<p><span data-ttu-id="38111-148">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="38111-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38111-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38111-149">7/3/2012</span></span></p>
<p><span data-ttu-id="38111-150">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="38111-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-151"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="38111-151"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="38111-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="38111-154">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="38111-154">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38111-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="38111-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38111-157">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38111-157">7/7/2012</span></span></p>
<p><span data-ttu-id="38111-158">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="38111-158">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38111-159">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38111-159">7/3/2012</span></span></p>
<p><span data-ttu-id="38111-160">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="38111-160">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-161"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="38111-161"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-p109">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38111-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-164">Alle</span><span class="sxs-lookup"><span data-stu-id="38111-164">[All]</span></span></p></li>
<li><p><span data-ttu-id="38111-165">Intern</span><span class="sxs-lookup"><span data-stu-id="38111-165">Internal</span></span></p></li>
<li><p><span data-ttu-id="38111-166">Extern</span><span class="sxs-lookup"><span data-stu-id="38111-166">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-167"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="38111-167"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-p110">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38111-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-170">Alle</span><span class="sxs-lookup"><span data-stu-id="38111-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="38111-171">Wired</span><span class="sxs-lookup"><span data-stu-id="38111-171">Wired</span></span></p></li>
<li><p><span data-ttu-id="38111-172">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="38111-172">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="38111-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38111-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-176">Alle</span><span class="sxs-lookup"><span data-stu-id="38111-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="38111-177">VPN</span><span class="sxs-lookup"><span data-stu-id="38111-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="38111-178">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="38111-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="38111-179">Metriken</span><span class="sxs-lookup"><span data-stu-id="38111-179">Metrics</span></span>

<span data-ttu-id="38111-180">In der folgenden Tabelle werden Metriken aufgelistet, die im Zusammenfassenden Bericht über Medienqualität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="38111-180">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="38111-181">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Audioanrufe</span><span class="sxs-lookup"><span data-stu-id="38111-181">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38111-182">Name</span><span class="sxs-lookup"><span data-stu-id="38111-182">Name</span></span></th>
<th><span data-ttu-id="38111-183">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="38111-183">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38111-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38111-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38111-185"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="38111-185"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-186">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-186">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p112">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="38111-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-189">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="38111-189">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="38111-190">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-190">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-191">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-191">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-192">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="38111-192">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="38111-193">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-193">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-194">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-194">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-195">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="38111-195">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-196"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="38111-196"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-197">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-197">No</span></span></p></td>
<td><p><span data-ttu-id="38111-198">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="38111-198">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-199"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="38111-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-200">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-200">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p113">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="38111-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-203"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-203"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-204">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-204">No</span></span></p></td>
<td><p><span data-ttu-id="38111-205">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-205">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-206"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-206"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-207">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-207">No</span></span></p></td>
<td><p><span data-ttu-id="38111-208">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-208">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-209"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-209"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-210">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-210">No</span></span></p></td>
<td><p><span data-ttu-id="38111-211">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="38111-211">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-212"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-212"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-213">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-213">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p114">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="38111-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="38111-p115">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="38111-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-218"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-218"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-219">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-219">No</span></span></p></td>
<td><p><span data-ttu-id="38111-220">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="38111-220">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="38111-221">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="38111-221">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="38111-222">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="38111-222">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="38111-223">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="38111-223">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="38111-224">In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="38111-224">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="38111-p117">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="38111-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-227"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="38111-227"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-228">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-228">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p118">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="38111-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-232"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-232"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-233">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-233">No</span></span></p></td>
<td><p><span data-ttu-id="38111-234">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-234">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38111-235">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="38111-235">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-236"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="38111-236"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-237">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-237">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p120">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="38111-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-240"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="38111-240"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-241">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-241">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p121">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="38111-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-244"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="38111-244"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-245">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-245">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p122">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="38111-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="38111-248">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Videoanrufe</span><span class="sxs-lookup"><span data-stu-id="38111-248">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38111-249">Name</span><span class="sxs-lookup"><span data-stu-id="38111-249">Name</span></span></th>
<th><span data-ttu-id="38111-250">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="38111-250">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38111-251">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38111-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38111-252"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="38111-252"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-253">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-253">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p123">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="38111-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-256">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="38111-256">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="38111-257">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-257">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-258">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-258">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-259">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="38111-259">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="38111-260">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-260">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-261">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-261">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-262">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="38111-262">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-263"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="38111-263"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-264">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-264">No</span></span></p></td>
<td><p><span data-ttu-id="38111-265">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="38111-265">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-266"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="38111-266"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-267">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-267">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p124">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="38111-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-270"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-270"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-271">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-271">No</span></span></p></td>
<td><p><span data-ttu-id="38111-272">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-272">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-273"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-273"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-274">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-274">No</span></span></p></td>
<td><p><span data-ttu-id="38111-275">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-275">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-276"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-276"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-277">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-277">No</span></span></p></td>
<td><p><span data-ttu-id="38111-278">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="38111-278">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-279"><strong>Durchschnittliche Bitrate (KBit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-279"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-280">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-280">No</span></span></p></td>
<td><p><span data-ttu-id="38111-281">Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="38111-281">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-282"><strong>Niedrige Bitrate %</strong></span><span class="sxs-lookup"><span data-stu-id="38111-282"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-283">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-283">No</span></span></p></td>
<td><p><span data-ttu-id="38111-284">Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.</span><span class="sxs-lookup"><span data-stu-id="38111-284">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-285"><strong>Verlust ausgehender Pakete</strong></span><span class="sxs-lookup"><span data-stu-id="38111-285"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-286">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-286">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p125">RTP-Paketverluste (Real-Time Transport Protocol) bei ausgehenden Paketen. (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="38111-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-290"><strong>Prozentzahl der eingefrorenen Frames</strong></span><span class="sxs-lookup"><span data-stu-id="38111-290"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-291">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-291">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p126">Prozentsatz der "eingefrorenen" Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.</span><span class="sxs-lookup"><span data-stu-id="38111-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-294"><strong>Durchschnittliche ausgehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="38111-294"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-295">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-295">No</span></span></p></td>
<td><p><span data-ttu-id="38111-296">Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="38111-296">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-297"><strong>Durchschnittliche eingehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="38111-297"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-298">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-298">No</span></span></p></td>
<td><p><span data-ttu-id="38111-299">Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="38111-299">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-300"><strong>Niedrige eingehende Framerate %</strong></span><span class="sxs-lookup"><span data-stu-id="38111-300"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-301">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-301">No</span></span></p></td>
<td><p><span data-ttu-id="38111-302">Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.</span><span class="sxs-lookup"><span data-stu-id="38111-302">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-303"><strong>Clientintegrität %</strong></span><span class="sxs-lookup"><span data-stu-id="38111-303"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38111-304">Gibt die relative Integrität des Clientgeräts während des Anrufs an.</span><span class="sxs-lookup"><span data-stu-id="38111-304">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="38111-305">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Anwendungsfreigabeanrufe</span><span class="sxs-lookup"><span data-stu-id="38111-305">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38111-306">Name</span><span class="sxs-lookup"><span data-stu-id="38111-306">Name</span></span></th>
<th><span data-ttu-id="38111-307">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="38111-307">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38111-308">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38111-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38111-309"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="38111-309"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-310">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-310">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p127">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="38111-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="38111-313">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="38111-313">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="38111-314">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-314">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-315">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="38111-315">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38111-316">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="38111-316">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="38111-317">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-317">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-318">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38111-318">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="38111-319">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="38111-319">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-320"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="38111-320"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-321">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-321">No</span></span></p></td>
<td><p><span data-ttu-id="38111-322">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="38111-322">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-323"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="38111-323"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-324">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-324">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p128">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="38111-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-327"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-327"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-328">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-328">No</span></span></p></td>
<td><p><span data-ttu-id="38111-329">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-329">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-330"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-330"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-331">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-331">No</span></span></p></td>
<td><p><span data-ttu-id="38111-332">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-332">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-333"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-333"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-334">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-334">No</span></span></p></td>
<td><p><span data-ttu-id="38111-335">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="38111-335">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-336"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="38111-336"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-337">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-337">No</span></span></p></td>
<td><p><span data-ttu-id="38111-338">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="38111-338">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38111-339">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="38111-339">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-340"><strong>Durchschnitt relativ unidirektional</strong></span><span class="sxs-lookup"><span data-stu-id="38111-340"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-341">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-341">No</span></span></p></td>
<td><p><span data-ttu-id="38111-p130">Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="38111-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38111-344"><strong>Durchschnittliche Latenz der RDP-Kachelverarbeitung</strong></span><span class="sxs-lookup"><span data-stu-id="38111-344"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-345">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-345">No</span></span></p></td>
<td><p><span data-ttu-id="38111-346">Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="38111-346">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="38111-347">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an und umfasst die Netzwerkwartezeit.</span><span class="sxs-lookup"><span data-stu-id="38111-347">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="38111-348">Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="38111-348">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38111-349"><strong>Insgesamt schlechte Kacheln %</strong></span><span class="sxs-lookup"><span data-stu-id="38111-349"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="38111-350">Nein</span><span class="sxs-lookup"><span data-stu-id="38111-350">No</span></span></p></td>
<td><p><span data-ttu-id="38111-351">Gesamtprozentsatz schlechter RDP-Kacheln.</span><span class="sxs-lookup"><span data-stu-id="38111-351">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

